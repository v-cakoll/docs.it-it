---
title: Distribuzione di eShopOnContainers in Azure
description: Distribuzione dell'applicazione eShopOnContainers tramite il servizio Kubernetes di Azure, Helm e DevSpaces.
ms.date: 05/13/2020
ms.openlocfilehash: 93a2848f095d7593e1e169f4a6c6c1818a76217d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614097"
---
# <a name="deploying-eshoponcontainers-to-azure"></a>Distribuzione di eShopOnContainers in Azure

L'applicazione eShopOnContainers può essere distribuita in un'ampia gamma di piattaforme Azure. L'approccio consigliato consiste nel distribuire l'applicazione in Azure Kubernetes Services (AKS). Helm, uno strumento di distribuzione Kubernetes, è disponibile per ridurre la complessità della distribuzione. Facoltativamente, gli sviluppatori possono implementare Azure Dev Spaces per Kubernetes per semplificare il processo di sviluppo.

## <a name="azure-kubernetes-service"></a>Servizio Azure Kubernetes

Per ospitare eShop in AKS, il primo passaggio consiste nel creare un cluster AKS. A tale scopo, è possibile usare la portale di Azure, che illustra i passaggi necessari. È anche possibile creare un cluster dall'interfaccia della riga di comando di Azure, prestando attenzione per abilitare il controllo degli accessi in base al ruolo e il routing dell'applicazione. La documentazione di eShopOnContainers descrive i passaggi per la creazione del cluster AKS. Una volta creato, è possibile accedere al cluster e gestirlo dal dashboard di Kubernetes.

È ora possibile distribuire l'applicazione eShop nel cluster sfruttando Helm e Tiller.

## <a name="deploying-to-azure-kubernetes-service-using-helm"></a>Distribuzione nel servizio Azure Kubernetes tramite Helm

Helm è uno strumento di gestione dei pacchetti dell'applicazione che funziona direttamente con Kubernetes. Consente di definire, installare e aggiornare le applicazioni Kubernetes. Sebbene le app semplici possano essere distribuite in AKS con script dell'interfaccia della riga di comando personalizzati o semplici file di distribuzione, le app complesse possono contenere molti oggetti Kubernetes e trarre vantaggio da Helm.

Con Helm, le applicazioni includono file di configurazione basati su testo, chiamati grafici Helm, che descrivono in modo dichiarativo l'applicazione e la configurazione nei pacchetti Helm. I grafici usano file in formato YAML standard per descrivere un set correlato di risorse Kubernetes. Viene eseguito il controllo delle versioni insieme al codice dell'applicazione descritto. I grafici Helm variano da semplici a complessi, a seconda dei requisiti dell'installazione che descrivono.

Helm è costituito da uno strumento client da riga di comando che utilizza i grafici Helm e avvia i comandi in un componente server denominato, Tiller. Il timone comunica con l'API Kubernetes per garantire il corretto provisioning dei carichi di lavoro in contenitori. Helm è gestito da cloud-native Computing Foundation.

Il file YAML seguente presenta un modello Helm:

```yaml
apiVersion: v1
kind: Service
metadata:
  name: {{ .Values.app.svc.marketing }}
  labels:
    app: {{ template "marketing-api.name" . }}
    chart: {{ template "marketing-api.chart" . }}
    release: {{ .Release.Name }}
    heritage: {{ .Release.Service }}
spec:
  type: {{ .Values.service.type }}
  ports:
    - port: {{ .Values.service.port }}
      targetPort: http
      protocol: TCP
      name: http
  selector:
    app: {{ template "marketing-api.name" . }}
    release: {{ .Release.Name }}
```

Si noti come il modello descrive un set dinamico di coppie chiave/valore. Quando il modello viene richiamato, i valori racchiusi tra parentesi graffe vengono estratti da altri file di configurazione basati su YAML.

I grafici Helm di eShopOnContainers sono disponibili nella cartella/K8S/Helm. La figura 2-6 illustra come i diversi componenti dell'applicazione sono organizzati in una struttura di cartelle utilizzata da Helm per definire e distribuire le distribuzioni.

![Architettura eShopOnContainers ](./media/eshoponcontainers-helm-folder.png)
 **Figura 2-6**. Cartella Helm eShopOnContainers.

Ogni singolo componente viene installato utilizzando un `helm install` comando. eShop include uno script "deploy all" che esegue il ciclo e installa i componenti usando i rispettivi grafici Helm. Il risultato è un processo ripetibile, con versione con l'applicazione nel controllo del codice sorgente, che chiunque nel team può distribuire in un cluster AKS con un comando di script a una riga.

