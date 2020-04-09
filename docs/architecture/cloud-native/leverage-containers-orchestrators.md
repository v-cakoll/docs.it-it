---
title: Uso di contenitori e agenti di orchestrazione
description: Sfruttare i contenitori Docker e gli orchestratori Kubernetes in Azure
ms.date: 06/30/2019
ms.openlocfilehash: 44b2fff8c9c88717d83e41a421b9817e2cc68135
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989038"
---
# <a name="leveraging-containers-and-orchestrators"></a>Uso di contenitori e agenti di orchestrazione

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

I contenitori e gli agenti di orchestrazione sono progettati per risolvere problemi comuni agli approcci di distribuzione monolitici.

## <a name="challenges-with-monolithic-deployments"></a>Sfide con distribuzioni monolitiche

Tradizionalmente, la maggior parte delle applicazioni sono state distribuite come una singola unità. Tali applicazioni sono definite monolite. Questo approccio generale di distribuzione di applicazioni come unità singole anche se sono composti da più moduli o assembly è noto come architettura monolitica, come illustrato nella Figura 3-1.

![Architettura monolitica.](./media/monolithic-architecture.png)

**Figura 3-1**. Architettura monolitica.

Sebbene abbiano il vantaggio della semplicità, le architetture monolitiche devono affrontare una serie di sfide:

### <a name="deployments"></a>Deployments

La distribuzione in applicazioni monolitiche richiede in genere il riavvio dell'intera applicazione, anche se viene sostituito un solo piccolo modulo. A seconda del numero di computer che ospitano l'applicazione, ciò può causare tempi di inattività durante le distribuzioni.

### <a name="hosting"></a>Hosting

Le applicazioni monolitiche sono ospitate interamente in una singola istanza del computer. Ciò potrebbe richiedere hardware con capacità superiore a quella necessaria per qualsiasi modulo in un'applicazione distribuita. Inoltre, se una parte qualsiasi dell'app diventa un collo di bottiglia, l'intera applicazione deve essere distribuita in nodi del computer aggiuntivi per poter eseguire la scalabilità orizzontale.

### <a name="environment"></a>Environment

Le applicazioni monolitiche vengono in genere distribuite in un ambiente di hosting esistente (sistema operativo, framework installati e così via). Questo ambiente potrebbe non corrispondere all'ambiente in cui l'applicazione è stata sviluppata o testata. Le incoerenze nell'ambiente dell'applicazione sono una fonte comune di problemi per le distribuzioni monolitiche.

### <a name="coupling"></a>Accoppiamento

È probabile che le applicazioni monolitiche abbiano una grande quantità di accoppiamento tra le diverse parti dell'applicazione e tra l'applicazione e il suo ambiente. Questo può rendere difficile fattorizzare un particolare servizio o preoccupazione in un secondo momento, al fine di aumentare la scalabilità o swap in un'implementazione alternativa. Questo accoppiamento porta anche a impatti potenziali molto più grandi per le modifiche al sistema, che richiedono test approfonditi in applicazioni più grandi.

### <a name="technology-choice"></a>Scelta tecnologica

Le applicazioni monolitiche vengono create e distribuite come unità. Questo offre semplicità e uniformità, ma può essere un ostacolo all'innovazione. Anche se una nuova funzionalità o modulo nel sistema potrebbe essere più adatto a una piattaforma o un framework più moderno, è probabile che venga compilato utilizzando l'approccio corrente dell'applicazione per motivi di coerenza, nonché per facilità di sviluppo e distribuzione.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>Quali sono i vantaggi di contenitori e agenti di orchestrazione?

Docker è la piattaforma di gestione e imaging dei contenitori più popolare e consente di lavorare rapidamente con i contenitori su Linux e Windows. I contenitori forniscono ambienti applicativi separati ma riproducibili che vengono eseguiti allo stesso modo in qualsiasi sistema. Questo li rende perfetti per lo sviluppo e l'hosting di applicazioni e componenti di app in applicazioni native cloud. I contenitori sono isolati l'uno dall'altro, pertanto due contenitori nello stesso hardware host possono avere versioni diverse del software e persino del sistema operativo installato, senza che le dipendenze causino conflitti.

