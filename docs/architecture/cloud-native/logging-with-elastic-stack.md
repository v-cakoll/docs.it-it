---
title: Registrazione con Elastic Stack
description: Registrazione con Elastic stack, logstash e Kibana
ms.date: 05/13/2020
ms.openlocfilehash: e886141fa691b75b882b5d67eae4ceb242e8089f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613850"
---
# <a name="logging-with-elastic-stack"></a>Registrazione con Elastic Stack

Sono disponibili molti strumenti di registrazione centralizzati e i costi variano a seconda del fatto che siano disponibili strumenti Open Source gratuiti per le opzioni più costose. In molti casi, gli strumenti gratuiti sono più efficaci o migliori delle offerte a pagamento. Uno di questi strumenti è costituito da una combinazione di tre componenti Open Source: ricerca elastica, logstash e Kibana.

Collettivamente questi strumenti sono noti come stack elastico o ELK.

## <a name="elastic-stack"></a>Elastic stack

Elastic stack è un'opzione potente per la raccolta di informazioni da un cluster Kubernetes. Kubernetes supporta l'invio di log a un endpoint elasticsearch e, nella [maggior parte dei casi](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), è sufficiente impostare le variabili di ambiente, come illustrato nella figura 7-5:

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

**Figura 7-5.** Variabili di configurazione per Kubernetes

Verrà installato elasticsearch nel cluster e la destinazione invierà tutti i log del cluster.

![Un esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes ](./media/kibana-dashboard.png)
 **Figura 7-6**. Esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes

## <a name="what-are-the-advantages-of-elastic-stack"></a>Quali sono i vantaggi di Elastic stack?

Elastic stack fornisce la registrazione centralizzata in modo semplice e a basso costo. L'interfaccia utente semplifica l'analisi dei dati, in modo da poter dedicare tempo alla spigolatura dei dati, anziché a un'interfaccia goffa. Supporta un'ampia gamma di input, in modo che l'applicazione distribuita si estenda su più tipi di servizi, ma è possibile prevedere di continuare a inserire dati di log e metriche nel sistema. Elastic stack supporta inoltre le ricerche rapide anche nei set di dati di grandi dimensioni, rendendo possibile anche per le applicazioni di grandi dimensioni registrare dati dettagliati e comunque essere in grado di renderli visibili in modo efficiente.

## <a name="logstash"></a>Logstash

Il primo componente è [logstash](https://www.elastic.co/products/logstash). Questo strumento viene usato per raccogliere informazioni di log da un'ampia gamma di origini diverse. Ad esempio, logstash può leggere i log dal disco e ricevere anche messaggi dalle librerie di registrazione come [Serilog](https://serilog.net/). Logstash è in grado di eseguire operazioni di filtro e espansione di base nei log Man mano che arrivano. Se, ad esempio, i log contengono indirizzi IP, è possibile configurare logstash per eseguire una ricerca geografica e ottenere un paese o anche una città di origine per quel messaggio.

Serilog è una libreria di registrazione per i linguaggi .NET, che consente la registrazione con parametri. Anziché generare un messaggio di log testuale che incorpora campi, i parametri vengono mantenuti separati. Questo consente un filtro e una ricerca più intelligenti. Nella figura 7-7 viene visualizzata una configurazione Serilog di esempio per la scrittura in logstash.

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

**Figura 7-7**. Configurazione di Serilog per la scrittura di informazioni di log direttamente in logstash su HTTP

Logstash utilizzerebbe una configurazione come quella illustrata nella figura 7-8.

```
input {
    http {
        #default host 0.0.0.0:8080
        codec => json
    }
}

output {
    elasticsearch {
        hosts => "elasticsearch:9200"
        index=>"sales-%{+xxxx.ww}"
    }
}
```

**Figura 7-8**. Una configurazione logstash per l'utilizzo di log da Serilog

Per gli scenari in cui non è necessaria una manipolazione estesa dei log, esiste un'alternativa a logstash noto come [Beats](https://www.elastic.co/products/beats). Beats è una famiglia di strumenti che consente di raccogliere un'ampia gamma di dati dai log ai dati di rete e alle informazioni di tempo di esecuzione. Molte applicazioni utilizzeranno sia logstash che Beats.

Una volta che i log sono stati raccolti da logstash, è necessario un punto in cui inserirli. Sebbene logstash supporti molti output diversi, uno dei più interessanti è la ricerca elastica.

## <a name="elastic-search"></a>Ricerca elastica

La ricerca elastica è un motore di ricerca potente che può indicizzare i log Man mano che arrivano. Consente di eseguire rapidamente query sui log. La ricerca elastica può gestire grandi quantità di log e, in casi estremi, può essere scalato orizzontalmente in più nodi.

I messaggi di log che sono stati creati per contenere parametri o i cui parametri sono stati divisi tramite l'elaborazione di logstash, possono essere sottoposti a query direttamente perché elasticsearch conserva queste informazioni.

Una query che cerca le prime 10 pagine visitate da `jill@example.com` viene visualizzata nella figura 7-9.

```
"query": {
    "match": {
      "user": "jill@example.com"
    }
  },
  "aggregations": {
    "top_10_pages": {
      "terms": {
        "field": "page",
        "size": 10
      }
    }
  }
```

**Figura 7-9**. Una query elasticsearch per trovare le prime 10 pagine visitate da un utente

## <a name="visualizing-information-with-kibana-web-dashboards"></a>Visualizzazione di informazioni con i dashboard Web di Kibana

Il componente finale dello stack è Kibana. Questo strumento viene usato per fornire visualizzazioni interattive in un dashboard Web. I dashboard possono essere creati anche dagli utenti non tecnici. La maggior parte dei dati residenti nell'indice elasticsearch può essere inclusa nei dashboard di Kibana. I singoli utenti possono avere desideri diversi per i dashboard e Kibana consente questa personalizzazione attraverso la possibilità di dashboard specifici dell'utente.

## <a name="installing-elastic-stack-on-azure"></a>Installazione di Elastic stack in Azure

Lo stack elastico può essere installato in Azure in diversi modi. Come sempre, è possibile eseguire [il provisioning di macchine virtuali e installare Elastic stack direttamente su di essi](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch). Questa opzione è preferibile ad alcuni utenti esperti perché offre il massimo grado di personalizzazione. La distribuzione nell'infrastruttura come servizio introduce un sovraccarico di gestione significativo che impone a coloro che prendono tale percorso di assumere la proprietà di tutte le attività associate all'infrastruttura come servizio, ad esempio la protezione dei computer e la conservazione delle patch.

Un'opzione con un sovraccarico minore consiste nell'usare uno dei molti contenitori Docker in cui è già stato configurato lo stack elastico. Questi contenitori possono essere rilasciati in un cluster Kubernetes esistente ed eseguiti insieme al codice dell'applicazione. Il contenitore [sebp/Elk](https://elk-docker.readthedocs.io/) è un contenitore di stack elastico ben documentato e testato.

Un'altra opzione è una nuova [offerta di Elk come servizio annunciata di recente](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).

## <a name="references"></a>Riferimenti

- [Installare Elastic stack in Azure](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
>[Precedente](observability-patterns.md) 
> [Avanti](monitoring-azure-kubernetes.md)
