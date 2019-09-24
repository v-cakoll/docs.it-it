---
title: Registrazione con Elastic stack
description: Registrazione con Elastic stack, logstash e Kibana
ms.date: 09/23/2019
ms.openlocfilehash: b3fd3ea30f46914e6513be79f7d949499142b381
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182832"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="43846-103">Registrazione con Elastic stack</span><span class="sxs-lookup"><span data-stu-id="43846-103">Logging with Elastic Stack</span></span> 

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="43846-104">Sono disponibili molti strumenti di registrazione centralizzati e i costi variano a seconda del fatto che siano disponibili strumenti Open Source gratuiti per le opzioni più costose.</span><span class="sxs-lookup"><span data-stu-id="43846-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="43846-105">In molti casi, gli strumenti gratuiti sono più efficaci o migliori delle offerte a pagamento.</span><span class="sxs-lookup"><span data-stu-id="43846-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="43846-106">Uno di questi strumenti è costituito da una combinazione di tre componenti Open Source: Ricerca elastica, logstash e Kibana.</span><span class="sxs-lookup"><span data-stu-id="43846-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span> <span data-ttu-id="43846-107">Collettivamente questi strumenti sono noti come stack elastico o ELK.</span><span class="sxs-lookup"><span data-stu-id="43846-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="43846-108">Quali sono i vantaggi di Elastic stack?</span><span class="sxs-lookup"><span data-stu-id="43846-108">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="43846-109">Elastic stack fornisce la registrazione centralizzata in modo semplice e a basso costo.</span><span class="sxs-lookup"><span data-stu-id="43846-109">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="43846-110">L'interfaccia utente semplifica l'analisi dei dati, in modo da poter dedicare tempo alla spigolatura dei dati, anziché a un'interfaccia goffa.</span><span class="sxs-lookup"><span data-stu-id="43846-110">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="43846-111">Supporta un'ampia gamma di input, in modo che l'applicazione distribuita si estenda su più tipi di servizi, ma è possibile prevedere di continuare a inserire dati di log e metriche nel sistema.</span><span class="sxs-lookup"><span data-stu-id="43846-111">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="43846-112">Elastic stack supporta inoltre le ricerche rapide anche nei set di dati di grandi dimensioni, consentendo alle applicazioni anche di grandi dimensioni di registrare dati dettagliati e comunque di potervi ottenere visibilità in modo efficiente.</span><span class="sxs-lookup"><span data-stu-id="43846-112">The Elastic Stack also supports fast searches even across large data sets, making it possible to for even large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="43846-113">Logstash</span><span class="sxs-lookup"><span data-stu-id="43846-113">Logstash</span></span>

