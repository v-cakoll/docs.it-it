---
title: Uso di contenitori e agenti di orchestrazione
description: Uso dei contenitori Docker e degli agenti di orchestrazione Kubernetes in Azure
ms.date: 06/30/2019
ms.openlocfilehash: 62aaa68b2ada0725f33df62e97f1ca3216b91ccf
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72315886"
---
# <a name="leveraging-containers-and-orchestrators"></a>Uso di contenitori e agenti di orchestrazione

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

I contenitori e gli agenti di orchestrazione sono progettati per risolvere i problemi comuni agli approcci di distribuzione monolitica.

## <a name="challenges-with-monolithic-deployments"></a>Problemi con le distribuzioni monolitiche

Tradizionalmente, la maggior parte delle applicazioni è stata distribuita come singola unità. Tali applicazioni sono definite monolitiche. Questo approccio generale per la distribuzione di applicazioni come unità singole, anche se sono costituite da più moduli o assembly, è noto come architettura monolitica, come illustrato nella figura 3-1.

![Architettura monolitica.](./media/monolithic-architecture.png)

**Figura 3-1**. Architettura monolitica.

Anche se hanno il vantaggio di semplicità, le architetture monolitiche affrontano una serie di problemi:

### <a name="deployments"></a>Distribuzioni

Per la distribuzione in applicazioni monolitiche è in genere necessario riavviare l'intera applicazione, anche se è in corso la sostituzione di un solo modulo di piccole dimensioni. A seconda del numero di computer che ospitano l'applicazione, ciò può causare tempi di inattività durante le distribuzioni.

### <a name="hosting"></a>Hosting

Le applicazioni monolitiche sono ospitate interamente in una singola istanza del computer. Questa operazione potrebbe richiedere hardware di capacità superiore rispetto a qualsiasi modulo di un'applicazione distribuita. Inoltre, se una parte dell'app diventa un collo di bottiglia, l'intera applicazione deve essere distribuita nei nodi del computer aggiuntivi per poter eseguire la scalabilità orizzontale.

### <a name="environment"></a>Ambiente

Le applicazioni monolitiche vengono in genere distribuite in un ambiente host esistente (sistema operativo, Framework installati e così via). Questo ambiente potrebbe non corrispondere all'ambiente in cui l'applicazione è stata sviluppata o testata. Le incoerenze nell'ambiente dell'applicazione sono una fonte comune di problemi per le distribuzioni monolitiche.

### <a name="coupling"></a>Accoppiamento

Le applicazioni monolitiche hanno probabilmente una grande quantità di accoppiamento tra parti diverse dell'applicazione e tra l'applicazione e il relativo ambiente. Questo può rendere difficile scomporre un particolare servizio o un problema in un secondo momento per aumentare la scalabilità o lo scambio in un'implementazione alternativa. Questo accoppiamento comporta anche un impatto potenziale molto maggiore per le modifiche al sistema, richiedendo test approfonditi nelle applicazioni più grandi.

### <a name="technology-choice"></a>Scelta della tecnologia

Le applicazioni monolitiche vengono compilate e distribuite come unità. Questo offre semplicità e uniformità, ma può costituire un ostacolo per l'innovazione. Anche se una nuova funzionalità o un nuovo modulo del sistema potrebbe essere più adatto a una piattaforma o a un Framework più moderno, è probabile che venga creato usando l'approccio corrente dell'applicazione per garantire la coerenza, oltre a semplificare lo sviluppo e la distribuzione.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>Quali sono i vantaggi dei contenitori e degli agenti di orchestrazione?

Docker è la piattaforma di gestione e imaging più diffusa e consente di lavorare rapidamente con i contenitori in Linux e Windows. I contenitori offrono ambienti applicativi distinti ma riproducibili che funzionano allo stesso modo in qualsiasi sistema. Questo li rende perfetti per lo sviluppo e l'hosting di applicazioni e componenti di app in applicazioni native del cloud. I contenitori sono isolati l'uno dall'altro, pertanto due contenitori sullo stesso hardware host possono avere versioni diverse del software e anche del sistema operativo installato, senza che le dipendenze causino conflitti.

I contenitori vengono definiti da file semplici che possono essere archiviati nel controllo del codice sorgente. Diversamente dai server completi, anche le macchine virtuali, che richiedono spesso operazioni manuali per applicare gli aggiornamenti o installare servizi aggiuntivi, l'infrastruttura del contenitore può essere facilmente controllata dalla versione. Quindi, le app create per l'esecuzione nei contenitori possono essere sviluppate, testate e distribuite usando strumenti automatici come parte di una pipeline di compilazione.

