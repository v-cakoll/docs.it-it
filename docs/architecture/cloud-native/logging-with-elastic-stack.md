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
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="843cb-103">Registrazione con Elastic Stack</span><span class="sxs-lookup"><span data-stu-id="843cb-103">Logging with Elastic Stack</span></span>

<span data-ttu-id="843cb-104">Sono disponibili molti strumenti di registrazione centralizzati e i costi variano a seconda del fatto che siano disponibili strumenti Open Source gratuiti per le opzioni più costose.</span><span class="sxs-lookup"><span data-stu-id="843cb-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="843cb-105">In molti casi, gli strumenti gratuiti sono più efficaci o migliori delle offerte a pagamento.</span><span class="sxs-lookup"><span data-stu-id="843cb-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="843cb-106">Uno di questi strumenti è costituito da una combinazione di tre componenti Open Source: ricerca elastica, logstash e Kibana.</span><span class="sxs-lookup"><span data-stu-id="843cb-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>

<span data-ttu-id="843cb-107">Collettivamente questi strumenti sono noti come stack elastico o ELK.</span><span class="sxs-lookup"><span data-stu-id="843cb-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="843cb-108">Elastic stack</span><span class="sxs-lookup"><span data-stu-id="843cb-108">Elastic Stack</span></span>

<span data-ttu-id="843cb-109">Elastic stack è un'opzione potente per la raccolta di informazioni da un cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="843cb-109">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="843cb-110">Kubernetes supporta l'invio di log a un endpoint elasticsearch e, nella [maggior parte dei casi](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), è sufficiente impostare le variabili di ambiente, come illustrato nella figura 7-5:</span><span class="sxs-lookup"><span data-stu-id="843cb-110">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="843cb-111">**Figura 7-5.**</span><span class="sxs-lookup"><span data-stu-id="843cb-111">**Figure 7-5**.</span></span> <span data-ttu-id="843cb-112">Variabili di configurazione per Kubernetes</span><span class="sxs-lookup"><span data-stu-id="843cb-112">Configuration variables for Kubernetes</span></span>

<span data-ttu-id="843cb-113">Verrà installato elasticsearch nel cluster e la destinazione invierà tutti i log del cluster.</span><span class="sxs-lookup"><span data-stu-id="843cb-113">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="843cb-114">![Un esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes ](./media/kibana-dashboard.png)
 **Figura 7-6**.</span><span class="sxs-lookup"><span data-stu-id="843cb-114">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="843cb-115">Esempio di dashboard Kibana che mostra i risultati di una query sui log inseriti da Kubernetes</span><span class="sxs-lookup"><span data-stu-id="843cb-115">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="843cb-116">Quali sono i vantaggi di Elastic stack?</span><span class="sxs-lookup"><span data-stu-id="843cb-116">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="843cb-117">Elastic stack fornisce la registrazione centralizzata in modo semplice e a basso costo.</span><span class="sxs-lookup"><span data-stu-id="843cb-117">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="843cb-118">L'interfaccia utente semplifica l'analisi dei dati, in modo da poter dedicare tempo alla spigolatura dei dati, anziché a un'interfaccia goffa.</span><span class="sxs-lookup"><span data-stu-id="843cb-118">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="843cb-119">Supporta un'ampia gamma di input, in modo che l'applicazione distribuita si estenda su più tipi di servizi, ma è possibile prevedere di continuare a inserire dati di log e metriche nel sistema.</span><span class="sxs-lookup"><span data-stu-id="843cb-119">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="843cb-120">Elastic stack supporta inoltre le ricerche rapide anche nei set di dati di grandi dimensioni, rendendo possibile anche per le applicazioni di grandi dimensioni registrare dati dettagliati e comunque essere in grado di renderli visibili in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="843cb-120">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="843cb-121">Logstash</span><span class="sxs-lookup"><span data-stu-id="843cb-121">Logstash</span></span>

