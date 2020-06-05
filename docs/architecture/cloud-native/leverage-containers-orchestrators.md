---
title: Uso di contenitori e agenti di orchestrazione
description: Uso dei contenitori Docker e degli agenti di orchestrazione Kubernetes in Azure
ms.date: 05/31/2020
ms.openlocfilehash: 25e981e0fb7957e7180be09a19a406eddfe4e51b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446867"
---
# <a name="leveraging-containers-and-orchestrators"></a>Uso di contenitori e agenti di orchestrazione

I contenitori e gli agenti di orchestrazione sono progettati per risolvere i problemi comuni agli approcci di distribuzione monolitica.

## <a name="challenges-with-monolithic-deployments"></a>Problemi con le distribuzioni monolitiche

Tradizionalmente, la maggior parte delle applicazioni è stata distribuita come singola unità. Tali applicazioni sono definite monolitiche. Questo approccio generale per la distribuzione di applicazioni come unità singole, anche se sono costituite da più moduli o assembly, è noto come architettura monolitica, come illustrato nella figura 3-1.

![Architettura monolitica.](./media/monolithic-design.png)

**Figura 3-1**. Architettura monolitica.

Anche se hanno il vantaggio di semplicità, le architetture monolitiche affrontano una serie di problemi:

### <a name="deployment"></a>Distribuzione

Le applicazioni monolitiche richiedono una distribuzione completa dell'intera applicazione, anche se è stata apportata solo una piccola modifica. Le distribuzioni complete possono essere costose e soggette a errori. Inoltre, richiedono il riavvio dell'applicazione, che influisca temporaneamente sull'indisponibilità.

### <a name="scaling"></a>Scalabilità

Un'applicazione monolitica è ospitata interamente in una singola istanza del computer, spesso richiedendo hardware ad alta capacità. Se una parte del monolito richiede la scalabilità, un'altra copia dell'intera applicazione deve essere distribuita in un altro computer. Con un Monolith, non è possibile ridimensionare singolarmente i componenti dell'applicazione, perché sono tutti o nulla. Il ridimensionamento di componenti che non richiedono la scalabilità comporta un uso inefficiente e costoso delle risorse.

### <a name="environment"></a>Ambiente

Le applicazioni monolitiche vengono in genere distribuite in un ambiente host con un sistema operativo preinstallato, un runtime e dipendenze di libreria. Questo ambiente potrebbe non corrispondere a quello in cui l'applicazione è stata sviluppata o testata. Le incoerenze negli ambienti applicativi rappresentano una fonte comune di problemi per le distribuzioni monolitiche.

### <a name="coupling"></a>Accoppiamento

È probabile che un'applicazione monolitica riscontri un accoppiamento elevato tra i componenti funzionali. Senza limiti rigidi, le modifiche apportate al sistema spesso generano effetti collaterali indesiderati e costosi. Le nuove funzionalità e correzioni diventano difficili da implementare e dispendiose in termini di tempo. Gli aggiornamenti richiedono test completi. L'accoppiamento rende anche difficile effettuare il refactoring dei componenti o scambiare in implementazioni alternative. Anche se costruita con una stretta separazione dei problemi, l'erosione dell'architettura si imposta in, in quanto la codebase monolitica si deteriora con "casi speciali" senza terminazione.

### <a name="platform-lock-in"></a>Blocco della piattaforma

Un'applicazione monolitica è costruita con un singolo stack di tecnologie. Pur offrendo uniformità, questo impegno può diventare un ostacolo per l'innovazione. Le nuove funzionalità e i nuovi componenti verranno creati usando lo stack corrente dell'applicazione, anche quando le tecnologie più moderne possono essere la scelta migliore. Un rischio a lungo termine è che lo stack di tecnologie diventa obsoleto e obsoleto. La riprogettazione di un'intera applicazione in una nuova piattaforma più moderna è molto costosa e rischiosa.

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a>Quali sono i vantaggi dei contenitori e degli agenti di orchestrazione?

Nel capitolo 1 sono stati introdotti i contenitori. È stato evidenziato il modo in cui il cloud native Computing Foundation (CNCF) classifica la contenitori come primo passaggio della [mappa dei percorsi nativa del cloud](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) : linee guida per le aziende che iniziano il percorso nativo del cloud. In questa sezione vengono illustrati i vantaggi dei contenitori.