I contenitori non sono modificabili. Quando si ha la definizione di un contenitore, è possibile ricreare il contenitore che verrà eseguito esattamente allo stesso modo. Questa immutabilità si presta alla progettazione basata su componenti. Se alcune parti di un'applicazione non cambiano spesso come altre, perché ridistribuire l'intera applicazione quando è possibile distribuire solo le parti che cambiano più di frequente? Diverse funzionalità e problematiche trasversali di un'app possono essere suddivise in unità separate. La figura 3-2 Mostra come un'app monolitica può sfruttare i vantaggi di contenitori e microservizi delegando determinate funzionalità o funzionalità. Anche le funzionalità rimanenti nell'app sono state incluse nel contenitore.

![Breaking un'app monolitica per l'uso di microservizi nel back-end. ](./media/breaking-up-monolith-with-backend-microservices.png)
**figura 3-2**. Suddivisione di un'app monolitica per l'uso di microservizi nel back-end.

Le app native del cloud compilate con contenitori separati traggono vantaggio dalla possibilità di distribuire il maggior volume o il minor volume di un'applicazione in base alle esigenze. I singoli servizi possono essere ospitati in nodi con risorse appropriate per ogni servizio. L'ambiente in cui viene eseguito ogni servizio non è modificabile, può essere condiviso tra sviluppo, test e produzione e può essere facilmente sottoversione. L'accoppiamento tra aree diverse dell'applicazione si verifica in modo esplicito come chiamate o messaggi tra servizi, non dipendenze in fase di compilazione all'interno di Monolith. Qualsiasi parte dell'app complessiva può scegliere la tecnologia più sensata per la funzionalità o la funzionalità senza richiedere modifiche al resto dell'app.

## <a name="what-are-the-scaling-benefits"></a>Quali sono i vantaggi di scalabilità?

I servizi basati sui contenitori possono sfruttare i vantaggi di scalabilità offerti dagli strumenti di orchestrazione, ad esempio Kubernetes. I contenitori di progettazione conoscono solo se stessi. Quando si inizia a avere più contenitori che devono collaborare, può essere utile organizzarli a un livello superiore. Per organizzare un numero elevato di contenitori e le relative dipendenze condivise, ad esempio la configurazione di rete, sono disponibili gli strumenti di orchestrazione per salvare il giorno. Kubernetes è una piattaforma di orchestrazione dei contenitori progettata per automatizzare la distribuzione, il ridimensionamento e la gestione di applicazioni in contenitori. Crea un livello di astrazione su gruppi di contenitori e li organizza in *Pod*. I pod vengono eseguiti nei computer di lavoro denominati *nodi*. L'intero gruppo organizzato viene definito *cluster*. La figura 3-3 Mostra i diversi componenti di un cluster Kubernetes.

componenti del cluster ![Kubernetes. ](./media/kubernetes-cluster-components.png)
**figura 3-3**. Componenti cluster Kubernetes.

Kubernetes offre il supporto incorporato per la scalabilità dei cluster per soddisfare la domanda. In combinazione con i microservizi in contenitori, offre alle applicazioni native del cloud la possibilità di rispondere in modo rapido ed efficiente ai picchi di domanda con risorse aggiuntive quando e dove sono necessari.

### <a name="declarative-versus-imperative"></a>Dichiarativo e imperativo

Kubernetes supporta la configurazione dell'oggetto dichiarativa e imperativa. L'approccio imperativo prevede l'esecuzione di diversi comandi che indicano a Kubernetes cosa eseguire ogni passaggio del processo. *Eseguire* questa immagine. *Eliminare* questo pod. *Esporre* questa porta. Con l'approccio dichiarativo, si usa un file di configurazione che descrive *cosa si vuole* , anziché le *operazioni da eseguire* e Kubernetes i dati per ottenere lo stato finale desiderato. Se il cluster è già stato configurato usando i comandi imperativi, è possibile esportare un manifesto dichiarativo usando `kubectl get svc SERVICENAME -o yaml > service.yaml`. Verrà generato un file manifesto come il seguente:

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

Quando si usa la configurazione dichiarativa, è possibile visualizzare in anteprima le modifiche che verranno apportate prima di eseguirne il commit usando `kubectl diff -f FOLDERNAME` sulla cartella in cui si trovano i file di configurazione. Quando si è certi di voler applicare le modifiche, eseguire `kubectl apply -f FOLDERNAME`. Aggiungere `-R` per elaborare in modo ricorsivo una gerarchia di cartelle.