Inoltre, i contenitori sono definiti da file semplici che possono essere archiviati nel controllo del codice sorgente. A differenza dei server completi, anche delle macchine virtuali, che spesso richiedono il lavoro manuale per applicare gli aggiornamenti o installare servizi aggiuntivi, l'infrastruttura contenitore può essere facilmente controllata dalla versione. Di conseguenza, le app create per essere eseguite in contenitori possono essere sviluppate, testate e distribuite usando strumenti automatizzati come parte di una pipeline di compilazione.

I contenitori non sono modificabili. Una volta che si dispone della definizione di un contenitore, è possibile ricreare tale contenitore e verrà eseguito esattamente nello stesso modo. Questa immutabilità si presta alla progettazione basata su componenti. Se alcune parti di un'applicazione non cambiano con la stessa frequenza di altre, perché ridistribuire l'intera app quando è possibile distribuire le parti che cambiano più frequentemente? Diverse caratteristiche e problemi trasversali di un'app possono essere suddivisi in unità separate. Nella figura 3-2 viene illustrato come un'app monolitica può sfruttare i vantaggi di contenitori e microservizi delegando determinate funzionalità o funzionalità. Anche la funzionalità rimanente nell'app stessa è stata inclusa in contenitore.

![Suddivisione di un'app monolitica per l'utilizzo di microservizi nel back-end. ](./media/breaking-up-monolith-with-backend-microservices.png)
 **Figura 3-2**. Suddivisione di un'app monolitica per l'utilizzo di microservizi nel back-end.

Le app native basate sul cloud create usando contenitori separati traggono vantaggio dalla possibilità di distribuire la durata di un'applicazione pari o piccola a quella necessaria. I singoli servizi possono essere ospitati in nodi con risorse appropriate per ogni servizio. L'ambiente in cui viene eseguito ogni servizio non è modificabile, può essere condiviso tra sviluppo, test e produzione e può essere facilmente sottoposto a controllo delle versioni. L'accoppiamento tra aree diverse dell'applicazione si verifica in modo esplicito come chiamate o messaggi tra servizi, non come dipendenze in fase di compilazione all'interno del monolite. E qualsiasi parte dell'app complessiva può scegliere la tecnologia che ha più senso per quella funzionalità o funzionalità senza richiedere modifiche al resto dell'app.

## <a name="what-are-the-scaling-benefits"></a>Quali sono i vantaggi della scalabilità?

I servizi basati su contenitori possono sfruttare i vantaggi di scalabilità forniti da strumenti di orchestrazione come Kubernetes.Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes. Con contenitori di progettazione solo conoscere se stessi. Una volta che si inizia ad avere più contenitori che devono lavorare insieme, può essere utile organizzarli a un livello superiore. Organizzare un numero elevato di contenitori e le relative dipendenze condivise, ad esempio la configurazione di rete, è il punto in cui gli strumenti di orchestrazione consentono di salvare la giornata. Kubernetes è una piattaforma di orchestrazione di contenitori progettata per automatizzare la distribuzione, la scalabilità e la gestione di applicazioni containerizzate. Crea un livello di astrazione sopra gruppi di contenitori e li organizza in *pod*. I pod vengono eseguiti su computer worker denominati *nodi*. L'intero gruppo organizzato viene definito *cluster*. La figura 3-3 mostra i diversi componenti di un cluster Kubernetes.

![Kubernetes componenti cluster. ](./media/kubernetes-cluster-components.png)
 **Figura 3-3**. Kubernetes componenti cluster.