> Si noti che la versione 3 di Helm Elimina ufficialmente la necessità di un componente del server di Tiller. Altre informazioni su questo miglioramento sono disponibili [qui](https://medium.com/better-programming/why-is-tiller-missing-in-helm-3-2347c446714).

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Le applicazioni native del cloud possono diventare rapidamente grandi e complesse, con la necessità di eseguire risorse di calcolo significative. In questi scenari, l'intera applicazione non può essere ospitata in un computer di sviluppo, soprattutto in un computer portatile. Azure Dev Spaces è progettato per risolvere questo problema usando AKS. Consente agli sviluppatori di usare una versione locale dei servizi mentre ospita il resto dell'applicazione in un cluster di sviluppo AKS.

Gli sviluppatori condividono un'istanza in esecuzione (sviluppo) in un cluster AKS che contiene l'intera applicazione in contenitori. Ma usano gli spazi personali configurati nel computer per lo sviluppo locale dei servizi. Quando si è pronti, viene testato da end-to-end nel cluster AKS senza replicare le dipendenze. Azure Dev Spaces unisce il codice del computer locale con i servizi in AKS. I membri del team possono vedere come si comporteranno le modifiche in un ambiente AKS reale. Gli sviluppatori possono eseguire rapidamente l'iterazione e il debug del codice direttamente in Kubernetes usando Visual Studio 2017 o Visual Studio Code.

Nella figura 2-7 è possibile vedere che lo sviluppatore Susie ha distribuito una versione aggiornata del microservizio Bikes nello spazio di sviluppo. Potrà quindi testare le modifiche usando un URL personalizzato che inizia con il nome dello spazio (susie.s.dev.myapp.eus.azds.io).

![Architettura eShopOnContainers ](./media/azure-devspaces-one.png)
 **Figura 2-7**. Developer Susie distribuisce la propria versione del microservizio Bikes e ne esegue il test.

Allo stesso tempo, lo sviluppatore Giorgio sta personalizzando il microservizio prenotazioni e deve testare le proprie modifiche. Distribuisce le modifiche nel proprio spazio di sviluppo senza conflitti con le modifiche di Susie, come illustrato nella figura 2-8. Giorgio quindi testa le modifiche usando il proprio URL, che è preceduto dal nome dello spazio (john.s.dev.myapp.eus.azds.io).

![Architettura eShopOnContainers ](./media/azure-devspaces-two.png)
 **Figura 2-8**. Developer Giorgio distribuisce la propria versione del microservizio prenotazioni e la testa senza conflitti con altri sviluppatori.

Con Azure Dev Spaces, i team possono lavorare direttamente con AKS mentre cambiano, distribuiscono e verificano le modifiche in modo indipendente. Questo approccio riduce la necessità di ambienti host dedicati distinti, perché ogni sviluppatore ha in effetti un proprio ambiente AKS. Gli sviluppatori possono lavorare con Azure Dev Spaces usando l'interfaccia della riga di comando o avviare l'applicazione per Azure Dev Spaces direttamente da Visual Studio. [Altre informazioni sul funzionamento di Azure Dev Spaces e sulla configurazione.](https://docs.microsoft.com/azure/dev-spaces/how-dev-spaces-works)

## <a name="azure-functions-and-logic-apps-serverless"></a>Funzioni di Azure e app per la logica (senza server)

L'esempio eShopOnContainers include il supporto per tenere traccia delle campagne di marketing online. Una funzione di Azure viene usata per tenere traccia dei dettagli della campagna di marketing per un determinato ID campagna. Anziché creare un microservizio completo, una singola funzione di Azure è più semplice e sufficiente. Funzioni di Azure include un semplice modello di compilazione e distribuzione, specialmente se configurato per l'esecuzione in Kubernetes. La distribuzione della funzione viene scritta tramite script usando i modelli di Azure Resource Manager (ARM) e l'interfaccia della riga di comando di Azure. Questo servizio della campagna non è rivolte al cliente e richiama una singola operazione, rendendolo un candidato ideale per funzioni di Azure. La funzione richiede una configurazione minima, incluse le impostazioni di dati della stringa di connessione del database e dell'URI di base dell'immagine. Le funzioni di Azure vengono configurate nel portale di Azure.

>[!div class="step-by-step"]
>[Precedente](map-eshoponcontainers-azure-services.md) 
> [Avanti](centralized-configuration.md)