Docker è la piattaforma di gestione dei contenitori più diffusa. Funziona con i contenitori in Linux o Windows. I contenitori offrono ambienti applicativi distinti ma riproducibili che funzionano allo stesso modo in qualsiasi sistema. Questo aspetto li rende perfetti per lo sviluppo e l'hosting di servizi nativi del cloud. I contenitori sono isolati l'uno dall'altro. Due contenitori nello stesso hardware host possono avere versioni diverse del software, senza causare conflitti.

I contenitori vengono definiti da semplici file basati su testo che diventano elementi del progetto e vengono archiviati nel controllo del codice sorgente. Sebbene i server completi e le macchine virtuali richiedano interventi manuali per l'aggiornamento, i contenitori sono facilmente controllati dalla versione. Le app compilate per l'esecuzione nei contenitori possono essere sviluppate, testate e distribuite usando strumenti automatici come parte di una pipeline di compilazione.

I contenitori non sono modificabili. Una volta definito un contenitore, è possibile ricrearlo ed eseguirlo esattamente allo stesso modo. Questa immutabilità si presta alla progettazione basata su componenti. Se alcune parti di un'applicazione si evolvono in modo diverso rispetto ad altre, perché ridistribuire l'intera applicazione quando è possibile distribuire solo le parti che cambiano più di frequente? Diverse funzionalità e problematiche trasversali di un'app possono essere suddivise in unità separate. La figura 3-2 Mostra come un'app monolitica può sfruttare i vantaggi di contenitori e microservizi delegando determinate funzionalità o funzionalità. Anche le funzionalità rimanenti nell'app sono state incluse nel contenitore.

![Suddivisione di un'app monolitica per l'uso di microservizi nel back-end.](./media/cloud-native-design.png)

**Figura 3-2**. Scomposizione di un'app monolitica per l'adozione di microservizi.

Ogni servizio nativo del cloud viene compilato e distribuito in un contenitore separato. Ogni può aggiornare in base alle esigenze. I singoli servizi possono essere ospitati in nodi con risorse appropriate per ogni servizio. L'ambiente in cui viene eseguito ogni servizio non è modificabile, è condiviso tra ambienti di sviluppo, test e produzione e con facilità di controllo delle versioni. L'accoppiamento tra aree diverse dell'applicazione si verifica in modo esplicito come chiamate o messaggi tra servizi, non dipendenze in fase di compilazione all'interno di Monolith. È anche possibile scegliere la tecnologia più adatta a una determinata funzionalità senza richiedere modifiche al resto dell'app.

I servizi in contenitori richiedono la gestione automatica. Non sarebbe possibile amministrare manualmente un ampio set di contenitori distribuiti in modo indipendente. Si considerino, ad esempio, le attività seguenti:

- Come verrà effettuato il provisioning delle istanze di contenitore in un cluster di molti computer?
- Dopo la distribuzione, in che modo i contenitori rileveranno e comunicheranno tra loro?
- In che modo i contenitori possono aumentare o ridurre la scalabilità su richiesta?
- Come è possibile monitorare l'integrità di ogni contenitore?
- In che modo è possibile proteggere un contenitore da errori hardware e software?
- Come si aggiornano i contenitori per un'applicazione dinamica senza tempi di inattività?

Gli agenti di orchestrazione dei contenitori indirizzano e automatizzano queste e altre problematiche.

Nel sistema eco-nativo del cloud, Kubernetes è diventato l'agente di orchestrazione del contenitore de facto. Si tratta di una piattaforma open source gestita da cloud native Computing Foundation (CNCF). Kubernetes automatizza la distribuzione, il ridimensionamento e i problemi operativi dei carichi di lavoro in contenitori in un cluster di computer. Tuttavia, l'installazione e la gestione di Kubernetes è notoriamente complessa.

Un approccio molto migliore consiste nell'utilizzare Kubernetes come servizio gestito da un fornitore di cloud. Il cloud di Azure offre una piattaforma Kubernetes completamente gestita denominata [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). AKS astrae la complessità e il sovraccarico operativo della gestione di Kubernetes. Si usa Kubernetes come servizio cloud; Microsoft si assume la responsabilità di gestirla e supportarla. AKS si integra inoltre strettamente con altri servizi e strumenti di sviluppo di Azure.

AKS è una tecnologia basata su cluster. Un pool di macchine virtuali federate, o nodi, viene distribuito nel cloud di Azure. Insieme formano un ambiente a disponibilità elevata o un cluster. Il cluster viene visualizzato come una singola entità semplice per l'applicazione nativa del cloud. Dietro le quinte, AKS distribuisce i servizi in contenitori in questi nodi seguendo una strategia predefinita che distribuisce il carico in modo uniforme.