Kubernetes dispone di supporto integrato per la scalabilità dei cluster per soddisfare la domanda. In combinazione con microservizi containerizzati, questo fornisce applicazioni native cloud con la possibilità di rispondere in modo rapido ed efficiente ai picchi di domanda con risorse aggiuntive quando e dove sono necessarie.

### <a name="declarative-versus-imperative"></a>Dichiarativo e imperativo

Kubernetes supporta sia la configurazione dichiarativa che la configurazione imperativa degli oggetti. L'approccio imperativo prevede l'esecuzione di vari comandi che indicano a Kubernetes cosa fare ogni passaggio del percorso. *Eseguire* questa immagine. *Elimina* questo contenitore. *Esporre* questa porta. Con l'approccio dichiarativo, si utilizza un file di configurazione che descrive *ciò* che si desidera invece di *cosa fare* e Kubernetes capisce cosa fare per raggiungere lo stato finale desiderato. Se il cluster è già stato configurato utilizzando comandi imperativi, `kubectl get svc SERVICENAME -o yaml > service.yaml`è possibile esportare un manifesto dichiarativo utilizzando . Verrà prodotto un file manifesto come questo:

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: "2019-09-13T13:58:47Z"
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "153"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 9b1fac62-d62e-11e9-8968-00155d38010d
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 6443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

Quando si utilizza la configurazione dichiarativa, è possibile visualizzare `kubectl diff -f FOLDERNAME` in anteprima le modifiche che verranno apportate prima di eseguirne il commit utilizzando la cartella in cui si trovano i file di configurazione. Una volta che si è sicuri di `kubectl apply -f FOLDERNAME`voler applicare le modifiche, eseguire . Aggiungere `-R` per elaborare in modo ricorsivo una gerarchia di cartelle.

Oltre ai servizi, è possibile utilizzare la configurazione dichiarativa per altre funzionalità di Kubernetes, ad esempio *le distribuzioni*. Le distribuzioni dichiarative vengono utilizzate dai controller di distribuzione per aggiornare le risorse del cluster. Le distribuzioni vengono usate per implementare nuove modifiche, aumentare le dimensioni per supportare un carico maggiore o eseguire il rollback a una revisione precedente. Se un cluster è instabile, le distribuzioni dichiarative forniscono un meccanismo per riportare automaticamente il cluster allo stato desiderato.

L'utilizzo della configurazione dichiarativa consente all'infrastruttura di essere rappresentata come codice che può essere archiviato e sottoposto a controllo delle versioni insieme al codice dell'applicazione. Ciò fornisce un migliore controllo delle modifiche e un migliore supporto per la distribuzione continua utilizzando una pipeline di compilazione e distribuzione legata alle modifiche del controllo del codice sorgente.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>Quali scenari sono ideali per contenitori e agenti di orchestrazione?

Gli scenari seguenti sono ideali per l'utilizzo di contenitori e agenti di orchestrazione.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Applicazioni che richiedono tempi di attività e scalabilità elevati

Le singole applicazioni con tempi di attività elevati e requisiti di scalabilità sono candidati ideali per architetture native cloud che utilizzano microservizi, contenitori e agenti di orchestrazione. Queste applicazioni possono essere sviluppate in contenitori utilizzando ambienti con controllo delle versioni, possono essere ampiamente testate prima di passare alla produzione e possono essere distribuite nell'ambiente di produzione senza tempi di inattività. L'uso dei cluster Kubernetes garantisce che tali app possano anche essere ridimensionate su richiesta e ripristinate automaticamente dagli errori dei nodi.

### <a name="large-numbers-of-applications"></a>Un gran numero di applicazioni

Le organizzazioni che distribuiscono e devono successivamente gestire un numero elevato di applicazioni traggono vantaggio da contenitori e agenti di orchestrazione. Lo sforzo iniziale di configurare ambienti containerizzati e cluster Kubernetes è principalmente un costo fisso. La distribuzione, la gestione e l'aggiornamento di singole applicazioni comportano un costo che varia in base al numero di applicazioni da gestire. Oltre a un certo numero di applicazioni piuttosto ridotto, la complessità della gestione manuale delle applicazioni personalizzate supera il costo dell'implementazione di una soluzione utilizzando contenitori e agenti di orchestrazione.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>Quando è consigliabile evitare l'utilizzo di contenitori e agenti di orchestrazione?

