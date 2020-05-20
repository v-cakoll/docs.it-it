---
title: DevOps
description: Considerazioni DevOps per le applicazioni native del cloud
ms.date: 05/13/2020
ms.openlocfilehash: ce814595245d49e409e780cb0f63c436299c2e4e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614117"
---
# <a name="devops"></a>DevOps

Il Mantra preferito dei consulenti software consiste nel rispondere a "dipendenze" da eventuali domande poste. Non è perché i consulenti software sono interessati a non occuparsi di una posizione. Poiché non esiste una vera risposta a domande nel software. Non esiste alcun diritto assoluto e errato, bensì un equilibrio tra gli opposti.

Si prendano, ad esempio, le due principali scuole dello sviluppo di applicazioni Web: applicazioni a pagina singola (Spa) rispetto alle applicazioni lato server. Da un lato, l'esperienza utente tende a essere migliore con le Spa e la quantità di traffico verso il server Web può essere ridotta al minimo, in modo da poterla ospitare in un'operazione semplice come l'hosting statico. D'altra parte, le Spa tendono a essere più lente per lo sviluppo e più difficili da testare. Quale è la scelta giusta? E dipende dalla situazione.

Le applicazioni native del cloud non sono immuni alla stessa dicotomia. Hanno vantaggi evidenti in termini di velocità di sviluppo, stabilità e scalabilità, ma la loro gestione può risultare molto più difficile.

Anni fa, non era insolito per il processo di trasferimento di un'applicazione dallo sviluppo alla produzione per un mese o anche di più. Le aziende hanno rilasciato il software in una cadenza di 6 mesi o addirittura ogni anno. Per ottenere un'idea della cadenza delle versioni accettabili prima dei giorni futuri di Windows 10, è necessario che non sia più disponibile Microsoft Windows. Cinque anni passati tra Windows XP e vista, un ulteriore 3 tra vista e Windows 7.

È ora abbastanza ben definito che la possibilità di rilasciare il software consente alle aziende in rapida evoluzione di ottenere un notevole vantaggio sul mercato rispetto ai concorrenti più simili a bradipo. Per questo motivo, gli aggiornamenti principali di Windows 10 sono ora approssimativamente ogni sei mesi.

I modelli e le procedure che consentono versioni più veloci e affidabili per fornire valore al business sono collettivamente noti come DevOps. Sono costituiti da un'ampia gamma di idee che occupano l'intero ciclo di vita dello sviluppo software, dalla specifica di un'applicazione fino alla distribuzione e al funzionamento di tale applicazione.

DevOps è emerso prima dei microservizi ed è probabile che lo spostamento verso i servizi più piccoli e più idonei non sarebbe stato possibile senza DevOps per rendere più semplice il rilascio e il funzionamento di una sola applicazione, ma di molte applicazioni in produzione.