<span data-ttu-id="843cb-122">Il primo componente è [logstash](https://www.elastic.co/products/logstash).</span><span class="sxs-lookup"><span data-stu-id="843cb-122">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="843cb-123">Questo strumento viene usato per raccogliere informazioni di log da un'ampia gamma di origini diverse.</span><span class="sxs-lookup"><span data-stu-id="843cb-123">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="843cb-124">Ad esempio, logstash può leggere i log dal disco e ricevere anche messaggi dalle librerie di registrazione come [Serilog](https://serilog.net/).</span><span class="sxs-lookup"><span data-stu-id="843cb-124">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="843cb-125">Logstash è in grado di eseguire operazioni di filtro e espansione di base nei log Man mano che arrivano.</span><span class="sxs-lookup"><span data-stu-id="843cb-125">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="843cb-126">Se, ad esempio, i log contengono indirizzi IP, è possibile configurare logstash per eseguire una ricerca geografica e ottenere un paese o anche una città di origine per quel messaggio.</span><span class="sxs-lookup"><span data-stu-id="843cb-126">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="843cb-127">Serilog è una libreria di registrazione per i linguaggi .NET, che consente la registrazione con parametri.</span><span class="sxs-lookup"><span data-stu-id="843cb-127">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="843cb-128">Anziché generare un messaggio di log testuale che incorpora campi, i parametri vengono mantenuti separati.</span><span class="sxs-lookup"><span data-stu-id="843cb-128">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="843cb-129">Questo consente un filtro e una ricerca più intelligenti.</span><span class="sxs-lookup"><span data-stu-id="843cb-129">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="843cb-130">Nella figura 7-7 viene visualizzata una configurazione Serilog di esempio per la scrittura in logstash.</span><span class="sxs-lookup"><span data-stu-id="843cb-130">A sample Serilog configuration for writing to Logstash appears in Figure 7-7.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="843cb-131">**Figura 7-7**.</span><span class="sxs-lookup"><span data-stu-id="843cb-131">**Figure 7-7**.</span></span> <span data-ttu-id="843cb-132">Configurazione di Serilog per la scrittura di informazioni di log direttamente in logstash su HTTP</span><span class="sxs-lookup"><span data-stu-id="843cb-132">Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="843cb-133">Logstash utilizzerebbe una configurazione come quella illustrata nella figura 7-8.</span><span class="sxs-lookup"><span data-stu-id="843cb-133">Logstash would use a configuration like the one shown in Figure 7-8.</span></span>

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

<span data-ttu-id="843cb-134">**Figura 7-8**.</span><span class="sxs-lookup"><span data-stu-id="843cb-134">**Figure 7-8**.</span></span> <span data-ttu-id="843cb-135">Una configurazione logstash per l'utilizzo di log da Serilog</span><span class="sxs-lookup"><span data-stu-id="843cb-135">A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="843cb-136">Per gli scenari in cui non è necessaria una manipolazione estesa dei log, esiste un'alternativa a logstash noto come [Beats](https://www.elastic.co/products/beats).</span><span class="sxs-lookup"><span data-stu-id="843cb-136">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="843cb-137">Beats è una famiglia di strumenti che consente di raccogliere un'ampia gamma di dati dai log ai dati di rete e alle informazioni di tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="843cb-137">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="843cb-138">Molte applicazioni utilizzeranno sia logstash che Beats.</span><span class="sxs-lookup"><span data-stu-id="843cb-138">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="843cb-139">Una volta che i log sono stati raccolti da logstash, è necessario un punto in cui inserirli.</span><span class="sxs-lookup"><span data-stu-id="843cb-139">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="843cb-140">Sebbene logstash supporti molti output diversi, uno dei più interessanti è la ricerca elastica.</span><span class="sxs-lookup"><span data-stu-id="843cb-140">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="843cb-141">Ricerca elastica</span><span class="sxs-lookup"><span data-stu-id="843cb-141">Elastic search</span></span>

<span data-ttu-id="843cb-142">La ricerca elastica è un motore di ricerca potente che può indicizzare i log Man mano che arrivano.</span><span class="sxs-lookup"><span data-stu-id="843cb-142">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="843cb-143">Consente di eseguire rapidamente query sui log.</span><span class="sxs-lookup"><span data-stu-id="843cb-143">It makes running queries against the logs quick.</span></span> <span data-ttu-id="843cb-144">La ricerca elastica può gestire grandi quantità di log e, in casi estremi, può essere scalato orizzontalmente in più nodi.</span><span class="sxs-lookup"><span data-stu-id="843cb-144">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="843cb-145">I messaggi di log che sono stati creati per contenere parametri o i cui parametri sono stati divisi tramite l'elaborazione di logstash, possono essere sottoposti a query direttamente perché elasticsearch conserva queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="843cb-145">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="843cb-146">Una query che cerca le prime 10 pagine visitate da `jill@example.com` viene visualizzata nella figura 7-9.</span><span class="sxs-lookup"><span data-stu-id="843cb-146">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-9.</span></span>

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

<span data-ttu-id="843cb-147">**Figura 7-9**.</span><span class="sxs-lookup"><span data-stu-id="843cb-147">**Figure 7-9**.</span></span> <span data-ttu-id="843cb-148">Una query elasticsearch per trovare le prime 10 pagine visitate da un utente</span><span class="sxs-lookup"><span data-stu-id="843cb-148">An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="843cb-149">Visualizzazione di informazioni con i dashboard Web di Kibana</span><span class="sxs-lookup"><span data-stu-id="843cb-149">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="843cb-150">Il componente finale dello stack è Kibana.</span><span class="sxs-lookup"><span data-stu-id="843cb-150">The final component of the stack is Kibana.</span></span> <span data-ttu-id="843cb-151">Questo strumento viene usato per fornire visualizzazioni interattive in un dashboard Web.</span><span class="sxs-lookup"><span data-stu-id="843cb-151">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="843cb-152">I dashboard possono essere creati anche dagli utenti non tecnici.</span><span class="sxs-lookup"><span data-stu-id="843cb-152">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="843cb-153">La maggior parte dei dati residenti nell'indice elasticsearch può essere inclusa nei dashboard di Kibana.</span><span class="sxs-lookup"><span data-stu-id="843cb-153">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="843cb-154">I singoli utenti possono avere desideri diversi per i dashboard e Kibana consente questa personalizzazione attraverso la possibilità di dashboard specifici dell'utente.</span><span class="sxs-lookup"><span data-stu-id="843cb-154">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="843cb-155">Installazione di Elastic stack in Azure</span><span class="sxs-lookup"><span data-stu-id="843cb-155">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="843cb-156">Lo stack elastico può essere installato in Azure in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="843cb-156">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="843cb-157">Come sempre, è possibile eseguire [il provisioning di macchine virtuali e installare Elastic stack direttamente su di essi](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span><span class="sxs-lookup"><span data-stu-id="843cb-157">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="843cb-158">Questa opzione è preferibile ad alcuni utenti esperti perché offre il massimo grado di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="843cb-158">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="843cb-159">La distribuzione nell'infrastruttura come servizio introduce un sovraccarico di gestione significativo che impone a coloro che prendono tale percorso di assumere la proprietà di tutte le attività associate all'infrastruttura come servizio, ad esempio la protezione dei computer e la conservazione delle patch.</span><span class="sxs-lookup"><span data-stu-id="843cb-159">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="843cb-160">Un'opzione con un sovraccarico minore consiste nell'usare uno dei molti contenitori Docker in cui è già stato configurato lo stack elastico.</span><span class="sxs-lookup"><span data-stu-id="843cb-160">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="843cb-161">Questi contenitori possono essere rilasciati in un cluster Kubernetes esistente ed eseguiti insieme al codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="843cb-161">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="843cb-162">Il contenitore [sebp/Elk](https://elk-docker.readthedocs.io/) è un contenitore di stack elastico ben documentato e testato.</span><span class="sxs-lookup"><span data-stu-id="843cb-162">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="843cb-163">Un'altra opzione è una nuova [offerta di Elk come servizio annunciata di recente](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span><span class="sxs-lookup"><span data-stu-id="843cb-163">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="843cb-164">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="843cb-164">References</span></span>

- [<span data-ttu-id="843cb-165">Installare Elastic stack in Azure</span><span class="sxs-lookup"><span data-stu-id="843cb-165">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="843cb-166">[Precedente](observability-patterns.md) 
> [Avanti](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="843cb-166">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