<span data-ttu-id="43846-114">Il primo componente è [logstash](https://www.elastic.co/products/logstash).</span><span class="sxs-lookup"><span data-stu-id="43846-114">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="43846-115">Questo strumento viene usato per raccogliere informazioni di log da un'ampia gamma di origini diverse.</span><span class="sxs-lookup"><span data-stu-id="43846-115">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="43846-116">Ad esempio, logstash può leggere i log dal disco e ricevere anche messaggi dalle librerie di registrazione come [Serilog](https://serilog.net/).</span><span class="sxs-lookup"><span data-stu-id="43846-116">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="43846-117">Logstash è in grado di eseguire operazioni di filtro e espansione di base nei log Man mano che arrivano.</span><span class="sxs-lookup"><span data-stu-id="43846-117">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="43846-118">Se, ad esempio, i log contengono indirizzi IP, è possibile configurare logstash per eseguire una ricerca geografica e ottenere un paese o anche una città di origine per quel messaggio.</span><span class="sxs-lookup"><span data-stu-id="43846-118">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span> 

<span data-ttu-id="43846-119">Serilog è una libreria di registrazione per i linguaggi .NET, che consente la registrazione con parametri.</span><span class="sxs-lookup"><span data-stu-id="43846-119">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="43846-120">Anziché generare un messaggio di log testuale che incorpora campi, i parametri vengono mantenuti separati.</span><span class="sxs-lookup"><span data-stu-id="43846-120">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="43846-121">Questo consente un filtro e una ricerca più intelligenti.</span><span class="sxs-lookup"><span data-stu-id="43846-121">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="43846-122">Nella figura 7-2 viene visualizzata una configurazione Serilog di esempio per la scrittura in logstash.</span><span class="sxs-lookup"><span data-stu-id="43846-122">A sample Serilog configuration for writing to Logstash appears in Figure 7-2.</span></span>

```csharp
var log = new LoggerConfiguration()   
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="43846-123">**Figura 7-2** Configurazione di Serilog per la scrittura di informazioni di log direttamente in logstash su HTTP</span><span class="sxs-lookup"><span data-stu-id="43846-123">**Figure 7-2** Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="43846-124">Logstash utilizzerebbe una configurazione come quella illustrata nella figura 7-3.</span><span class="sxs-lookup"><span data-stu-id="43846-124">Logstash would use a configuration like the one shown in Figure 7-3.</span></span> 

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

<span data-ttu-id="43846-125">**Figura 7-3** -configurazione di logstash per l'utilizzo di log da Serilog</span><span class="sxs-lookup"><span data-stu-id="43846-125">**Figure 7-3** - A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="43846-126">Per gli scenari in cui non è necessaria una manipolazione estesa dei log, esiste un'alternativa a logstash noto come [Beats](https://www.elastic.co/products/beats).</span><span class="sxs-lookup"><span data-stu-id="43846-126">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="43846-127">Beats è una famiglia di strumenti che consente di raccogliere un'ampia gamma di dati dai log ai dati di rete e alle informazioni di tempo di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="43846-127">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="43846-128">Molte applicazioni utilizzeranno sia logstash che Beats.</span><span class="sxs-lookup"><span data-stu-id="43846-128">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="43846-129">Una volta che i log sono stati raccolti da logstash, è necessario un punto in cui inserirli.</span><span class="sxs-lookup"><span data-stu-id="43846-129">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="43846-130">Sebbene logstash supporti molti output diversi, uno dei più interessanti è la ricerca elastica.</span><span class="sxs-lookup"><span data-stu-id="43846-130">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="43846-131">Ricerca elastica</span><span class="sxs-lookup"><span data-stu-id="43846-131">Elastic search</span></span>

<span data-ttu-id="43846-132">La ricerca elastica è un motore di ricerca potente che può indicizzare i log Man mano che arrivano.</span><span class="sxs-lookup"><span data-stu-id="43846-132">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="43846-133">Consente di eseguire rapidamente query sui log.</span><span class="sxs-lookup"><span data-stu-id="43846-133">It makes running queries against the logs quick.</span></span> <span data-ttu-id="43846-134">La ricerca elastica può gestire grandi quantità di log e, in casi estremi, può essere scalato orizzontalmente in più nodi.</span><span class="sxs-lookup"><span data-stu-id="43846-134">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span> 

<span data-ttu-id="43846-135">I messaggi di log che sono stati creati per contenere parametri o i cui parametri sono stati divisi tramite l'elaborazione di logstash, possono essere sottoposti a query direttamente perché elasticsearch conserva queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="43846-135">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="43846-136">Una query che cerca le prime 10 pagine visitate da `jill@example.com`viene visualizzata nella figura 7-4.</span><span class="sxs-lookup"><span data-stu-id="43846-136">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-4.</span></span>

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

<span data-ttu-id="43846-137">**Figura 7-4** -query elasticsearch per trovare le prime 10 pagine visitate da un utente</span><span class="sxs-lookup"><span data-stu-id="43846-137">**Figure 7-4** - An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="43846-138">Visualizzazione di informazioni con i dashboard Web di Kibana</span><span class="sxs-lookup"><span data-stu-id="43846-138">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="43846-139">Il componente finale dello stack è Kibana.</span><span class="sxs-lookup"><span data-stu-id="43846-139">The final component of the stack is Kibana.</span></span> <span data-ttu-id="43846-140">Questo strumento viene usato per fornire visualizzazioni interattive in un dashboard Web.</span><span class="sxs-lookup"><span data-stu-id="43846-140">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="43846-141">I dashboard possono essere creati anche dagli utenti non tecnici.</span><span class="sxs-lookup"><span data-stu-id="43846-141">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="43846-142">La maggior parte dei dati residenti nell'indice elasticsearch può essere inclusa nei dashboard di Kibana.</span><span class="sxs-lookup"><span data-stu-id="43846-142">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="43846-143">I singoli utenti possono avere desideri diversi per i dashboard e Kibana consente questa personalizzazione attraverso la possibilità di dashboard specifici dell'utente.</span><span class="sxs-lookup"><span data-stu-id="43846-143">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span> 

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="43846-144">Installazione di Elastic stack in Azure</span><span class="sxs-lookup"><span data-stu-id="43846-144">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="43846-145">Lo stack elastico può essere installato in Azure in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="43846-145">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="43846-146">Come sempre, è possibile eseguire [il provisioning di macchine virtuali e installare Elastic stack direttamente su di essi](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span><span class="sxs-lookup"><span data-stu-id="43846-146">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="43846-147">Questa opzione è preferibile ad alcuni utenti esperti perché offre il massimo grado di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="43846-147">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="43846-148">La distribuzione nell'infrastruttura come servizio introduce un sovraccarico di gestione significativo che impone a coloro che prendono tale percorso di assumere la proprietà di tutte le attività associate all'infrastruttura come servizio, ad esempio la protezione dei computer e la conservazione delle patch.</span><span class="sxs-lookup"><span data-stu-id="43846-148">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span> 

<span data-ttu-id="43846-149">Un'opzione con un sovraccarico minore consiste nell'usare uno dei molti contenitori Docker in cui è già stato configurato lo stack elastico.</span><span class="sxs-lookup"><span data-stu-id="43846-149">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="43846-150">Questi contenitori possono essere rilasciati in un cluster Kubernetes esistente ed eseguiti insieme al codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43846-150">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="43846-151">Il contenitore [sebp/Elk](https://elk-docker.readthedocs.io/) è un contenitore di stack elastico ben documentato e testato.</span><span class="sxs-lookup"><span data-stu-id="43846-151">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="43846-152">Un'altra opzione è una nuova [offerta di Elk come servizio annunciata di recente](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span><span class="sxs-lookup"><span data-stu-id="43846-152">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="43846-153">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="43846-153">References</span></span>

- [<span data-ttu-id="43846-154">Installare Elastic stack in Azure</span><span class="sxs-lookup"><span data-stu-id="43846-154">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="43846-155">[Precedente](observability-patterns.md)
>[Successivo](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="43846-155">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>