## <a name="what-are-the-scaling-benefits"></a>Quali sono i vantaggi di scalabilità?

I servizi basati sui contenitori possono sfruttare i vantaggi di scalabilità offerti dagli strumenti di orchestrazione, ad esempio Kubernetes. I contenitori di progettazione conoscono solo se stessi. Quando si dispone di più contenitori che devono collaborare, è necessario organizzarli a un livello superiore. Per organizzare un numero elevato di contenitori e le relative dipendenze condivise, ad esempio la configurazione di rete, sono disponibili gli strumenti di orchestrazione per salvare il giorno. Kubernetes crea un livello di astrazione su gruppi di contenitori e li organizza in *baccelli*. I pod vengono eseguiti nei computer di lavoro denominati *nodi*. Questa struttura organizzata è detta *cluster*. La figura 3-3 Mostra i diversi componenti di un cluster Kubernetes.

![Componenti cluster Kubernetes. ](./media/kubernetes-cluster-components.png)
 **Figura 3-3**. Componenti cluster Kubernetes.

La scalabilità dei carichi di lavoro in contenitori è una funzionalità chiave degli agenti di orchestrazione dei contenitori. AKS supporta il ridimensionamento automatico tra due dimensioni: istanze di contenitore e nodi di calcolo. Insieme offrono a AKS la possibilità di rispondere in modo rapido ed efficiente ai picchi di richiesta e di aggiungere altre risorse. Più avanti in questo capitolo viene illustrato il ridimensionamento in AKS.

### <a name="declarative-versus-imperative"></a>Dichiarativo e imperativo

Kubernetes supporta sia la configurazione dichiarativa che imperativa. L'approccio imperativo prevede l'esecuzione di diversi comandi che indicano a Kubernetes cosa eseguire ogni passaggio del processo. Eseguire questa immagine. Eliminare questo pod. Esporre questa porta. Con l'approccio dichiarativo, si crea un file di configurazione, denominato manifesto, per descrivere cosa si vuole, anziché come procedere. Kubernetes legge il manifesto e trasforma lo stato finale desiderato nello stato finale effettivo.

I comandi imperativi sono ottimi per l'apprendimento e la sperimentazione interattiva. Tuttavia, è opportuno creare in modo dichiarativo i file manifesto Kubernetes per adottare un'infrastruttura come approccio al codice, fornendo distribuzioni affidabili e ripetibili. Il file manifesto diventa un elemento del progetto e viene usato nella pipeline CI/CD per l'automazione delle distribuzioni Kubernetes.

Se il cluster è già stato configurato usando i comandi imperativi, è possibile esportare un manifesto dichiarativo usando `kubectl get svc SERVICENAME -o yaml > service.yaml` . Questo comando genera un manifesto simile a quello riportato di seguito:

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

Quando si usa la configurazione dichiarativa, è possibile visualizzare in anteprima le modifiche che verranno apportate prima di eseguirne il commit usando la cartella in cui si trovano i `kubectl diff -f FOLDERNAME` file di configurazione. Quando si è certi di voler applicare le modifiche, eseguire `kubectl apply -f FOLDERNAME` . Aggiungere `-R` per elaborare in modo ricorsivo una gerarchia di cartelle.

È anche possibile usare la configurazione dichiarativa con altre funzionalità di Kubernetes, tra cui le distribuzioni. Le distribuzioni dichiarative consentono di gestire versioni, aggiornamenti e scalabilità. Indicano al controller di distribuzione Kubernetes di distribuire nuove modifiche, aumentare il carico o eseguire il rollback a una revisione precedente. Se un cluster è instabile, una distribuzione dichiarativa restituirà automaticamente il cluster allo stato desiderato. Se ad esempio un nodo si arresta in modo anomalo, il meccanismo di distribuzione ridistribuirà una sostituzione per ottenere lo stato desiderato

L'uso della configurazione dichiarativa consente la rappresentazione dell'infrastruttura come codice che può essere archiviato e sottoposto a controllo delle versioni insieme al codice dell'applicazione. Fornisce un miglioramento del controllo delle modifiche e un supporto migliore per la distribuzione continua tramite una pipeline di compilazione e distribuzione.

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a>Quali scenari sono ideali per i contenitori e gli agenti di orchestrazione?

Gli scenari seguenti sono ideali per l'uso dei contenitori e degli agenti di orchestrazione.

### <a name="applications-requiring-high-uptime-and-scalability"></a>Applicazioni che richiedono tempi di esecuzione elevati e scalabilità