![Figura 10-1 le tendenze di ricerca mostrano che la crescita nei microservizi non si avvia fino a quando DevOps non è un'idea abbastanza ben definita.](./media/microservices-vs-devops.png)

**Figura 10-1** -DevOps e microservizi.

Grazie alle buone procedure DevOps, è possibile sfruttare i vantaggi delle applicazioni native del cloud senza soffocare in una montagna di lavoro che funziona effettivamente con le applicazioni.

Non esiste un martello dorato quando si tratta di DevOps. Nessuno può vendere una soluzione completa e onnicomprensiva per rilasciare e gestire applicazioni di alta qualità. Poiché ogni applicazione è molto diversa da tutte le altre. Tuttavia, sono disponibili strumenti che possono rendere DevOps una proposta molto meno scoraggiante. Uno di questi strumenti è noto come Azure DevOps.

## <a name="azure-devops"></a>Azure DevOps

Azure DevOps ha un pedigree lungo. Può riportare le radici a quando Team Foundation Server prima spostato online e con le varie modifiche del nome: Visual Studio online e Visual Studio Team Services. Nel corso degli anni, tuttavia, è diventato molto più dei suoi predecessori.

Azure DevOps è suddiviso in cinque componenti principali:

![Figura 10-2 le cinque principali aree di Azure DevOps](./media/devops-components.png)

**Figura 10-2** -Azure DevOps.

Gestione del codice sorgente **Azure Repos** che supporta il venerato controllo della versione di Team Foundation (TFVC) e il [git](https://en.wikipedia.org/wiki/Git)preferito del settore. Le richieste pull consentono di abilitare la codifica social attraverso la discussione delle modifiche apportate.

**Azure Boards** : fornisce un problema e lo strumento di gestione degli elementi di lavoro che consente agli utenti di selezionare i flussi di lavoro più adatti. Include una serie di modelli preconfigurati, tra cui quelli per supportare gli stili SCRUM e Kanban dello sviluppo.

**Azure Pipelines** : un sistema di compilazione e di gestione delle versioni che supporta una stretta integrazione con Azure. Le compilazioni possono essere eseguite su una vasta gamma di piattaforme da Windows a Linux e MacOS. È possibile eseguire il provisioning degli agenti di compilazione nel cloud o in locale.

**Azure test plans** : non verrà lasciata alcuna persona di controllo di qualità con la gestione dei test e il supporto per il testing esplorativo offerti dalla funzionalità test plans.

**Azure Artifacts** : un feed artefatto che consente alle aziende di creare le proprie versioni, interne e di NuGet, NPM e altre. Si tratta di un doppio scopo di fungere da cache di pacchetti upstream in caso di errore di un repository centralizzato.

L'unità organizzativa di primo livello in Azure DevOps è nota come progetto. All'interno di ogni progetto è possibile attivare e disattivare i vari componenti, ad esempio Azure Artifacts. Ognuno di questi componenti offre vantaggi diversi per le applicazioni native del cloud. I tre più utili sono repository, lavagne e pipeline. Se gli utenti vogliono gestire il codice sorgente in un altro stack di repository, ad esempio GitHub, ma sfruttano ancora Azure Pipelines e altri componenti, questo è perfettamente possibile.

Fortunatamente, i team di sviluppo hanno molte opzioni per la selezione di un repository. Uno di questi è GitHub.

## <a name="github-actions"></a>Azioni di GitHub

Fondata nel 2009, GitHub è un repository basato sul web molto diffuso per l'hosting di progetti, documentazione e codice. Molte aziende tech di grandi dimensioni, ad esempio Apple, Amazon, Google e mainstream Corporation, usano GitHub. GitHub usa il sistema di controllo della versione distribuito open source denominato git come base. Nella parte superiore viene quindi aggiunto il proprio set di funzionalità, tra cui il rilevamento dei difetti, le richieste di funzionalità e pull, la gestione delle attività e i wiki per ogni codebase.

Quando GitHub si evolve, aggiunge anche le funzionalità DevOps. In GitHub, ad esempio, è presente una pipeline di integrazione continua/recapito continuo (CI/CD), denominata `GitHub Actions` . Azioni di GitHub è uno strumento di automazione del flusso di lavoro basato su community. Consente ai team di DevOps di integrarsi con gli strumenti esistenti, combinare e abbinare nuovi prodotti e collegarsi al ciclo di vita del software, inclusi i partner CI/CD esistenti. "

GitHub ha più di 40 milioni utenti, rendendolo l'host più grande del codice sorgente nel mondo. Nell'ottobre del 2018 Microsoft ha acquistato GitHub. Microsoft si è impegnata a fare in modo che GitHub rimanga una [piattaforma aperta](https://techcrunch.com/2018/06/04/microsoft-promises-to-keep-github-independent-and-open/) che tutti gli sviluppatori possono inserire ed estendere. Continua a funzionare come società indipendente. GitHub offre piani per account aziendali, team, professionali e gratuiti.

## <a name="source-control"></a>Controllo del codice sorgente

Organizzare il codice per un'applicazione nativa del cloud può risultare complesso. Invece di una singola applicazione gigante, le applicazioni native del cloud tendono a essere costituite da un Web di applicazioni più piccole che comunicano tra loro. Come per tutti gli aspetti del calcolo, la migliore disposizione del codice rimane una domanda aperta. Sono disponibili esempi di applicazioni riuscite che usano diversi tipi di layout, ma due varianti sembrano avere la massima popolarità.

Prima di accedere al controllo del codice sorgente effettivo, è probabile che sia opportuno decidere il numero di progetti appropriati. All'interno di un singolo progetto è disponibile il supporto per più repository e pipeline di compilazione. Le lavagne sono leggermente più complesse, ma anche in questo caso le attività possono essere assegnate facilmente a più team all'interno di un singolo progetto. È possibile supportare centinaia, persino migliaia di sviluppatori, da un singolo progetto DevOps di Azure. Questa operazione è probabilmente l'approccio migliore in quanto offre un'unica posizione per consentire a tutti gli sviluppatori di lavorare da e ridurre la confusione di ricerca di un'applicazione quando gli sviluppatori non sono certi del progetto in cui risiede.

Suddividere il codice per i microservizi nel progetto Azure DevOps può essere leggermente più complesso.

![Figura 10-3 singolo e più repository](./media/single-repository-vs-multiple.png)

**Figura 10-3** -uno rispetto a molti repository.

### <a name="repository-per-microservice"></a>Repository per microservizio

A prima vista, questo sembra come l'approccio più logico per suddividere il codice sorgente per i microservizi. Ogni repository può contenere il codice necessario per compilare un microservizio. I vantaggi di questo approccio sono immediatamente visibili:

1. Le istruzioni per la compilazione e la gestione dell'applicazione possono essere aggiunte a un file Leggimi nella radice di ogni repository. Quando si esegue il capovolgimento dei repository, è facile trovare queste istruzioni, riducendo il tempo di rotazione per gli sviluppatori.
2. Ogni servizio si trova in una posizione logica, facilmente individuabile conoscendo il nome del servizio.
3. È possibile configurare facilmente le compilazioni in modo che vengano attivate solo quando viene apportata una modifica al repository proprietario.
4. Il numero di modifiche in entrata in un repository è limitato al numero ridotto di sviluppatori che lavorano al progetto.
5. La sicurezza è facile da configurare limitando i repository a cui gli sviluppatori hanno autorizzazioni di lettura e scrittura.
6. Le impostazioni a livello di repository possono essere modificate dal team proprietario con almeno una discussione con altri utenti.

Una delle idee principali alla base dei microservizi è che i servizi devono essere silo e separati tra loro. Quando si utilizza la progettazione basata su dominio per stabilire i limiti per i servizi, i servizi fungono da limiti transazionali. Gli aggiornamenti del database non devono occupare più servizi. Questa raccolta di dati correlati viene definita contesto delimitato.  Questa idea è riflessa dall'isolamento dei dati di microservizio in un database separato e autonomo dal resto dei servizi. Si tratta di un'operazione molto utile per portare questa idea fino al codice sorgente.

Tuttavia, questo approccio non è privo di problemi. Uno dei problemi di sviluppo più problematici del tempo è la gestione delle dipendenze. Prendere in considerazione il numero di file che costituiscono la `node_modules` directory media. Una nuova installazione di qualcosa di simile `create-react-app` è probabilmente costituita da migliaia di pacchetti. La questione della gestione di queste dipendenze è difficile.

Se viene aggiornata una dipendenza, i pacchetti downstream devono aggiornare anche questa dipendenza. Sfortunatamente, il lavoro di sviluppo viene eseguito in modo invariabilmente, la `node_modules` Directory si trova in più versioni di un singolo pacchetto, ciascuna delle quali è una dipendenza di un altro pacchetto con versione con una cadenza leggermente diversa. Quando si distribuisce un'applicazione, quale versione di una dipendenza deve essere utilizzata? La versione attualmente in produzione? La versione attualmente in versione beta ma probabilmente è in produzione nel momento in cui il consumer lo rende disponibile per la produzione? Problemi difficili che non vengono risolti usando solo i microservizi.

Sono disponibili librerie che dipendono da un'ampia gamma di progetti. Suddividendo i microservizi con uno in ogni repository, le dipendenze interne possono essere risolte in modo ottimale usando il repository interno Azure Artifacts. Le compilazioni per le librerie effettueranno il push delle versioni più recenti in Azure Artifacts per il consumo interno. Il progetto downstream deve ancora essere aggiornato manualmente per assumere una dipendenza dai pacchetti appena aggiornati.

Un altro svantaggio si presenta quando si trasferisce il codice tra i servizi. Sebbene sia opportuno ritenere che la prima divisione di un'applicazione in microservizi sia corretta al 100%, la realtà è che raramente preveggente come per evitare errori di divisione dei servizi. Di conseguenza, le funzionalità e il codice che lo guidano devono passare da Service a Service: repository al repository. Quando si esegue il salto da un repository a un altro, il codice perde la cronologia. Esistono molti casi, soprattutto nel caso di un controllo, in cui la cronologia completa di un frammento di codice è inestimabile.

Lo svantaggio finale e più importante è il coordinamento delle modifiche. In un'applicazione di microservizi reale, non devono essere presenti dipendenze di distribuzione tra i servizi. Dovrebbe essere possibile distribuire i servizi A, B e C in qualsiasi ordine, in quanto hanno un accoppiamento libero. In realtà, tuttavia, in alcuni casi è preferibile apportare una modifica che attraversi più repository nello stesso momento. Alcuni esempi includono l'aggiornamento di una libreria per chiudere un problema di sicurezza o la modifica di un protocollo di comunicazione utilizzato da tutti i servizi.

Per eseguire una modifica tra repository è necessario eseguire il commit di ogni repository in successione. Ogni modifica apportata a ogni repository dovrà essere richiesta ed esaminata separatamente. Questo può essere difficile da coordinare.

Un'alternativa all'uso di molti repository consiste nell'inserire tutto il codice sorgente in un gigantesco, il tutto noto come singolo repository.

### <a name="single-repository"></a>Repository singolo

In questo approccio, talvolta denominato [monorepository](https://danluu.com/monorepo/), tutto il codice sorgente per ogni servizio viene inserito nello stesso repository. In primo luogo, sembra molto probabile che la gestione del codice sorgente risulti difficoltosa. In questo modo, tuttavia, alcuni vantaggi sono stati evidenziati.

Il primo vantaggio è che è più facile gestire le dipendenze tra i progetti. Anziché basarsi su un feed di artefatto esterno, è possibile importare direttamente i progetti. Questo significa che gli aggiornamenti sono istantanei ed è probabile che le versioni in conflitto vengano rilevate in fase di compilazione nella workstation dello sviluppatore. In effetti, il passaggio di parte del test di integrazione è stato interrotto.

Quando si sposta il codice tra i progetti, è ora più facile mantenere la cronologia poiché i file verranno rilevati come spostati anziché essere riscritti.

Un altro vantaggio è che è possibile apportare modifiche estese che superano i limiti del servizio in un unico commit. In questo modo si riduce il sovraccarico dovuto alla presenza potenzialmente di dozzine di modifiche da rivedere singolarmente.

Sono disponibili molti strumenti che consentono di eseguire l'analisi statica del codice per rilevare procedure di programmazione non sicure o uso problematico di API. In un ambiente con più repository, è necessario eseguire l'iterazione di ogni repository per individuare i problemi. Il singolo repository consente l'esecuzione dell'analisi in un'unica posizione.

Esistono anche molti svantaggi per l'approccio con singolo repository. Uno dei più preoccupati è che la presenza di un singolo repository genera problemi di sicurezza. Se il contenuto di un repository viene perso in un repository per ogni modello di servizio, la quantità di codice perso è minima. Con un singolo repository, tutto il proprietario dell'azienda potrebbe andare perduto. Sono stati apportati molti esempi nel passato di questo evento e sono stati completati gli sforzi per lo sviluppo di giochi. La presenza di più repository espone meno superficie di attacco, che è un tratto auspicabile nella maggior parte delle procedure di sicurezza.

È probabile che le dimensioni del singolo repository diventino rapidamente ingestibili. Questa operazione presenta alcune implicazioni interessanti sulle prestazioni. Potrebbe essere necessario usare strumenti specializzati come [virtual file System per git](https://vfsforgit.org/), originariamente progettato per migliorare l'esperienza degli sviluppatori nel team di Windows.

Spesso l'argomento per l'uso di un singolo repository si riduce a un argomento che Facebook o Google usa questo metodo per la disposizione del codice sorgente. Se l'approccio è sufficientemente adatto per queste società, sicuramente è l'approccio corretto per tutte le aziende. La verità è che alcune aziende operano su qualsiasi tipo di scalabilità di Facebook o Google. I problemi che si verificano in queste scale sono diversi da quelli che la maggior parte degli sviluppatori affronterà. Il bene per l'oca potrebbe non essere adatto per il paper.

Alla fine, è possibile usare una delle due soluzioni per ospitare il codice sorgente per i microservizi. Tuttavia, nella maggior parte dei casi, la gestione e il sovraccarico tecnico del funzionamento in un singolo repository non sono degni dei vantaggi. Suddividere il codice su più repository favorisce una migliore separazione delle problematiche e favorisce l'autonomia tra i team di sviluppo.  

### <a name="standard-directory-structure"></a>Struttura di directory standard

Indipendentemente dai diversi repository singoli e multipli, ogni servizio disporrà di una propria directory. Una delle migliori ottimizzazioni per consentire agli sviluppatori di attraversare rapidamente i progetti consiste nel mantenere una struttura di directory standard.

![Figura 10-4 una struttura di directory standard per i servizi di posta elettronica e di accesso](./media/dir-struct.png)

**Figura 10-4** -struttura di directory standard.

Ogni volta che viene creato un nuovo progetto, deve essere usato un modello che inserisce la struttura corretta. Questo modello può includere anche elementi utili come un file Leggimi di scheletro e un `azure-pipelines.yml` . In qualsiasi architettura di microservizi, un elevato livello di varianza tra i progetti rende più difficili le operazioni bulk rispetto ai servizi.

Sono disponibili molti strumenti che consentono di creare modelli per un'intera directory, contenenti diverse directory di codice sorgente. L' [attendente](https://yeoman.io/) è molto diffuso nel mondo JavaScript e GitHub ha rilasciato di recente [modelli di repository](https://github.blog/2019-06-06-generate-new-repositories-with-repository-templates/), che offrono gran parte della stessa funzionalità.

## <a name="task-management"></a>Gestione delle attività

La gestione delle attività in qualsiasi progetto può essere difficile. Ci sono innumerevoli domande a cui rispondere in merito al tipo di flussi di lavoro da configurare per garantire una produttività ottimale per gli sviluppatori.

Le applicazioni native del cloud tendono a essere più piccole dei prodotti software tradizionali o almeno sono divise in servizi più piccoli. Il rilevamento dei problemi o delle attività correlate a questi servizi rimane altrettanto importante come per qualsiasi altro progetto software. Nessuno desidera perdere traccia di un elemento di lavoro o spiegare a un cliente che il problema non è stato registrato correttamente. Le lavagne sono configurate a livello di progetto, ma all'interno di ogni progetto è possibile definire le aree. Che consentono di suddividere i problemi tra diversi componenti. Il vantaggio di mantenere tutto il lavoro per l'intera applicazione in un'unica posizione consiste nel fatto che è facile spostare gli elementi di lavoro da un team a un altro man mano che sono più comprensibili.

Azure DevOps è dotato di una serie di modelli diffusi preconfigurati. Nella configurazione più semplice, tutto ciò che è necessario conoscere è quello che si trova nel backlog, cosa stanno lavorando gli utenti e cosa è successo. È importante avere questa visibilità sul processo di compilazione del software, in modo che il lavoro possa essere classificato in ordine di priorità e le attività completate segnalate al cliente. Naturalmente, pochi progetti software si attengono a un processo semplice come `to do` , `doing` e `done` . Non è necessario che le persone avviino l'aggiunta di passaggi come `QA` o `Detailed Specification` al processo.

Una delle parti più importanti delle metodologie agile è l'introspezione automatica a intervalli regolari. Queste revisioni hanno lo scopo di fornire informazioni sui problemi che il team sta per affrontare e su come possono essere migliorati. Spesso questo significa modificare il flusso di problemi e funzionalità tramite il processo di sviluppo. Quindi, è perfettamente integro per espandere i layout delle lavagne con fasi aggiuntive.

Le fasi nelle lavagne non sono l'unico strumento organizzativo. A seconda della configurazione della lavagna, è presente una gerarchia di elementi di lavoro. L'elemento più granulare che può essere visualizzato in una lavagna è un'attività. Un'attività contiene i campi relativi a un titolo, una descrizione, una priorità, una stima della quantità di lavoro rimanente e la possibilità di collegarsi ad altri elementi di lavoro o elementi di sviluppo, ovvero rami, commit, richieste pull, compilazioni e così via. Gli elementi di lavoro possono essere classificati in aree diverse dell'applicazione e diverse iterazioni (Sprint) per facilitarne l'individuazione.

![Figura 10-5 un'attività di esempio in Azure DevOps](./media/task-details.png)

**Figura 10-5** -attività in Azure DevOps.

Il campo Descrizione supporta gli stili normali che ci si aspetterebbe (grassetto, corsivo di sottolineatura e sciopero) e la possibilità di inserire immagini. Questo lo rende uno strumento potente da usare quando si specificano lavoro o bug.

È possibile raggruppare le attività in funzioni che definiscono un'unità di lavoro più ampia. Le funzionalità, a loro volta, possono essere [raggruppate in Epic](https://docs.microsoft.com/azure/devops/boards/backlogs/define-features-epics?view=azure-devops). La classificazione delle attività in questa gerarchia rende molto più semplice comprendere il modo in cui la chiusura di una funzionalità di grandi dimensioni consiste nell'implementazione.

![Figura 10-6 tipi di elementi di lavoro configurati per impostazione predefinita nel modello di processo di base](./media/board-issue-types.png)

**Figura 10-6** -elemento di lavoro in Azure DevOps.

Sono presenti diversi tipi di viste nei problemi in Azure Boards. Gli elementi che non sono ancora pianificati vengono visualizzati nel backlog. A questo punto, è possibile assegnarli a uno sprint. Uno sprint è una casella di tempo durante la quale è prevista una certa quantità di lavoro completata. Questo lavoro può includere attività, ma anche la risoluzione dei ticket. Al termine, è possibile gestire l'intero sprint dalla sezione della lavagna dello sprint. Questa visualizzazione Mostra il modo in cui il lavoro è in corso e include un grafico Burn-down per fornire una stima di aggiornamento continuo di se lo sprint avrà esito positivo.

![Figura 10-7 una lavagna con uno sprint definito](./media/sprint-board.png)

**Figura 10-7** -bacheca in Azure DevOps.

A questo punto, dovrebbe essere evidente che è presente una grande quantità di energia nelle lavagne di Azure DevOps. Per gli sviluppatori, è facile visualizzare le informazioni su cui si sta lavorando. Per le visualizzazioni dei Project Manager nei prossimi lavori, oltre a una panoramica del lavoro esistente. Per i responsabili sono disponibili numerosi report relativi a riapprovvigionamento e capacità. Sfortunatamente, non c'è niente di magico sulle applicazioni native del cloud che eliminano la necessità di tenere traccia del lavoro. Tuttavia, se è necessario tenere traccia del lavoro, esistono alcune posizioni in cui l'esperienza è migliore rispetto a DevOps di Azure.

## <a name="cicd-pipelines"></a>Pipeline CI/CD

Quasi nessuna modifica del ciclo di vita dello sviluppo del software è stata così rivoluzionaria come l'avvento dell'integrazione continua (CI) e del recapito continuo (CD). La compilazione e l'esecuzione di test automatizzati rispetto al codice sorgente di un progetto non appena viene archiviata una modifica in rileva gli errori in anticipo. Prima dell'avvento delle compilazioni di integrazione continua, non sarebbe insolito estrarre il codice dal repository e scoprire che non ha superato i test o che non è stato possibile compilarlo. Ciò ha comportato il rilevamento dell'origine della rottura.

Tradizionalmente, la distribuzione di software all'ambiente di produzione richiedeva una documentazione completa e un elenco di passaggi. Ognuno di questi passaggi deve essere completato manualmente in un processo molto soggetto a errori.

![Figura 10-8 elenco di controllo](./media/checklist.png)

**Figura 10-8** -elenco di controllo.

La sorella dell'integrazione continua è il recapito continuo in cui i pacchetti appena creati vengono distribuiti in un ambiente. Il processo manuale non può essere ridimensionato in base alla velocità di sviluppo, in modo che l'automazione diventi più importante. Gli elenchi di controllo vengono sostituiti da script che possono eseguire le stesse attività in modo più rapido e accurato rispetto a qualsiasi uomo.

L'ambiente in cui il recapito continuo può essere un ambiente di test o, come avviene in molte importanti aziende tecnologiche, potrebbe essere l'ambiente di produzione. Quest'ultimo richiede un investimento in test di alta qualità che può garantire che una modifica non interrompa la produzione per gli utenti. Nello stesso modo in cui l'integrazione continua ha rilevato problemi nel codice, il recapito continuo tempestivo rileva i problemi del processo di distribuzione in anticipo.

L'importanza dell'automazione del processo di compilazione e distribuzione è accentuata dalle applicazioni native del cloud. Le distribuzioni si verificano con maggiore frequenza e in più ambienti, quindi la distribuzione manuale di bordi non è possibile.

### <a name="azure-builds"></a>Build di Azure

Azure DevOps offre un set di strumenti per semplificare l'integrazione e la distribuzione continue. Questi strumenti si trovano in Azure Pipelines. Il primo è costituito da build di Azure, uno strumento che consente di eseguire definizioni di compilazione basate su YAML su larga scala. Gli utenti possono usare i propri computer di compilazione (ideale per se la compilazione richiede un ambiente meticolosamente configurato) o usare un computer da un pool costantemente aggiornato di macchine virtuali ospitate in Azure. Questi agenti di compilazione ospitati sono preinstallati con una vasta gamma di strumenti di sviluppo per non solo lo sviluppo .NET, ma per lo sviluppo da Java a Python a quello di iPhone.

DevOps include un'ampia gamma di definizioni di compilazione predefinite che possono essere personalizzate per qualsiasi compilazione. Le definizioni di compilazione sono definite in un file denominato `azure-pipelines.yml` e archiviate nel repository in modo che possano essere sottoposte a controllo delle versioni insieme al codice sorgente. In questo modo è molto più semplice apportare modifiche alla pipeline di compilazione in un branch in quanto è possibile archiviare le modifiche in un solo ramo. Un esempio `azure-pipelines.yml` per la compilazione di un'applicazione web ASP.NET in Framework completo è illustrato nella figura 10-9.

```yml
name: $(rev:r)

variables:
  version: 9.2.0.$(Build.BuildNumber)
  solution: Portals.sln
  artifactName: drop
  buildPlatform: any cpu
  buildConfiguration: release
  
pool:
  name: Hosted VS2017
  demands:
  - msbuild
  - visualstudio
  - vstest

steps:
- task: NuGetToolInstaller@0
  displayName: 'Use NuGet 4.4.1'
  inputs:
    versionSpec: 4.4.1

- task: NuGetCommand@2
  displayName: 'NuGet restore'
  inputs:
    restoreSolution: '$(solution)'

- task: VSBuild@1
  displayName: 'Build solution'
  inputs:
    solution: '$(solution)'
    msbuildArgs: '-p:DeployOnBuild=true -p:WebPublishMethod=Package -p:PackageAsSingleFile=true -p:SkipInvalidConfigurations=true -p:PackageLocation="$(build.artifactstagingdirectory)\\"'
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

- task: VSTest@2
  displayName: 'Test Assemblies'
  inputs:
    testAssemblyVer2: |
     **\$(buildConfiguration)\**\*test*.dll
     !**\obj\**
     !**\*testadapter.dll
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

- task: CopyFiles@2
  displayName: 'Copy UI Test Files to: $(build.artifactstagingdirectory)'
  inputs:
    SourceFolder: UITests
    TargetFolder: '$(build.artifactstagingdirectory)/uitests'

- task: PublishBuildArtifacts@1
  displayName: 'Publish Artifact'
  inputs:
    PathtoPublish: '$(build.artifactstagingdirectory)'
    ArtifactName: '$(artifactName)'
  condition: succeededOrFailed()
```

**Figura 10-9** -un esempio Azure-Pipelines. yml

Questa definizione di compilazione usa una serie di attività predefinite che semplificano la creazione di compilazioni come la creazione di un set di LEGO (più semplice rispetto al gigantesco Millennium Falcon). Ad esempio, l'attività NuGet Ripristina i pacchetti NuGet, mentre l'attività VSBuild chiama gli strumenti di compilazione di Visual Studio per eseguire la compilazione effettiva. In Azure DevOps sono disponibili centinaia di attività diverse, con altre migliaia gestite dalla community. È probabile che, a prescindere dalle attività di compilazione che si sta cercando di eseguire, qualcuno ne abbia già creato uno.

Le compilazioni possono essere attivate manualmente, tramite un'archiviazione, in base a una pianificazione o mediante il completamento di un'altra compilazione. Nella maggior parte dei casi, la compilazione a ogni archiviazione è auspicabile. È possibile filtrare le compilazioni in modo che diverse compilazioni vengano eseguite su diverse parti del repository o su rami diversi. Questo consente scenari come l'esecuzione di compilazioni veloci con test ridotti sulle richieste pull e l'esecuzione di una suite di regressione completa sul trunk su base notturna.

Il risultato finale di una compilazione è una raccolta di file noti come artefatti di compilazione. Questi elementi possono essere passati al passaggio successivo del processo di compilazione o aggiunti a un feed di artefatto di Azure, in modo che possano essere utilizzati da altre compilazioni.

### <a name="azure-devops-releases"></a>Versioni di Azure DevOps

Le compilazioni si occupano della compilazione del software in un pacchetto spedito, ma gli artefatti devono comunque essere inviati a un ambiente di test per completare il recapito continuo. Per questo, Azure DevOps usa uno strumento separato denominato releases. Lo strumento versioni utilizza la stessa libreria delle attività disponibili per la compilazione, ma introduce un concetto di "fasi". Una fase è un ambiente isolato in cui è installato il pacchetto. Un prodotto, ad esempio, potrebbe usare uno sviluppo, un sistema di controllo di qualità e un ambiente di produzione. Il codice viene costantemente recapitato nell'ambiente di sviluppo in cui è possibile eseguire test automatizzati. Una volta superati i test, i test vengono spostati sull'ambiente di controllo di qualità per i test manuali. Infine, il codice viene inserito in produzione, dove è visibile a tutti gli utenti.

![Figura 10-10 una pipeline di rilascio di esempio con fasi di sviluppo, QA e produzione](./media/release-pipeline.png)

**Figura 10-10** -pipeline di versione

Ogni fase della compilazione può essere attivata automaticamente dal completamento della fase precedente. In molti casi, tuttavia, ciò non è consigliabile. Lo stato di un codice in produzione potrebbe richiedere l'approvazione di qualcuno. Lo strumento versioni supporta questa operazione consentendo ai responsabili approvazione a ogni passaggio della pipeline di rilascio. Le regole possono essere configurate in modo che una persona o un gruppo di utenti specifico debba disconnettersi da un rilascio prima di renderlo in produzione. Questi controlli consentono di controllare la qualità manuale e anche per la conformità ai requisiti normativi correlati al controllo di ciò che passa alla produzione.

### <a name="everybody-gets-a-build-pipeline"></a>Tutti gli utenti ottengono una pipeline di compilazione

Non è previsto alcun costo per la configurazione di molte pipeline di compilazione, quindi è vantaggioso avere almeno una pipeline di compilazione per microservizio. Idealmente, i microservizi possono essere distribuiti in modo indipendente in qualsiasi ambiente, in modo che ognuno di essi possa essere rilasciato tramite la propria pipeline senza rilasciare una massa di codice non correlato è perfetto. Ogni pipeline può avere un proprio set di approvazioni che consentono variazioni nel processo di compilazione per ogni servizio.

### <a name="versioning-releases"></a>Versioni di versioni

Uno svantaggio dell'uso della funzionalità versioni è che non può essere definito in un `azure-pipelines.yml` file archiviato. Esistono molti motivi per cui è possibile fare in modo che le definizioni di versione per ramo includano uno scheletro di versione nel modello di progetto. Fortunatamente, il lavoro è in corso per spostare alcune delle fasi del supporto nel componente di compilazione. Questa operazione sarà nota come compilazione in più fasi e la [prima versione è ora disponibile](https://devblogs.microsoft.com/devops/whats-new-with-azure-pipelines/).

>[!div class="step-by-step"]
>[Precedente](azure-security.md) 
> [Avanti](feature-flags.md)
