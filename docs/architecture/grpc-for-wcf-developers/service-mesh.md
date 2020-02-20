---
title: Mesh del servizio-gRPC per sviluppatori WCF
description: Uso di una rete mesh di servizi per indirizzare e bilanciare le richieste ai servizi gRPC in un cluster Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: a29d6893e585c7eb60c847cef0149afeeaebcdab
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503393"
---
# <a name="service-meshes"></a>Mesh del servizio

Una mesh di servizi è un componente dell'infrastruttura che prende il controllo del routing delle richieste di servizio all'interno di una rete. Le mesh del servizio possono gestire tutti i tipi di problemi a livello di rete all'interno di un cluster Kubernetes, tra cui:

- Individuazione del servizio
- Bilanciamento del carico
- Tolleranza di errore
- Crittografia
- Monitoraggio

Il servizio Kubernetes mesh funziona aggiungendo un contenitore aggiuntivo, denominato *sidecar proxy*, a ogni pod incluso nella rete. Il proxy acquisisce la gestione di tutte le richieste di rete in ingresso e in uscita. È quindi possibile gestire la configurazione e la gestione delle questioni di rete separate dai contenitori di applicazioni. In molti casi, questa separazione non richiede alcuna modifica al codice dell'applicazione.

Nell' [esempio del capitolo precedente](kubernetes.md#test-the-application), le richieste gRPC dall'applicazione Web sono state indirizzate a una singola istanza del servizio gRPC. Questo problema si verifica perché il nome host del servizio viene risolto in un indirizzo IP e tale indirizzo IP viene memorizzato nella cache per la durata dell'istanza di `HttpClientHandler`. Potrebbe essere possibile aggirare questo problema gestendo manualmente le ricerche DNS o creando più client. Questa soluzione potrebbe tuttavia complicare il codice dell'applicazione senza aggiungere alcun valore aziendale o del cliente.

Quando si usa una mesh di servizi, le richieste provenienti dal contenitore dell'applicazione vengono inviate al proxy sidecar. Il proxy sidecar può quindi distribuirli in modo intelligente in tutte le istanze dell'altro servizio. Il mesh può anche:

- Rispondere facilmente agli errori delle singole istanze di un servizio.
- Gestire la semantica di ripetizione dei tentativi per le chiamate non riuscite o i timeout.
- Reindirizzare le richieste non riuscite a un'istanza alternativa senza tornare all'applicazione client.

Lo screenshot seguente illustra l'applicazione StockWeb in esecuzione con la mesh del servizio Linkerd. Non sono state apportate modifiche al codice dell'applicazione e l'immagine Docker non è in uso. L'unica modifica necessaria è l'aggiunta di un'annotazione alla distribuzione nei file YAML per i servizi `stockdata` e `stockweb`.

![StockWeb con mesh del servizio](media/service-mesh/stockweb-servicemesh-screenshot.png)

Dalla colonna **Server** è possibile vedere che le richieste dall'applicazione StockWeb sono state indirizzate a entrambe le repliche del servizio StockData, anche se originate da una singola istanza `HttpClient` nel codice dell'applicazione. Infatti, se si esamina il codice, si noterà che tutte le richieste 100 al servizio StockData vengono effettuate simultaneamente utilizzando la stessa istanza di `HttpClient`. Con la mesh dei servizi, le richieste verranno bilanciate tra loro, ma sono disponibili molte istanze del servizio.

Le mesh del servizio si applicano solo al traffico all'interno di un cluster. Per i client esterni, vedere il capitolo successivo, [bilanciamento del carico](load-balancing.md).

## <a name="service-mesh-options"></a>Opzioni di mesh del servizio

Sono attualmente disponibili tre implementazioni di rete di servizi generici per l'uso con Kubernetes: [Istio](https://istio.io), [Linkerd](https://linkerd.io)e [console connect](https://consul.io/mesh.html). Tutte e tre forniscono routing/inoltro delle richieste, crittografia del traffico, resilienza, autenticazione da host a host e controllo del traffico.

La scelta di una mesh di servizi dipende da diversi fattori:

- Requisiti specifici dell'organizzazione relativi ai costi, alla conformità, ai piani di supporto a pagamento e così via.
- La natura del cluster, le dimensioni, il numero di servizi distribuiti e il volume di traffico all'interno della rete cluster.
- Semplifica la distribuzione e la gestione della rete e la sua uso con i servizi.

## <a name="example-add-linkerd-to-a-deployment"></a>Esempio: aggiungere Linkerd a una distribuzione

In questo esempio si apprenderà come usare la mesh del servizio Linkerd con l'applicazione *StockKube* della [sezione precedente](kubernetes.md).
Per seguire questo esempio, è necessario [installare l'interfaccia della](https://linkerd.io/2/getting-started/#step-1-install-the-cli)riga di comando di Linkerd. È possibile scaricare i file binari di Windows dalla sezione che elenca le versioni di GitHub. Assicurarsi di usare la versione *stabile* più recente e non una delle versioni perimetrali.

Con l'interfaccia della riga di comando di Linkerd installata, seguire le istruzioni [Introduzione](https://linkerd.io/2/getting-started/index.html) per installare i componenti di Linkerd nel cluster Kubernetes. Le istruzioni sono semplici e l'installazione dovrebbe richiedere solo un paio di minuti in un'istanza locale di Kubernetes.

### <a name="add-linkerd-to-kubernetes-deployments"></a>Aggiungere Linkerd alle distribuzioni di Kubernetes

L'interfaccia della riga di comando di Linkerd fornisce un comando `inject` per aggiungere le sezioni e le proprietà necessarie ai file Kubernetes. È possibile eseguire il comando e scrivere l'output in un nuovo file.

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

È possibile esaminare i nuovi file per vedere quali modifiche sono state apportate. Per gli oggetti di distribuzione, viene aggiunta un'annotazione dei metadati per indicare a Linkerd di inserire un contenitore del proxy sidecar nel pod quando viene creato.

È anche possibile inviare tramite pipe l'output del comando `linkerd inject` per `kubectl` direttamente. I comandi seguenti funzioneranno in PowerShell o in qualsiasi shell Linux.

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a>Esaminare i servizi nel dashboard di Linkerd

Aprire il dashboard di Linkerd usando l'interfaccia della riga di comando `linkerd`.

```console
linkerd dashboard
```

Il dashboard fornisce informazioni dettagliate su tutti i servizi connessi alla rete.

![Dashboard Linkerd che mostra le applicazioni StockKube](media/service-mesh/linkerd-screenshot.png)

Se si aumenta il numero di repliche del servizio StockData gRPC, come illustrato nell'esempio seguente, e si aggiorna la pagina StockWeb nel browser, viene visualizzata una combinazione di ID nella colonna **Server** . Questa combinazione indica che tutte le istanze disponibili sono in grado di soddisfare le richieste.

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