Oltre ai servizi, è possibile usare la configurazione dichiarativa per altre funzionalità di Kubernetes, ad esempio le *distribuzioni*. Le distribuzioni dichiarative vengono utilizzate dai controller di distribuzione per aggiornare le risorse del cluster. Le distribuzioni vengono usate per implementare nuove modifiche, ridimensionarle per supportare un carico maggiore o eseguire il rollback a una revisione precedente. Se un cluster è instabile, le distribuzioni dichiarative forniscono un meccanismo per ripristinare automaticamente il cluster allo stato desiderato.

L'uso della configurazione dichiarativa consente la rappresentazione dell'infrastruttura come codice che può essere archiviato e sottoposto a controllo delle versioni insieme al codice dell'applicazione. In questo modo viene migliorato il controllo delle modifiche e il supporto migliore per la distribuzione continua mediante una pipeline di compilazione e distribuzione associata alle modifiche al controllo del codice sorgente.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>Quali scenari sono ideali per i contenitori e gli agenti di orchestrazione?

Gli scenari seguenti sono ideali per l'uso dei contenitori e degli agenti di orchestrazione.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Applicazioni che richiedono tempi di esecuzione elevati e scalabilità

Le singole applicazioni con requisiti di scalabilità e tempi di esecuzione elevati sono candidati ideali per architetture cloud native che usano microservizi, contenitori e agenti di orchestrazione. Queste applicazioni possono essere sviluppate in contenitori che usano ambienti con versioni, possono essere testate in modo esteso prima di passare alla produzione e possono essere distribuite in produzione senza tempi di inattività. L'uso di cluster Kubernetes garantisce che tali app possano anche essere ridimensionate su richiesta e ripristinate automaticamente dagli errori dei nodi.

### <a name="large-numbers-of-applications"></a>Un numero elevato di applicazioni

Le organizzazioni che distribuiscono e devono successivamente gestire un numero elevato di applicazioni traggono vantaggio da contenitori e agenti di orchestrazione. Il primo sforzo per configurare gli ambienti in contenitori e i cluster Kubernetes è principalmente un costo fisso. La distribuzione, la gestione e l'aggiornamento delle singole applicazioni hanno un costo che varia in base al numero di applicazioni che devono essere gestite. Oltre a un certo numero relativamente ridotto di applicazioni, la complessità della gestione manuale delle applicazioni personalizzate supera il costo di implementazione di una soluzione tramite contenitori e agenti di orchestrazione.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>Quando è consigliabile evitare di usare i contenitori e gli agenti di orchestrazione?

Se non si è in grado di compilare l'applicazione in base ai principi dell'app a dodici fattori, probabilmente è meglio evitare di evitare i contenitori e gli agenti di orchestrazione. In questi casi, può essere preferibile procedere con una piattaforma di hosting basata su VM o in un sistema ibrido in cui è possibile disattivare determinate parti di funzionalità in contenitori distinti o anche funzioni senza server. 

## <a name="development-resources"></a>Risorse di sviluppo

