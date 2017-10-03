---
title: Migrazione di applicazioni monolitiche .NET Framework legacy nei contenitori di Windows
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Migrazione di applicazioni monolitiche .NET Framework legacy nei contenitori di Windows
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 1756ff0f49d9bb243fa561ba760418eba79de1f0
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="migrating-legacy-monolithic-net-framework-applications-to-windows-containers"></a>Migrazione di applicazioni monolitiche .NET Framework legacy nei contenitori di Windows

*I contenitori Windows possono essere usati per migliorare gli ambienti di sviluppo e test e per distribuire applicazioni basate su tecnologie .NET Framework legacy come i Web* *Form. Questa modalità di utilizzo dei contenitori per le applicazioni legacy viene definita scenario "lift-and-shift".*

Nelle sezioni precedenti di questa guida è stata illustrata un'architettura di microservizi in cui le applicazioni aziendali sono distribuite tra contenitori diversi, ognuno dei quali esegue un servizio limitato ma mirato. Tale obiettivo offre numerosi vantaggi. In un nuovo sviluppo questo approccio è fortemente consigliato. Anche le applicazioni aziendali critiche trarranno un vantaggio tale da giustificare il costo di una nuova architettura e di una reimplementazione.

Ma non tutte le applicazioni godranno di vantaggi sufficienti per giustificare il costo. Questo non vuol dire che tali applicazioni non possano essere usate in scenari basati su contenitori.

In questa sezione verrà presa in esame un'applicazione per eShopOnContainers, illustrata nella figura 7-1, che potrà essere usata dai membri del team aziendale di eShopOnContainers per visualizzare e modificare il catalogo dei prodotti.

![](./media/image1.png)

**Figura 7-1**. Applicazione Web Form ASP.NET (tecnologia legacy) in un contenitore Windows

Si tratta di un'applicazione Web Form usata per esplorare e modificare le voci di catalogo. La dipendenza da Web Form significa che questa applicazione non verrà eseguita in .NET Core a meno che non sia riscritta senza Web Form e usi invece ASP.NET Core MVC. Verrà spiegato come eseguire applicazioni come queste in contenitori senza modifiche. Si comprenderà inoltre come apportare modifiche minime al lavoro in una modalità ibrida in cui alcune funzionalità sono state spostate in un microservizio separato, mentre la maggior parte di esse rimane nell'applicazione monolitica.

## <a name="benefits-of-containerizing-a-monolithic-application"></a>Vantaggi dell'inserimento di un'applicazione monolitica in un contenitore

L'applicazione Catalog.WebForms è disponibile nel repository GitHub eShopOnContainers (<https://github.com/dotnet/eShopOnContainers>). Questa applicazione è un'applicazione Web autonoma che accede a un archivio dati a disponibilità elevata. Anche in questo caso l'esecuzione dell'applicazione in un contenitore presenta alcuni vantaggi. Viene creata un'immagine per l'applicazione. Da quel punto in avanti, ogni distribuzione viene eseguita nello stesso ambiente. Ogni contenitore usa la stessa versione del sistema operativo, ha la stessa versione di dipendenze installata, usa lo stesso framework ed è compilato con lo stesso processo. È possibile visualizzare l'applicazione caricata in Visual Studio 2017 nella figura 7-2.

![](./media/image2.png)

**Figura 7-2**. Applicazione Web Form per la gestione del catalogo in Visual Studio 2017

Inoltre, gli sviluppatori possono eseguire tutti l'applicazione in questo ambiente coerente. I problemi che si verificano solo con determinate versioni verranno riscontrati immediatamente dagli sviluppatori, anziché emergere in un ambiente di gestione temporanea o di produzione. Le differenze tra gli ambienti di sviluppo all'interno del team di sviluppo sono meno rilevanti quando le applicazioni sono eseguite in contenitori.

Infine, per le applicazioni incluse in contenitori la curva di scalabilità orizzontale si appiattisce. Si è appreso in che modo le app incluse in contenitori abilitino più contenitori in una macchina virtuale o più contenitori in un computer fisico. Questo si traduce in maggiore densità e meno risorse richieste.

Per tutti questi motivi, prendere in considerazione l'esecuzione di app monolitiche legacy in un contenitore Docker usando un'operazione di "lift-and-shift". L'espressione "lift-and-shift" descrive l'ambito dell'attività: si *solleva* l'intera applicazione da un computer fisico o da una macchina virtuale e la si *sposta* in un contenitore. In situazioni ideali non è necessario apportare modifiche al codice dell'applicazione per eseguirla in un contenitore.

## <a name="possible-migration-paths"></a>Percorsi di migrazione possibili