Le singole applicazioni con requisiti di scalabilità e tempi di esecuzione elevati sono candidati ideali per architetture cloud native che usano microservizi, contenitori e agenti di orchestrazione. Possono essere sviluppate in contenitori, testati in ambienti con versioni diverse e distribuiti in produzione senza tempi di inattività. L'uso di cluster Kubernetes garantisce che tali app possano anche essere ridimensionate su richiesta e ripristinate automaticamente dagli errori dei nodi.

### <a name="large-numbers-of-applications"></a>Un numero elevato di applicazioni

Le organizzazioni che distribuiscono e gestiscono un numero elevato di applicazioni traggono vantaggio da contenitori e agenti di orchestrazione. Il primo sforzo per configurare gli ambienti in contenitori e i cluster Kubernetes è principalmente un costo fisso. La distribuzione, la gestione e l'aggiornamento delle singole applicazioni hanno un costo che varia in base al numero di applicazioni. Oltre a un numero ridotto di applicazioni, la complessità della gestione manuale delle applicazioni personalizzate supera il costo di implementazione di una soluzione tramite contenitori e agenti di orchestrazione.

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a>Quando è consigliabile evitare di usare i contenitori e gli agenti di orchestrazione?

Se non si è in grado di compilare l'applicazione in base ai principi dell'app a dodici fattori, è consigliabile evitare i contenitori e gli agenti di orchestrazione. In questi casi, si consideri una piattaforma di hosting basata su VM o eventualmente un sistema ibrido. Con esso, è sempre possibile disattivare determinate parti di funzionalità in contenitori distinti o anche funzioni senza server.

## <a name="development-resources"></a>Risorse di sviluppo

Questa sezione presenta un breve elenco di risorse di sviluppo che possono essere utili per iniziare a usare i contenitori e gli agenti di orchestrazione per l'applicazione successiva. Per informazioni aggiuntive su come progettare un'app per l'architettura di microservizi nativa del cloud, vedere l'articolo complementare [per i microservizi .NET di questo libro: architettura per le applicazioni .NET in contenitori](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook).

### <a name="local-kubernetes-development"></a>Sviluppo Kubernetes locale

Le distribuzioni Kubernetes offrono un notevole valore negli ambienti di produzione, ma possono anche essere eseguite localmente nel computer di sviluppo. Sebbene sia possibile lavorare su singoli microservizi in modo indipendente, in alcuni casi è necessario eseguire l'intero sistema localmente, così come verrà eseguito quando viene distribuito in produzione. Sono disponibili diversi strumenti che possono essere utili: Minikube e Docker desktop. Visual Studio fornisce anche gli strumenti per lo sviluppo di Docker.

### <a name="minikube"></a>Minikube

Che cos'è Minikube? Il progetto Minikube indica che Minikube implementa un cluster Kubernetes locale in macOS, Linux e Windows. Gli obiettivi principali sono "come lo strumento migliore per lo sviluppo di applicazioni Kubernetes locali e per supportare tutte le funzionalità di Kubernetes che soddisfano". L'installazione di Minikube è separata da Docker, ma Minikube supporta hypervisor diversi rispetto al supporto per desktop docker. Le funzionalità di Kubernetes seguenti sono attualmente supportate da Minikube:

- DNS
- Deports
- ConfigMaps e segreti
- Dashboard
- Runtime del contenitore: Docker, RKT, CRI-O e contenitori
- Abilitazione di CNI (container Network Interface)
- Dati in ingresso

Dopo l'installazione di Minikube, è possibile iniziare a usarla rapidamente eseguendo il `minikube start` comando, che Scarica un'immagine e avvia il cluster Kubernetes locale. Una volta avviato il cluster, è possibile interagire con esso usando i comandi Kubernetes standard `kubectl` .

### <a name="docker-desktop"></a>Docker Desktop

È anche possibile usare Kubernetes direttamente da Docker desktop in Windows. Si tratta dell'unica opzione se si usano i contenitori di Windows ed è un'ottima scelta anche per i contenitori non Windows. La figura 3-4 illustra come abilitare il supporto Kubernetes locale durante l'esecuzione di Docker desktop.

![Configurazione di Kubernetes in Docker desktop](./media/docker-desktop-kubernetes.png)

**Figura 3-4**. Configurazione di Kubernetes in Docker desktop.

