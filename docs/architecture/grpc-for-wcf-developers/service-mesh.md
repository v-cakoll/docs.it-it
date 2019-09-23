---
title: Mesh del servizio-gRPC per sviluppatori WCF
description: Uso di una rete mesh di servizi per indirizzare e bilanciare le richieste ai servizi gRPC in un cluster Kubernetes.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 7fc80b95937dab9153b72aa6bc8da90f6453779f
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184092"
---
# <a name="service-meshes"></a>Mesh del servizio

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Una mesh di servizi è un componente dell'infrastruttura che prende il controllo del routing delle richieste di servizio all'interno di una rete. Le mesh del servizio possono gestire tutti i tipi di problemi a livello di rete all'interno di un cluster Kubernetes, tra cui:

- Individuazione del servizio
- Bilanciamento del carico
- Tolleranza di errore
- Crittografia
- Monitoraggio

Il servizio Kubernetes mesh funziona aggiungendo un contenitore aggiuntivo, denominato *sidecar proxy*, a ogni pod incluso nella rete. Il proxy acquisisce la gestione di tutte le richieste di rete in ingresso e in uscita, consentendo la configurazione e la gestione delle operazioni di rete da mantenere separate dai contenitori dell'applicazione e, in molti casi, senza richiedere alcuna modifica al codice dell'applicazione.

Prendere l' [esempio del capitolo precedente](kubernetes.md#testing-the-application), in cui le richieste gRPC dall'applicazione Web sono state indirizzate a una singola istanza del servizio gRPC. Questo problema si verifica perché il nome host del servizio viene risolto in un indirizzo IP e tale indirizzo IP viene memorizzato nella cache per `HttpClientHandler` la durata dell'istanza. Potrebbe essere possibile aggirare questo problema gestendo manualmente le ricerche DNS o creando più client, ma ciò complica notevolmente il codice dell'applicazione senza aggiungere alcun valore aziendale o cliente.

Usando una mesh di servizi, le richieste provenienti dal contenitore dell'applicazione vengono inviate al proxy sidecar, che può distribuirle in modo intelligente in tutte le istanze dell'altro servizio. Il mesh può anche:

- Rispondere facilmente agli errori delle singole istanze di un servizio.
- Gestire la semantica di ripetizione dei tentativi per le chiamate non riuscite o i timeout
- Reindirizzare le richieste non riuscite a un'istanza alternativa senza tornare all'applicazione client.

Lo screenshot seguente illustra l'applicazione StockWeb in esecuzione con la mesh del servizio Linkerd, senza modifiche al codice dell'applicazione o anche all'immagine Docker usata. L'unica modifica necessaria è l'aggiunta di un'annotazione alla distribuzione nei file YAML per i `stockdata` servizi `stockweb` e.

![StockWeb con mesh del servizio](media/service-mesh/stockweb-servicemesh-screenshot.png)

Dalla colonna Server è possibile vedere che le richieste dall'applicazione StockWeb sono state indirizzate a entrambe le repliche del servizio StockData, nonostante l'origine da una singola `HttpClient` istanza nel codice dell'applicazione. Infatti, se si esamina il codice, si noterà che tutte le richieste 100 al servizio StockData vengono effettuate simultaneamente utilizzando la stessa `HttpClient` istanza, ma con la mesh del servizio, tali richieste verranno bilanciate in molte istanze del servizio disponibili.

Le mesh del servizio si applicano solo al traffico all'interno di un cluster. Per i client esterni, vedere [il capitolo successivo, bilanciamento del carico](load-balancing.md).

## <a name="service-mesh-options"></a>Opzioni di mesh del servizio

Sono attualmente disponibili tre implementazioni di rete di servizi generiche da usare con Kubernetes: Istio, Linkerd e Consul Connect. Tutte e tre forniscono routing/inoltro delle richieste, crittografia del traffico, resilienza, autenticazione da host a host e controllo del traffico.

La scelta di una mesh di servizi dipende da diversi fattori: 

- Requisiti specifici dell'organizzazione relativi ai costi, alla conformità, ai piani di supporto a pagamento e così via. 
- La natura del cluster, le dimensioni, il numero di servizi distribuiti e il volume di traffico all'interno della rete cluster.
- Semplifica la distribuzione e la gestione della rete e la sua uso con i servizi.

Altre informazioni su ogni mesh di servizi sono disponibili nei rispettivi siti Web.

- [**Istio** -Istio.io](https://istio.io)
- [**Linkerd** -linkerd.io](https://linkerd.io)
- [**Console** -Consul.io/mesh.html](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a>Esempio: aggiungere Linkerd a una distribuzione

In questo esempio si apprenderà come usare la mesh del servizio Linkerd con l'applicazione *StockKube* della [sezione precedente](kubernetes.md).
Per seguire questo esempio, è necessario [installare l'interfaccia della](https://linkerd.io/2/getting-started/#step-1-install-the-cli)riga di comando di Linkerd. I file binari di Windows possono essere scaricati dalla sezione relativa alle versioni di GitHub. Assicurarsi di usare la versione **stabile** più recente e non una delle versioni perimetrali.

Con l'interfaccia della riga di comando di Linkerd installata, seguire le [istruzioni*Introduzione* nel sito Web Linkerd] per installare i componenti Linkerd nel cluster Kubernetes. Le istruzioni sono semplici e l'installazione dovrebbe richiedere solo alcuni minuti in un'istanza locale di Kubernetes.

### <a name="add-linkerd-to-kubernetes-deployments"></a>Aggiungere Linkerd alle distribuzioni di Kubernetes

L'interfaccia della riga di `inject` comando di Linkerd fornisce un comando per aggiungere le sezioni e le proprietà necessarie ai file Kubernetes. È possibile eseguire il comando e scrivere l'output in un nuovo file.

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

È possibile esaminare i nuovi file per vedere quali modifiche sono state apportate. Per gli oggetti di distribuzione, viene aggiunta un'annotazione dei metadati per indicare a Linkerd di inserire un contenitore del proxy sidecar nel pod quando viene creato.

È anche possibile inviare tramite pipe l'output del `linkerd inject` comando a `kubectl` direttamente. I comandi seguenti funzioneranno in PowerShell o in qualsiasi shell Linux.

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a>Esaminare i servizi nel dashboard di Linkerd

Avviare il dashboard di Linkerd usando `linkerd` l'interfaccia della riga di comando.

```console
linkerd dashboard
```

Il dashboard fornisce informazioni dettagliate su tutti i servizi connessi alla rete.

![Dashboard Linkerd che mostra le applicazioni StockKube](media/service-mesh/linkerd-screenshot.png)

Se si aumenta il numero di repliche del servizio StockData gRPC, come illustrato nell'esempio seguente, e si aggiorna la pagina StockWeb nel browser, viene visualizzata una combinazione di ID nella colonna Server, che indica che le richieste vengono gestite da tutte le istanze disponibili .

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
>[Precedente](kubernetes.md)
>[Successivo](load-balancing.md)