Come applicazione monolitica, l'applicazione Catalog.Webforms è un'applicazione Web contenente tutto il codice, incluse le librerie di accesso ai dati. Il database viene eseguito in un computer a disponibilità elevata distinto. Tale configurazione viene simulata nel codice di esempio tramite un servizio catalogo fittizio: è possibile eseguire l'applicazione Catalog.WebForms in base a tali dati falsi per simulare uno scenario lift-and-shift puro. Ciò dimostra il percorso di migrazione più semplice, in cui le risorse esistenti vengono spostate per l'esecuzione in un contenitore senza alcuna modifica al codice. Questo percorso è appropriato per le applicazioni complete che hanno un'interazione minima con le funzionalità che si spostano nei microservizi.

Tuttavia, il sito Web eShopOnContainers accede già all'archivio dati usando i microservizi per scenari diversi. È possibile apportare alcune piccole modifiche aggiuntive all'editor del catalogo per sfruttare il microservizio catalogo anziché accedere direttamente all'archivio dati del catalogo.

Queste modifiche dimostrano la continuità per le applicazioni in uso. È possibile eseguire qualsiasi operazione, dallo spostamento di un'applicazione esistente senza modifiche nei contenitori, all'attuazione di piccole modifiche che consentono alle applicazioni esistenti di accedere ad alcuni dei nuovi microservizi, fino alla riscrittura completa di un'applicazione per partecipare pienamente in una nuova architettura basata su microservizi. Il percorso più adeguato dipende sia dal costo della migrazione che dai vantaggi di qualsiasi migrazione.

## <a name="application-tour"></a>Presentazione dell'applicazione