Se non si è disposti o non è in grado di compilare l'applicazione seguendo i principi dell'app a dodici fattori, è probabile che sia preferibile evitare contenitori e agenti di orchestrazione. In questi casi, potrebbe essere meglio andare avanti con una piattaforma di hosting basata su macchine virtuali o forse con un sistema ibrido in cui è possibile eseguire lo spin-off di determinate funzionalità in contenitori separati o anche funzioni senza server.

## <a name="development-resources"></a>Risorse per lo sviluppo

In questa sezione viene illustrato un breve elenco di risorse di sviluppo che consentono di iniziare a usare contenitori e agenti di orchestrazione per l'applicazione successiva. Per indicazioni su come progettare l'app di architettura dei microservizi nativa del cloud, leggere il servizio complementare di questo libro, [.NET Microservices: Architecture for Containerized Applications](https://aka.ms/microservicesebook).

### <a name="local-kubernetes-development"></a>Sviluppo Kubernetes locale

Le distribuzioni Kubernetes offrono un grande valore negli ambienti di produzione, ma è anche possibile eseguirle in locale. Anche se la maggior parte del tempo è bene essere in grado di lavorare su singole applicazioni o microservizi in modo indipendente, a volte è bene essere in grado di eseguire l'intero sistema in locale così come verrà eseguito quando viene distribuito in produzione. Ci sono diversi modi per raggiungere questo obiettivo, due dei quali sono Minikube e Docker Desktop. Visual Studio fornisce anche strumenti per lo sviluppo Docker.Visual Studio also provides tooling for Docker development.

### <a name="minikube"></a>Minikube

Che cos'è Minikube? Il progetto Minikube dice "Minikube implementa un cluster Kubernetes locale su macOS, Linux e Windows." I suoi obiettivi principali sono "essere il miglior strumento per lo sviluppo di applicazioni Kubernetes locali e per supportare tutte le funzionalità di Kubernetes che si adattano." L'installazione di Minikube è separata da Docker, ma Minikube supporta hypervisor diversi da quelli supportati da Docker Desktop. Le seguenti funzionalità di Kubernetes sono attualmente supportate da Minikube:

- DNS
- NodePorts (Porte nodo)
- ConfigMappe e segreti
- Dashboard
- Runtime contenitore: Docker, rkt, CRI-O e incontenitoreContainer runtimes: Docker, rkt, CRI-O, and containerd
- Abilitazione dell'interfaccia di rete contenitore (CNI)Enabling Container Network Interface (CNI)
- Dati in ingresso

Dopo aver installato Minikube, è possibile iniziare `minikube start` rapidamente a usarlo eseguendo il comando, che scarica un'immagine e avvia il cluster Kubernetes locale. Una volta avviato il cluster, si interagisce con `kubectl` esso utilizzando i comandi Kubernetes standard.

### <a name="docker-desktop"></a>Docker Desktop

Puoi anche lavorare con Kubernetes direttamente da Docker Desktop su Windows. Questa è l'unica opzione se si utilizzano contenitori di Windows ed è un'ottima scelta anche per i contenitori non Windows. L'app di configurazione Standard Docker Desktop viene utilizzata per configurare Kubernetes in esecuzione da Docker Desktop.

![Configurazione di Kubernetes in Docker Desktop](./media/docker-desktop-kubernetes.png)

**Figura 3-4**. Configurazione di Kubernetes in Docker Desktop.

Docker Desktop è già lo strumento più popolare per la configurazione e l'esecuzione di applicazioni containerizzate in locale. Quando si lavora con Docker Desktop, è possibile sviluppare localmente lo stesso set di immagini del contenitore Docker che verrà distribuito nell'ambiente di produzione. Docker Desktop è progettato per "compilare, testare e spedire" le app containerizzate in locale. Dopo aver inviato le immagini a un registro immagini come Registro di sistema contenitori di Azure o Docker Hub, i servizi come Il servizio Azure Kubernetes (AKS) gestiscono l'applicazione nell'ambiente di produzione.

### <a name="visual-studio-docker-tooling"></a>Strumenti Docker di Visual Studio

Visual Studio supporta lo sviluppo Docker per le applicazioni Web. Quando si crea una nuova applicazione ASP.NET Core, è possibile configurarla con il supporto Docker come parte del processo di creazione del progetto, come illustrato nella Figura 3-5.

![Supporto per Visual Studio Enable Docker](./media/visual-studio-enable-docker-support.png)

**Figura 3-5**. Supporto per Visual Studio Enable Docker

Quando questa opzione è selezionata, `Dockerfile` il progetto viene creato con un nella radice, che può essere usato per compilare e ospitare l'app in un contenitore Docker.When this option is selected, the project is created with a in its root, which can be used to build and host the app in a Docker container. Un esempio Dockerfile è illustrato nella Figura 3-6.

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.0-stretch AS build
WORKDIR /src
COPY ["WebApplication3/WebApplication3.csproj", "WebApplication3/"]
RUN dotnet restore "WebApplication3/WebApplication3.csproj"
COPY . .
WORKDIR "/src/WebApplication3"
RUN dotnet build "WebApplication3.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication3.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication3.dll"]
```

**Figura 3-6**. Dockerfile generato da Visual Studio

Il comportamento predefinito quando l'app viene eseguita è configurato per l'uso anche di Docker.The default behavior when the app runs is configured to use Docker as well. Figura 3-7 Mostra le diverse opzioni di esecuzione disponibili da un nuovo progetto ASP.NET Core creato con il supporto Docker aggiunto.

![Opzioni di esecuzione della finestra mobile di Visual Studio](./media/visual-studio-docker-run-options.png)

**Figura 3-7**. Opzioni di esecuzione della finestra mobile di Visual Studio

Oltre allo sviluppo locale, Azure Dev Spaces offre a più sviluppatori un modo pratico per lavorare con le proprie configurazioni Kubernetes all'interno di Azure.In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way to multiple developers to work with their own Kubernetes configurations within Azure. Come si può vedere nella Figura 3-7, è anche possibile eseguire l'applicazione in Azure Dev Spaces.

Se non si aggiunge il supporto Docker all'applicazione ASP.NET Core al momento della creazione, è sempre possibile aggiungerlo in un secondo momento. In Esplora soluzioni di Visual Studio fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi** > **supporto Docker**, come illustrato nella Figura 3-8.

![Supporto per Visual Studio Add Docker](./media/visual-studio-add-docker-support.png)

**Figura 3-8**. Supporto per Visual Studio Add Docker

Oltre al supporto Docker, è anche possibile aggiungere il supporto per l'orchestrazione del contenitore, illustrato anche nella Figura 3-8. Per impostazione predefinita, l'agente di orchestrazione utilizza Kubernetes e Helm. Dopo aver scelto l'agente di `azds.yaml` orchestrazione, viene aggiunto `charts` un file alla radice del progetto e viene aggiunta una cartella contenente i grafici Helm utilizzati per configurare e distribuire l'applicazione a Kubernetes. Figura 3-9 Mostra i file risultanti in un nuovo progetto.

![Visual Studio Add Orchestrator Support](./media/visual-studio-add-orchestrator-support.png)

**Figura 3-9**. Visual Studio Add Orchestrator Support

## <a name="references"></a>Riferimenti

- [Cos'è Kubernetes](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Installazione di Kubernetes con Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube vs Docker Desktop](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools per Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[Successivo](scale-applications.md)
>[precedente](leverage-serverless-functions.md)