Questa sezione presenta un breve elenco di risorse di sviluppo che possono essere utili per iniziare a usare i contenitori e gli agenti di orchestrazione per l'applicazione successiva. Per informazioni aggiuntive su come progettare un'app per l'architettura di microservizi nativa del cloud, vedere l'articolo complementare [per i microservizi .NET di questo libro: architettura per le applicazioni .NET in contenitori](https://aka.ms/microservicesebook).

### <a name="local-kubernetes-development"></a>Sviluppo Kubernetes locale

Le distribuzioni Kubernetes offrono un notevole valore negli ambienti di produzione, ma possono anche essere eseguite localmente. Sebbene la maggior parte del tempo sia utile per poter lavorare a singole app o microservizi in modo indipendente, a volte è opportuno poter eseguire l'intero sistema localmente così come verrà eseguito quando viene distribuito in produzione. Esistono diversi modi per ottenere questo risultato, due dei quali sono Minikube e Docker desktop. Visual Studio fornisce anche gli strumenti per lo sviluppo di Docker.

### <a name="minikube"></a>Minikube

Che cos'è Minikube? Il progetto Minikube indica che Minikube implementa un cluster Kubernetes locale in macOS, Linux e Windows. Gli obiettivi principali sono "come lo strumento migliore per lo sviluppo di applicazioni Kubernetes locali e per supportare tutte le funzionalità di Kubernetes che soddisfano". L'installazione di Minikube è separata da Docker, ma Minikube supporta hypervisor diversi rispetto al supporto per desktop docker. Le funzionalità di Kubernetes seguenti sono attualmente supportate da Minikube:

- DNS
- Deports
- ConfigMaps e segreti
- Dashboard
- Runtime del contenitore: Docker, RKT, CRI-O e contenitori
- Abilitazione di CNI (container Network Interface)
- Ingresso

Dopo l'installazione di Minikube, è possibile iniziare a usarla rapidamente eseguendo il comando `minikube start`, che Scarica un'immagine e avvia il cluster Kubernetes locale. Una volta avviato il cluster, è possibile interagire con esso usando i comandi Kubernetes `kubectl` standard.

### <a name="docker-desktop"></a>Desktop Docker

È anche possibile usare Kubernetes direttamente da Docker desktop in Windows. Questa è l'unica opzione se si usano i contenitori di Windows ed è la scelta ideale anche per i contenitori non Windows. L'app di configurazione standard per desktop Docker viene usata per configurare Kubernetes in esecuzione da Docker desktop.

![Configurazione di Kubernetes in Docker desktop](./media/docker-desktop-kubernetes.png)

**Figura 3-4**. Configurazione di Kubernetes in Docker desktop.

Docker desktop è già lo strumento più diffuso per la configurazione e l'esecuzione di app in contenitori in locale. Quando si lavora con Docker desktop, è possibile eseguire lo sviluppo localmente con lo stesso set di immagini del contenitore Docker da distribuire nell'ambiente di produzione. Docker desktop è progettato per creare, testare e distribuire le app in contenitori in locale. Quando le immagini sono state spedite a un registro immagini come Azure Container Registry o Docker Hub, i servizi come Azure Kubernetes Service (AKS) gestiscono l'applicazione in produzione.

### <a name="visual-studio-docker-tooling"></a>Strumenti Docker per Visual Studio

Visual Studio supporta lo sviluppo di Docker per le applicazioni Web. Quando si crea una nuova applicazione ASP.NET Core, viene fornita la possibilità di configurarla con il supporto di Docker come parte del processo di creazione del progetto, come illustrato nella figura 3-5.

![Abilitazione del supporto Docker in Visual Studio](./media/visual-studio-enable-docker-support.png)

**Figura 3-5**. Abilitazione del supporto Docker in Visual Studio

Quando questa opzione è selezionata, il progetto viene creato con un `Dockerfile` nella radice, che può essere usato per creare e ospitare l'app in un contenitore docker. Un esempio di Dockerfile è illustrato nella figura 3-6.

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

Il comportamento predefinito quando viene eseguita l'app è configurato anche per l'uso di Docker. La figura 3-7 Mostra le diverse opzioni di esecuzione disponibili da un nuovo progetto ASP.NET Core creato con il supporto Docker aggiunto.

![Opzioni di esecuzione di Docker per Visual Studio](./media/visual-studio-docker-run-options.png)

**Figura 3-7**. Opzioni di esecuzione di Docker per Visual Studio

Oltre allo sviluppo locale, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) offre un modo pratico per consentire a più sviluppatori di lavorare con le proprie configurazioni Kubernetes all'interno di Azure. Come si può vedere nella figura 3-7, è anche possibile eseguire l'applicazione in Azure Dev Spaces.

Se non si aggiunge il supporto di Docker all'applicazione ASP.NET Core al momento della creazione, è sempre possibile aggiungerla in un secondo momento. Dalla Esplora soluzioni di Visual Studio fare clic con il pulsante destro del mouse sul progetto e scegliere **aggiungi**  > **supporto Docker**, come illustrato nella figura 3-8.

![Aggiunta del supporto per Docker in Visual Studio](./media/visual-studio-add-docker-support.png)

**Figura 3-8**. Aggiunta del supporto per Docker in Visual Studio

Oltre al supporto per Docker, è anche possibile aggiungere il supporto dell'orchestrazione del contenitore, illustrato nella figura 3-8. Per impostazione predefinita, l'agente di orchestrazione USA Kubernetes e Helm. Una volta scelto l'agente di orchestrazione, viene aggiunto un file di `azds.yaml` alla radice del progetto e viene aggiunta una cartella `charts` contenente i grafici Helm usati per configurare e distribuire l'applicazione in Kubernetes. La figura 3-9 Mostra i file risultanti in un nuovo progetto.

![Aggiunta del supporto dell'agente di orchestrazione in Visual Studio](./media/visual-studio-add-orchestrator-support.png)

**Figura 3-9**. Aggiunta del supporto dell'agente di orchestrazione in Visual Studio

## <a name="references"></a>Riferimenti

- [Che cos'è Kubernetes?](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [Installazione di Kubernetes con Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [MiniKube rispetto al desktop Docker](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [Visual Studio Tools per Docker](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
>[Precedente](scale-applications.md)
>[Successivo](leverage-serverless-functions.md)