È possibile caricare la soluzione Catalog.WebForms ed eseguire l'applicazione come applicazione autonoma. In questa configurazione, invece di un database dell'archivio permanente, l'applicazione usa un servizio fittizio per restituire i dati. L'applicazione usa Autofac (<https://autofac.org/>) come un'inversione del contenitore del controllo (IOC). Tramite l'inserimento delle dipendenze, è possibile configurare l'applicazione in modo da usare i dati falsi o il servizio dati del catalogo in tempo reale (a breve verranno forniti ulteriori dettagli sull'inserimento delle dipendenze). Il codice di avvio legge un'impostazione useFake dai file web.config e configura il contenitore Autofac per inserire il servizio dati fittizio o il servizio catalogo in tempo reale. Se si esegue l'applicazione con useFake impostato su false nel file web.config, verrà visualizzata l'applicazione Web Form con i dati del catalogo.

La maggior parte delle tecniche usate in questa applicazione dovrebbe risultare estremamente familiare per chiunque abbia usato i Web Form. Tuttavia, il microservizio catalogo introduce due tecniche che potrebbero essere meno note: l'inserimento delle dipendenze, menzionato in precedenza, e l'uso di archivi dati asincroni nei Web Form.

L'inserimento delle dipendenze inverte la strategia orientata a oggetti tipica della scrittura di classi che allocano tutte le risorse necessarie. Al contrario, le classi richiedono le relative dipendenze da un contenitore del servizio. Il vantaggio dell'inserimento delle dipendenze consiste nella possibilità di sostituire i servizi esterni con oggetti fittizi (simulazioni) per supportare ambienti di test o di altro tipo.

Il contenitore di inserimento delle dipendenze usa la configurazione appSettings di web.config per controllare se usare i dati del catalogo fittizio o i dati in tempo reale dal servizio in esecuzione. L'applicazione registra un oggetto HttpModule che crea il contenitore e registra un gestore di pre-richiesta per l'inserimento delle dipendenze. Tale codice può essere visualizzato nel file Modules/AutoFacHttpModule.cs, che presenta un aspetto analogo al seguente:

```cs
private static IContainer CreateContainer()
{
  // Configure AutoFac:
  // Register Containers:

  var settings = WebConfigurationManager.AppSettings;
  var useFake = settings["usefake"];
  bool fake = useFake == "true";
  var builder = new ContainerBuilder();

  if (fake)
  {
    builder.RegisterType<CatalogMockService>()
    .As<ICatalogService>();
  }
  else
  {
    builder.RegisterType<CatalogService>()
    .As<ICatalogService>();
    builder.RegisterType<RequestProvider>()
    .As<IRequestProvider>();
  }

  var container = builder.Build();
  return container;
}

private void InjectDependencies()
{
  if (HttpContext.Current.CurrentHandler is Page page)
  {
    // Get the code-behind class that we may have written
    var pageType = page.GetType().BaseType;

    // Determine if there is a constructor to inject, and grab it
    var ctor = (from c in pageType.GetConstructors()
                where c.GetParameters().Length > 0
                select c).FirstOrDefault();

    if (ctor != null)
    {
      // Resolve the parameters for the constructor
      var args = (from parm in ctor.GetParameters()
                  select Container.Resolve(parm.ParameterType))
                  .ToArray();

      // Execute the constructor method with the arguments resolved
      ctor.Invoke(page, args);
    }

    // Use the Autofac method to inject any
    // properties that can be filled by Autofac
    Container.InjectProperties(page);
  }
}
```

Le pagine dell'applicazione (Default.aspx.cs e EditPage.aspx.cs) definiscono costruttori che accettano queste dipendenze. Il costruttore predefinito è ancora presente e accessibile. L'infrastruttura necessita del codice seguente.

```cs
protected _Default() { }

public _Default(ICatalogService catalog) => this.catalog = catalog;
```

Le API del catalogo sono tutte metodi asincroni. I Web Form ora le supportano per tutti i controlli dati. L'applicazione Catalog.WebForms usa l'associazione di modelli per le pagine di elenco e modifica; i controlli nelle pagine definiscono le proprietà SelectMethod, UpdateMethod, InsertMethod e DeleteMethod che specificano le operazioni asincrone che restituiscono un'attività. I controlli Web Form comprendono quando i metodi associati a un controllo sono asincroni. L'unica limitazione che si riscontra quando si usano metodi di selezione asincroni è che non è possibile supportare il paging. La firma di paging richiede un parametro out e i metodi asincroni non possono avere parametri out. Questa stessa tecnica viene usata in altre pagine che richiedono dati dal servizio catalogo.

La configurazione predefinita per l'applicazione Web Form del catalogo usa un'implementazione fittizia del servizio catalog.api. Questa simulazione usa un set di dati hardcoded per i dati, che consente di semplificare alcune attività rimuovendo la dipendenza dal servizio catalog.api negli ambienti di sviluppo.

## <a name="lifting-and-shifting"></a>Lift-and-shift

Visual Studio garantisce un supporto ottimale per l'inserimento di un'applicazione nei contenitori. Fare clic con il pulsante destro del mouse sul nodo di progetto e quindi selezionare **Aggiungi** e **Supporto Docker**. Il modello di progetto Docker aggiunge un nuovo progetto alla soluzione denominata **docker-compose**. Il progetto contiene le risorse Docker che compongono (o compilano) le immagini necessarie e viene avviato eseguendo i contenitori necessari, come illustrato nella figura 7-3.

Negli scenari lift-and-shift più semplici l'applicazione sarà il servizio singolo usato per l'applicazione Web Form. Il modello modifica anche il progetto di avvio in modo che punti al progetto **docker-compose**. Premendo CTRL+F5 o F5, verrà creata l'immagine Docker e sarà avviato il contenitore Docker.

![](./media/image3.png)

**Figura 7-3**. Progetto **docker-compose** nella soluzione Web Form

Prima di eseguire la soluzione, è necessario assicurarsi di configurare Docker per l'uso dei contenitori Windows. A tale scopo, fare clic con il pulsante destro del mouse sull'icona Docker della barra delle applicazioni in Windows e selezionare **Switch to Windows Containers** (Passa ai contenitori Windows), come illustrato nella figura 7-4.

![](./media/image4.png)

**Figura 7-4**. Passaggio ai contenitori Windows dall'icona Docker della barra delle applicazioni in Windows

Se la voce di menu visualizzata è **Switch to Linux containers** (Passa ai contenitori Linux), Docker è già in esecuzione con i contenitori Windows.

L'esecuzione della soluzione riavvia l'host Docker. Durante la compilazione, vengono compilate l'applicazione e l'immagine Docker per il progetto Web Form. La prima volta che si esegue questa operazione, è richiesto molto tempo. Ciò accade perché il processo di compilazione estrae l'immagine base di Windows Server e l'immagine aggiuntiva per ASP.NET. I cicli di compilazione ed esecuzione successivi saranno molto più veloci.

Verranno ora esaminati in maniera più approfondita i file aggiunti dal modello di progetto Docker. Diversi file sono stati creati automaticamente. Visual Studio usa questi file per creare l'immagine Docker e avviare un contenitore. È possibile usare gli stessi file dall'interfaccia della riga di comando per eseguire manualmente i comandi di Docker.

L'esempio di Dockerfile seguente mostra le impostazioni di base per la compilazione di un'immagine Docker basata sull'immagine Windows ASP.NET che esegue un sito ASP.NET.

```
FROM microsoft/aspnet

ARG source

WORKDIR /inetpub/wwwroot

COPY ${source:-obj/Docker/publish} .
```

Questo Dockerfile avrà un aspetto molto simile ai file creati per l'esecuzione di un'applicazione ASP.NET Core nei contenitori Linux. Esistono tuttavia alcune importanti differenze. La differenza più rilevante è che l'immagine di base è microsoft/aspnet, ovvero l'immagine corrente di Windows Server che include .NET Framework. Altre differenze sono che le directory copiate dalla directory di origine sono diverse.

Gli altri file nel progetto **docker-compose** sono le risorse Docker necessarie per compilare e configurare i contenitori. Visual Studio inserisce i vari file docker-compose.yml in un nodo per evidenziarne le modalità di utilizzo. Il file di base docker-compose contiene le direttive comuni a tutte le configurazioni. Il file docker-compose.override.yml contiene le variabili di ambiente e gli override correlati per una configurazione per sviluppatori. Le varianti con .vs.debug e .vs.release forniscono le impostazioni dell'ambiente che consentono a Visual Studio di connettersi al contenitore in esecuzione e gestirlo.

Mentre l'integrazione con Visual Studio rientra nell'aggiunta del supporto per Docker alla soluzione in uso, è anche possibile compilare ed eseguire dalla riga di comando usando il comando docker-compose up, come illustrato nelle sezioni precedenti.

## <a name="getting-data-from-the-existing-catalog-net-core-microservice"></a>Recupero di dati dal microservizio .NET Core del catalogo esistente

È possibile configurare l'applicazione Web Form in modo da usare il microservizio catalogo eShopOnContainers per recuperare i dati anziché usare dati falsi. A tale scopo, è necessario modificare il file web.config e impostare il valore della chiave useFake su false. Il contenitore di inserimento delle dipendenze userà la classe che accede al microservizio catalogo in tempo reale invece di quella che restituisce i dati hardcoded. Non sono necessarie altre modifiche al codice.

L'accesso al servizio catalogo in tempo reale implica la necessità di aggiornare il progetto **docker-compose** per compilare l'immagine del servizio catalogo e avviare il contenitore del servizio catalogo. Docker CE per Windows supporta sia i contenitori Linux che quelli Windows, ma non contemporaneamente. Per eseguire il microservizio catalogo, è necessario compilare un'immagine per l'esecuzione del microservizio catalogo sulla base di un contenitore Windows. Questo approccio richiede un Dockerfile diverso per il progetto dei microservizi che è stato illustrato nelle sezioni precedenti. Il file Dockerfile.windows contiene le impostazioni di configurazione per creare l'immagine del contenitore dell'API del catalogo in modo che l'esecuzione sia basata su un contenitore Windows, ad esempio per usare un'immagine Docker Windows Nano.

Il microservizio catalogo si basa sul database di SQL Server. Pertanto, è necessario usare anche un'immagine Docker di SQL Server basata su Windows.

Dopo che sono state apportate queste modifiche, il progetto docker-compose non si limita ad avviare l'applicazione. Il progetto avvia ora SQL Server usando l'immagine di SQL Server basata su Windows. Avvia il microservizio catalogo in un contenitore Windows. E avvia il contenitore dell'editor del catalogo Web Form, anch'esso in un contenitore Windows. Se necessario, per prima cosa vengono create le immagini.

## <a name="development-and-production-environments"></a>Ambienti di sviluppo e produzione

Esistono alcune differenze tra una configurazione di sviluppo e una di produzione. Nell'ambiente di sviluppo si esegue l'applicazione Web Form, il microservizio catalogo e SQL Server in contenitori Windows, nell'ambito dello stesso host Docker. Nelle sezioni precedenti sono state menzionate le immagini di SQL Server distribuite nello stesso host Docker come gli altri servizi basati su .NET Core in un host Docker basato su Linux. Il vantaggio di eseguire più microservizi nello stesso host Docker (o cluster) è che la comunicazione di rete è inferiore e la comunicazione tra i contenitori ha una latenza più bassa.

Nell'ambiente di sviluppo è necessario eseguire tutti i contenitori nello stesso sistema operativo. Docker CE per Windows non supporta l'esecuzione di contenitori basati su Windows e Linux contemporaneamente. In produzione è possibile decidere se si vuole eseguire il microservizio catalogo in un contenitore Windows in un singolo host Docker (o cluster) o fare in modo che l'applicazione Web Form comunichi con un'istanza del microservizio catalogo in esecuzione in un contenitore Linux in un altro host Docker. Dipende dalla modalità di ottimizzazione prescelta per la latenza di rete. Nella maggior parte dei casi si specifica che i microservizi da cui dipendono le applicazioni siano eseguiti nello stesso host Docker (o swarm) per una maggiore facilità di distribuzione e una minore latenza di comunicazione. In tali configurazioni le uniche comunicazioni costose sono quelle tra le istanze del microservizio e i server a disponibilità elevata per l'archivio dati permanente.

>[!div class="step-by-step"]
[Precedente] (../net-core-single-containers-linux-windows-server-hosts/index.md) [Successivo] (../multi-container-microservice-net-applications/index.md)