Docker desktop è lo strumento più diffuso per la configurazione e l'esecuzione di app in contenitori in locale. Quando si lavora con Docker desktop, è possibile eseguire lo sviluppo localmente con lo stesso set di immagini del contenitore Docker da distribuire nell'ambiente di produzione. Docker desktop è progettato per creare, testare e distribuire le app in contenitori in locale. Supporta i contenitori sia Linux che Windows. Quando si esegue il push delle immagini in un registro immagini, ad esempio Azure Container Registry o Docker Hub, AKS può effettuare il pull e la distribuzione nell'ambiente di produzione.

### <a name="visual-studio-docker-tooling"></a>Strumenti Docker per Visual Studio

Visual Studio supporta lo sviluppo di Docker per le applicazioni basate sul Web. Quando si crea una nuova applicazione ASP.NET Core, è possibile configurarla con il supporto di Docker, come illustrato nella figura 3-5.

![Abilitazione del supporto Docker in Visual Studio](./media/visual-studio-enable-docker-support.png)

**Figura 3-5**. Abilitazione del supporto Docker in Visual Studio

Quando questa opzione è selezionata, il progetto viene creato con `Dockerfile` nella relativa radice, che può essere usato per compilare e ospitare l'app in un contenitore docker. Un esempio di Dockerfile è illustrato nella figura 3 6. git

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ["eShopWeb/eShopWeb.csproj", "eShopWeb/"]
RUN dotnet restore "eShopWeb/eShopWeb.csproj"
COPY . .
WORKDIR "/src/eShopWeb"
RUN dotnet build "eShopWeb.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "eShopWeb.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "eShopWeb.dll"]
```

**Figura 3-6**. Dockerfile generato da Visual Studio

Il comportamento predefinito quando viene eseguita l'app è configurato anche per l'uso di Docker. La figura 3-7 Mostra le diverse opzioni di esecuzione disponibili da un nuovo progetto ASP.NET Core creato con il supporto Docker aggiunto.

![Opzioni di esecuzione di Docker per Visual Studio](./media/visual-studio-docker-run-options.png)

**Figura 3-7**. Opzioni di esecuzione di Docker per Visual Studio

Oltre allo sviluppo locale, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) offre un modo pratico per consentire a più sviluppatori di lavorare con le proprie configurazioni Kubernetes all'interno di Azure. Come si può vedere nella figura 3-7, è anche possibile eseguire l'applicazione in Azure Dev Spaces.

Inoltre, in qualsiasi momento è possibile aggiungere il supporto di Docker a un'applicazione ASP.NET Core esistente. Dalla Esplora soluzioni di Visual Studio, fare clic con il pulsante destro del mouse sul progetto e **aggiungere**il  >  **supporto di Docker**, come illustrato nella figura 3-8.

![Aggiunta del supporto per Docker in Visual Studio](./media/visual-studio-add-docker-support.png)

**Figura 3-8**. Aggiunta del supporto Docker a Visual Studio

È anche possibile aggiungere il supporto dell'orchestrazione del contenitore, illustrato nella figura 3-8. Per impostazione predefinita, l'agente di orchestrazione USA Kubernetes e Helm. Dopo aver scelto l'agente di orchestrazione, `azds.yaml` viene aggiunto un file alla radice del progetto e `charts` viene aggiunta una cartella contenente i grafici Helm usati per configurare e distribuire l'applicazione in Kubernetes. La figura 3-9 Mostra i file risultanti in un nuovo progetto.

![Aggiunta del supporto dell'agente di orchestrazione in Visual Studio](./media/visual-studio-add-orchestrator-support.png)

**Figura 3-9**. Aggiunta del supporto dell'orchestrazione a Visual Studio

### <a name="visual-studio-code-docker-tooling"></a>Strumenti Docker Visual Studio Code

Sono disponibili numerose estensioni per Visual Studio Code che supportano lo sviluppo di Docker.

Microsoft fornisce l' [estensione Docker per Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker). Questa estensione semplifica il processo di aggiunta del supporto del contenitore alle applicazioni. Esegue l'impalcatura dei file necessari, compila le immagini Docker e consente di eseguire il debug dell'app all'interno di un contenitore. L'estensione include una finestra di esplorazione visiva che semplifica l'esecuzione di azioni su contenitori e immagini, ad esempio avvio, arresto, ispezione, rimozione e altro ancora. L'estensione supporta inoltre Docker Compose consentendo di gestire più contenitori in esecuzione come una singola unità.

>[!div class="step-by-step"]
>[Precedente](scale-applications.md) 
> [Avanti](leverage-serverless-functions.md)
