---
title: Definizione di cloud nativo
description: Scopri i pilastri fondamentali che forniscono il fondamento per i sistemi cloud-native
author: robvet
ms.date: 08/20/2019
ms.openlocfilehash: 27191a67b2964ac2e1636a4d7dc55d5314b78439
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401571"
---
# <a name="defining-cloud-native"></a>Definizione di cloud nativeDefining cloud native

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Ferma quello che stai facendo e invia un SMS a 10 dei tuoi colleghi. Chiedere loro di definire il termine "Cloud Native". Buone probabilità che tu ottua otto risposte diverse. È interessante notare che, tra sei mesi, con l'evolversi delle tecnologie e delle pratiche native del cloud, anche la loro definizione.

Cloud native consiste nel cambiare il modo in cui pensiamo di costruire sistemi aziendali critici.

I sistemi nativi del cloud sono progettati per abbracciare rapidi cambiamenti, su larga scala e resilienza.

La Cloud Native Computing Foundation fornisce una [definizione ufficiale:](https://github.com/cncf/foundation/blob/master/charter.md)

> *Le tecnologie native per il cloud consentono alle organizzazioni di creare ed eseguire applicazioni scalabili in ambienti moderni e dinamici, ad esempio cloud pubblici, privati e ibridi. Contenitori, maglie del servizio, microservizi, infrastruttura non modificabile e API dichiarative esemplificano questo approccio.*

> *Queste tecniche consentono sistemi ad accoppiamento libero che sono resilienti, gestibili e osservabili. In combinazione con un'automazione robusta, consentono agli ingegneri di apportare frequentemente e prevedibilmente modifiche ad alto impatto con una fatica minima.*

Le applicazioni sono diventate sempre più complesse e gli utenti richiedono sempre di più. Gli utenti si aspettano una rapida reattività, funzionalità innovative e zero tempi di inattività. I problemi di prestazioni, gli errori ricorrenti e l'impossibilità di muoversi rapidamente non sono più accettabili. Si sposteranno facilmente verso il tuo concorrente.

Cloud nativo è molto di *velocità* e *agilità*. I sistemi aziendali si stanno evolvendo dall'abilitazione delle capacità aziendali alle armi di trasformazione strategica, all'accelerazione della velocità e della crescita del business. È imperativo far entrare immediatamente le idee sul mercato.

Ecco alcune aziende che hanno implementato queste tecniche. Pensa alla velocità, all'agilità e alla scalabilità che hanno raggiunto.

| Company | Esperienza |
| :-------- | :-------- |
| [Netflix](https://www.infoq.com/news/2013/06/netflix/) | Ha oltre 600 servizi in produzione. Distribuisce cento volte al giorno. |
| [Uber](https://eng.uber.com/micro-deploy/) | Ha più di 1.000 servizi immagazzinati in produzione. Distribuisce diverse migliaia di compilazioni ogni settimana. |
| [WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf) | Ha più di 300 servizi in produzione. Fa quasi 1.000 modifiche al giorno. |

Come puoi vedere, Netflix, Uber e WeChat espongono sistemi costituiti da centinaia di microservizi indipendenti. Questo stile architettonico consente loro di rispondere rapidamente alle condizioni di mercato. Possono aggiornare istantaneamente piccole aree di un'applicazione live e complessa e scalarle singolarmente in base alle esigenze.

La velocità e l'agilità del cloud nativo derivano da una serie di fattori. In primo luogo è l'infrastruttura cloud. Cinque ulteriori pilastri fondamentali illustrati nella Figura 1-3 forniscono anche il fondamento per i sistemi cloud-nativi.

![Pilastri fondamentali nativi del cloud](./media/cloud-native-foundational-pillars.png)

**Figura 1-3**. Pilastri fondamentali nativi del cloud

Prendiamoci un po' di tempo per capire meglio il significato di ogni pilastro.

## <a name="the-cloud"></a>La nuvola...

I sistemi nativi nel cloud sfruttano appieno il modello di servizio cloud.

Progettati per prosperare in un ambiente cloud dinamico e virtualizzato, questi sistemi fanno ampio uso dell'infrastruttura di elaborazione [Platform as a Service (PaaS)](https://azure.microsoft.com/overview/what-is-paas/) e dei servizi gestiti. Trattano l'infrastruttura sottostante come *usa e getta,* sottoposta a provisioning in pochi minuti e ridimensionata, ridimensionata, spostata o distrutta su richiesta, tramite l'automazione.

Si consideri il concetto di DevOps ampiamente accettato di [animali domestici vs bovini](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313). In un data center tradizionale, i server sono trattati come *animali domestici*: una macchina fisica, dato un nome significativo, e curato. È possibile eseguire la scalabilità verticale aggiungendo più risorse alla stessa macchina (scalabilità verticale). Se il server si ammala, lo infermiera di nuovo alla salute. Se il server non è più disponibile, tutti se ne accorge.

Il modello di servizio *Cattle* è diverso. Il provisioning di ogni istanza viene eseguito come macchina virtuale o contenitore. Sono identici e gli viene assegnato un identificatore di sistema, ad esempio Service-01, Service-02 e così via. È possibile ridimensionare creando più di essi (scalabilità orizzontale). Quando uno diventa non disponibile, nessuno se ne accorge.

Il modello di bestiame abbraccia *infrastrutture non modificabili.* I server non vengono riparati o modificati. Se uno non riesce o richiede l'aggiornamento, viene distrutto e ne viene eseguito il provisioning di uno nuovo, il tutto tramite automazione.

I sistemi nativi del cloud adottano il modello di servizio Cattle. Continuano a funzionare come l'infrastruttura aumenta o esce senza riguardo ai computer su cui sono in esecuzione.

La piattaforma cloud di Azure supporta questo tipo di infrastruttura altamente elastica con funzionalità di scalabilità automatica, autopulizia e monitoraggio.

## <a name="modern-design"></a>Progettazione moderna

Come si progetta un'app nativa del cloud? Come sarebbe la tua architettura? A quali principi, modelli e best practice aderisce? Quali problemi operativi e infrastrutturali sarebbero importanti?

### <a name="the-twelve-factor-application"></a>L'applicazione a dodici fattori

Una metodologia ampiamente accettata per la costruzione di applicazioni basate su cloud è l'applicazione a [dodici fattori](https://12factor.net/). Descrive una serie di principi e procedure che gli sviluppatori seguono per costruire applicazioni ottimizzate per ambienti cloud moderni. Particolare attenzione viene data alla portabilità tra gli ambienti e all'automazione dichiarativa.

Anche se applicabile a qualsiasi applicazione basata sul Web, molti professionisti lo considerano una solida base per la creazione di applicazioni cloud-native. I sistemi basati su questi principi possono essere implementati e scalati rapidamente e aggiungere funzionalità per reagire rapidamente ai cambiamenti del mercato.

La tabella seguente evidenzia la metodologia a dodici fattori:

|    |  Fattore | Spiegazione  |
| :-------- | :-------- | :-------- |
| 1 | Base di codice | Un'unica base di codice per ogni microservizio, archiviata nel proprio repository. Tracciato con controllo della versione, può essere distribuito in più ambienti (QA, gestione temporanea, produzione). |
| 2 | Dependencies | Ogni microservizio isola e comprime le proprie dipendenze, adottando le modifiche senza influire sull'intero sistema. |
| 3 | Configurazioni  | Le informazioni di configurazione vengono spostate dal microservizio ed esterne tramite uno strumento di gestione della configurazione all'esterno del codice. La stessa distribuzione può propagarsi tra gli ambienti con la configurazione corretta applicata.  |
| 4 | Servizi di backup | Le risorse acillari (archivi dati, cache, broker di messaggi) devono essere esposte tramite un URL indirizzabile. In questo modo la risorsa viene disaccoppiata dall'applicazione, consentendone l'intercambiabile.  |
| 5 | Compilazione, rilascio, esecuzioneBuild, Release, Run | Ogni versione deve imporre una separazione rigorosa tra le fasi di compilazione, rilascio ed esecuzione. Ognuno deve essere contrassegnato con un ID univoco e supportare la possibilità di eseguire il rollback. I moderni sistemi CI/CD contribuiscono a soddisfare questo principio. |
| 6 | Processi | Ogni microservizio deve essere eseguito nel proprio processo, isolato dagli altri servizi in esecuzione. Esternalizzare lo stato richiesto a un servizio di backup, ad esempio una cache distribuita o un archivio dati. |
| 7 | Binding porta | Ogni microservizio deve essere autonomo con le relative interfacce e funzionalità esposte sulla propria porta. In questo modo viene fornito l'isolamento da altri microservizi. |
| 8 | Concorrenza | La scalabilità orizzontale dei servizi su un numero elevato di piccoli processi identici (copie) anziché su una singola istanza di grandi dimensioni nel computer più potente disponibile. |
| 9 | Disposabilità | Le istanze del servizio devono essere usa e getta, favorendo le startup veloci per aumentare le opportunità di scalabilità e gli arresti normali per lasciare il sistema in uno stato corretto. I contenitori Docker insieme a un agente di orchestrazione soddisfano intrinsecamente questo requisito. |
| 10 | Parità Sviluppo/Prod | Mantenere gli ambienti durante il ciclo di vita dell'applicazione nel modo più simile possibile, evitando costose scorciatoie. In questo caso, l'adozione di contenitori può contribuire notevolmente promuovendo lo stesso ambiente di esecuzione. |
| 11 | Registrazione | Considerare i log generati dai microservizi come flussi di eventi. Elaborarli con un aggregatore di eventi e propagare i dati agli strumenti di data mining/gestione dei log come Monitoraggio di Azure o Splunk ed eventualmente all'archiviazione a lungo termine. |
| 12 | Processi amministrativi | Eseguire attività amministrative/di gestione come processi una tantum. Le attività possono includere la pulizia dei dati e il pull dell'analisi per un report. Gli strumenti che eseguono queste attività devono essere richiamati dall'ambiente di produzione, ma separatamente dall'applicazione. |

Nel libro, [Beyond the Twelve-Factor App , l'autore](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)Kevin Hoffman descrive in dettaglio ciascuno dei 12 fattori originali (scritto nel 2011). Inoltre, il libro fornisce tre fattori aggiuntivi che riflettono la progettazione di applicazioni cloud moderna di oggi.

|    |  Nuovo fattore | Spiegazione  |
| :-------- | :-------- | :-------- |
| 13 | Prima API | Rendere tutto un servizio. Si supponga che il codice verrà utilizzato da un client front-end, gateway o un altro servizio. |
| 14 | Telemetria | In una workstation, si ha una visibilità approfondita dell'applicazione e del relativo comportamento. Nel cloud, non è vero. Assicurarsi che il progetto includa la raccolta di dati di monitoraggio, specifici del dominio e integrità/sistema. |
| 15 | Autenticazione/Autorizzazione  | Implementare l'identità dall'inizio. Prendere in considerazione le funzionalità RBAC (controllo degli [accessi in base](https://docs.microsoft.com/azure/role-based-access-control/overview) al ruolo) disponibili nei cloud pubblici.  |

Ci riferiremo a molti dei 12 fattori in questo capitolo e in tutto il libro.

### <a name="critical-design-considerations"></a>Considerazioni critiche sulla progettazione

Oltre alle indicazioni fornite dalla metodologia a dodici fattori, è necessario prendere diverse decisioni di progettazione critiche durante la costruzione di sistemi distribuiti.

*Comunicazione*

In che modo le applicazioni client front-end comunicheranno con i servizi core back-end? Consentirete la comunicazione diretta? Oppure, è possibile astrarre i servizi back-end con una facciata gateway che offre flessibilità, controllo e sicurezza?

In che modo i servizi principali back-end comunicheranno tra loro? Consentire le chiamate HTTP dirette che portano all'accoppiamento e influiscono sulle prestazioni e sull'agilità? O si potrebbe prendere in considerazione la messaggistica disaccoppiata con le tecnologie di coda e argomento?

La comunicazione è trattata in dettaglio Capitolo 4, Modelli di *comunicazione cloud-nativi*.

*Resilienza*

Un'architettura di microservizi sposta il sistema dalla comunicazione in-process alla comunicazione di rete. In un ambiente distribuito, cosa fare quando il servizio B non risponde a una chiamata dal servizio A? Cosa succede quando il servizio C diventa temporaneamente non disponibile e altri servizi che lo chiamano stack e riducono le prestazioni del sistema?

La resilienza è trattata in dettaglio Capitolo 6, *Resilienza nativa cloud*.

*Dati distribuiti*

Per impostazione specifica, ogni microservizio incapsula i propri dati, esponendo le operazioni tramite la relativa interfaccia pubblica. In caso affermativo, come si esegue una query sui dati o si implementa una transazione tra più servizi?

I dati distribuiti vengono trattati nel dettaglio Capitolo 5, Modelli di *dati cloud-nativi*.

*Identità*

In che modo il servizio identificherà chi vi accede e quali autorizzazioni hanno?

L'identità è trattata nel dettaglio Capitolo 8, *Identità*.

## <a name="microservices"></a>Microservizi

I sistemi nativi del cloud adottano microservizi, uno stile architettonico popolare per la costruzione di applicazioni moderne.

Creati come un set distribuito di servizi di piccole dimensioni e indipendenti che interagiscono tramite un'infrastruttura condivisa, i microservizi condividono le caratteristiche seguenti:Built as a distributed set of small, independent services that interact through a shared fabric, microservices share the following characteristics:

- Ognuno implementa una funzionalità aziendale specifica all'interno di un contesto di dominio più ampio.

- Ognuno è sviluppato in modo autonomo e può essere distribuito in modo indipendente.

- Ognuna è autonomamente incapsulando la propria tecnologia di archiviazione dei dati (SQL, NoSQL) e la piattaforma di programmazione.

- Ognuno viene eseguito nel proprio processo e comunica con gli altri utilizzando protocolli di comunicazione standard come HTTP/HTTPS, WebSockets o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).

- Compongono insieme per formare una domanda.

Figura 1-4 confronta un approccio applicazione monolitico con un approccio di microservizi. Si noti come il monolite è composto da un'architettura a più livelli, che viene eseguita in un unico processo. In genere utilizza un database relazionale. L'approccio microservizio, tuttavia, separa le funzionalità in servizi indipendenti che includono logica e dati. Ogni microservizio ospita il proprio archivio dati.

![Distribuzione monolitica rispetto ai microservizi](./media/monolithic-vs-microservices.png)

**Figura 1-4.** Distribuzione monolitica rispetto ai microservizi

Si noti come i microservizi promuovano il principio "One Codebase, One Application" [dall'applicazione a dodici](https://12factor.net/)fattori , illustrato in precedenza nel capitolo.

> *Fattore \#1 specifica "Una singola codebase per ogni microservizio, archiviato nel proprio repository. Tracciato con il controllo della versione, può essere distribuito in più ambienti."*

### <a name="why-microservices"></a>Perché usare i microservizi?

I microservizi offrono agilità.

All'inizio del capitolo, abbiamo confrontato un'applicazione di e-commerce costruita come monolite a quella con i microservizi. Nell'esempio, abbiamo visto alcuni vantaggi chiari:

- Ogni microservizio ha un ciclo di vita autonomo e può evolvere in modo indipendente e distribuirlo frequentemente. Non è necessario attendere una versione trimestrale per distribuire una nuova funzionalità o un aggiornamento. È possibile aggiornare una piccola area di un'applicazione complessa con meno rischi di interrompere l'intero sistema.

- Ogni microservizio può essere scalato in modo indipendente. Anziché ridimensionare l'intera applicazione come singola unità, si aumenta la scalabilità orizzontale solo dei servizi che richiedono maggiore potenza di elaborazione o larghezza di banda di rete. Questo approccio granulare alla scalabilità consente un maggiore controllo del sistema e consente di ridurre i costi complessivi durante la scalabilità di parti del sistema, non di tutto.

Un'eccellente guida di riferimento per comprendere i microservizi è [.NET Microservices: Architecture for Containerized Applications .](https://docs.microsoft.com/dotnet/standard/microservices-architecture/) Il libro a pvence la progettazione e l'architettura dei microservizi. È un compagno per [un'architettura di riferimento microservizio full-stack](https://github.com/dotnet-architecture/eShopOnContainers) disponibile come download gratuito da Microsoft.

### <a name="developing-microservices"></a>Sviluppo di microservizi

I microservizi possono essere creati con qualsiasi piattaforma di sviluppo moderna.

La piattaforma Microsoft .NET Core è una scelta eccellente. Gratuito e open source, ha molte funzionalità integrate per semplificare lo sviluppo di microservizi. .NET Core è multipiattaforma. Le applicazioni possono essere create ed eseguite su Windows, macOS e la maggior parte dei sapori di Linux.

.NET Core è altamente performante e ha ottenuto un buon punteggio rispetto a Node.js e ad altre piattaforme concorrenti. È interessante notare che [TechEmpower](https://www.techempower.com/) ha condotto una vasta gamma di [benchmark di prestazioni](https://www.techempower.com/benchmarks/#section=data-r17&hw=ph&test=plaintext) in molte piattaforme e framework di applicazioni web. .NET Core ha segnato nella top 10 - ben al di sopra di Node.js e di altre piattaforme concorrenti.

.NET Core è gestito da Microsoft e dalla community .NET su GitHub..NET Core is maintained by Microsoft and the .NET community on GitHub.

## <a name="containers"></a>Contenitori

Al giorno d'oggi, è naturale sentire il *termine contenitore* menzionato in qualsiasi conversazione riguardante *cloud nativo*. Nel libro, [Cloud Native Patterns](https://www.manning.com/books/cloud-native-patterns), l'autrice Cornelia Davis osserva che "I contenitori sono un grande abilitatore del software cloud-nativo." La Cloud Native Computing Foundation pone la containerizzazione dei microservizi come primo passo nella mappa [Cloud-Native Trail:](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) guida per le aziende che iniziano il loro percorso cloud-native.

La containerizzazione di un microservizio è semplice e semplice. Il codice, le relative dipendenze e il runtime vengono inclusi in un file binario denominato [immagine del contenitore.](https://docs.docker.com/glossary/?term=image) Le immagini vengono archiviate in un [registro contenitori](https://caylent.com/container-registries/), che funge da repository o libreria per le immagini. Un registro può essere posizionato nel computer di sviluppo, nel data center o in un cloud pubblico. Docker stesso gestisce un registro pubblico tramite [Docker Hub](https://hub.docker.com/). Il cloud di Azure include un [registro contenitori](https://azure.microsoft.com/services/container-registry/) per archiviare le immagini del contenitore vicino alle applicazioni cloud che le eseguiranno.

Quando necessario, si trasforma l'immagine in un'istanza del contenitore in esecuzione. L'istanza viene eseguita in qualsiasi computer in cui è installato un motore [di runtime del contenitore.](https://kubernetes.io/docs/setup/production-environment/container-runtimes/) È possibile avere tutte le istanze del servizio containerizzato in base alle esigenze.

La figura 1-5 mostra tre diversi microservizi, ognuno nel proprio contenitore, in esecuzione su un singolo host.

![Più contenitori in esecuzione in un host contenitore](./media/hosting-mulitple-containers.png)

**Figura 1-5**. Più contenitori in esecuzione in un host contenitore

Si noti come ogni contenitore gestisce il proprio set di dipendenze e runtime, che può essere diverso. Qui vediamo diverse versioni del microservizio Product in esecuzione sullo stesso host. Ogni contenitore condivide una sezione del sistema operativo, della memoria e del processore dell'host sottostante, ma è isolato l'uno dall'altro.

Si noti quanto bene il modello di contenitore abbraccia il principio "Dipendenze" [dall'applicazione a dodici](https://12factor.net/)fattori .

> *Fattore \#2 specifica che "Ogni microservizio isola e mballile proprie dipendenze, abbracciando le modifiche senza influire sull'intero sistema."*

I contenitori supportano carichi di lavoro Linux e Windows.Containers support both Linux and Windows workloads. Il cloud di Azure abbraccia apertamente entrambi. È interessante notare che, è Linux, non Windows Server, che è diventato il sistema operativo più popolare in Azure.

Mentre esistono diversi venditori di container, Docker ha catturato la parte del leone del mercato. L'azienda ha guidato il movimento del contenitore software. È diventato lo standard de facto per la creazione di pacchetti, la distribuzione e l'esecuzione di applicazioni cloud native.

### <a name="why-containers"></a>Perché i contenitori?

I contenitori garantiscono la portabilità e garantiscono la coerenza tra gli ambienti. Incapsulando tutti gli elementi in un singolo pacchetto, si *isola* il microservizio e le relative dipendenze dall'infrastruttura sottostante.

È possibile distribuire lo stesso contenitore in qualsiasi ambiente che dispone del motore di runtime Docker.You can deploy that same container in any environment that has the Docker runtime engine. I carichi di lavoro containerizzati eliminano inoltre i costi di preconfigurazione di ogni ambiente con framework, librerie software e motori di runtime.

Condividendo il sistema operativo sottostante e le risorse host, i contenitori hanno un footprint molto più piccolo rispetto a una macchina virtuale completa. Le dimensioni inferiori aumentano la *densità*o il numero di microservizi che un determinato host può eseguire contemporaneamente.

### <a name="container-orchestration"></a>Orchestrazione dei contenitori

Mentre strumenti come Docker creano immagini ed eseguono contenitori, sono necessari anche strumenti per gestirli. La gestione dei contenitori viene eseguita con un programma software speciale denominato orchestratore contenitore. Quando si opera su larga scala, l'orchestrazione del contenitore è essenziale.

Nella figura 1-6 vengono illustrate le attività di gestione fornite dagli orchestratori di contenitori.

![Cosa fanno gli orchestratori di contenitoriWhat container orchestrators do](./media/what-container-orchestrators-do.png)

**Figura 1-6**. Cosa fanno gli orchestratori di contenitoriWhat container orchestrators do

Nella tabella seguente vengono descritte le attività di orchestrazione comuni.

|  Attività | Spiegazione  |
| :-------- | :-------- |
| Pianificazione | Eseguire automaticamente il provisioning delle istanze del contenitore.|
| Affinità/anti-affinità | Effettua il provisioning di contenitori vicini o distanti l'uno dall'altro, aiutando la disponibilità e le prestazioni. |
| Monitoraggio dell’integrità | Rilevare e correggere automaticamente gli errori.|
| Failover | Eseguire automaticamente il provisioning dell'istanza non riuscita su macchine integre.|
| Scalabilità | Aggiungere o rimuovere automaticamente l'istanza del contenitore per soddisfare la domanda.|
| Rete | Gestire una sovrapposizione di rete per la comunicazione del contenitore.|
| Individuazione dei servizi | Consentire ai contenitori di individuarsi a vicenda.|
| Aggiornamenti in sequenza | Coordinare gli aggiornamenti incrementali senza alcuna distribuzione dei tempi di inattività. Eseguire automaticamente il rollback delle modifiche problematiche.|

Si noti come gli agenti di orchestrazione adottino i principi di eliminazione e concorrenza [dall'applicazione](https://12factor.net/)a dodici fattori , illustrati in precedenza nel capitolo.

> *Il \#fattore 9 specifica che "Le istanze del servizio devono essere eliminabili, favorendo gli avvii veloci per aumentare le opportunità di scalabilità e gli arresti normali per lasciare il sistema in uno stato corretto. I contenitori Docker insieme a un agente di orchestrazione soddisfano intrinsecamente questo requisito."*

> *Fattore \#8 specifica che "I servizi scalabili a un numero elevato di piccoli processi identici (copie) anziché scalabilità verticale di una singola istanza di grandi dimensioni nel computer più potente disponibile."*

Mentre esistono diversi orchestratori di container, [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) è diventato lo standard de facto per il mondo nativo del cloud. È una piattaforma aperta portatile, estensibile e open source per la gestione dei carichi di lavoro containerizzati.

Potresti ospitare la tua istanza di Kubernetes, ma poi saresti responsabile del provisioning e della gestione delle sue risorse, il che può essere complesso. Il cloud di Azure include Kubernetes come servizio gestito, [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). Un servizio gestito consente di sfruttare appieno le sue funzionalità, senza doverlo installare e gestire.

Servizi di Azure Kubernetes è descritto in dettaglio Capitolo 2, *Scalabilità*di applicazioni native cloud .

## <a name="backing-services"></a>Servizi di backup

I sistemi nativi nel cloud dipendono da molte risorse ausiliarie diverse, ad esempio archivi dati, broker di messaggi, monitoraggio e servizi di identità. Questi servizi sono noti come [servizi di backup](https://12factor.net/backing-services).

 Figura 1-7 Mostra molti servizi di backup comuni che i sistemi nativi cloud utilizzano.

![Servizi di backup comuni](./media/common-backing-services.png)

**Figura 1-7**. Servizi di backup comuni

I servizi di sostegno promuovono il principio dell'"apolidia" dalla domanda a [dodici fattori,](https://12factor.net/)discusso in precedenza nel capitolo.

>*Fattore \#6* specifica che, "Ogni microservizio deve essere eseguito nel proprio processo, isolato da altri servizi in esecuzione. Esternalizzare lo stato richiesto a un servizio di backup, ad esempio una cache distribuita o un archivio dati."

È possibile ospitare i propri servizi di backup, ma in questo modo si sarebbe responsabile delle licenze, del provisioning e della gestione di tali risorse.

I provider di servizi cloud offrono un ricco assortimento di servizi di *backup gestiti.* Invece di possedere il servizio, è sufficiente consumarlo. Il fornitore gestisce la risorsa su larga scala e si assume la responsabilità delle prestazioni, della sicurezza e della manutenzione. Il monitoraggio, la ridondanza e la disponibilità sono incorporati nel servizio. I provider supportano completamente i loro servizi gestiti- apri un ticket e risolviil problema.

I sistemi nativi del cloud favoriscono i servizi di supporto gestiti dei fornitori di cloud. I risparmi in tempo e di lavoro sono grandi. Il rischio operativo di ospitare il proprio e di avere problemi può diventare costoso veloce.

Una procedura consigliata consiste nel considerare un servizio di supporto come una *risorsa associata,* associata in modo dinamico a un microservizio con informazioni (un URL e credenziali) archiviate in una configurazione esterna. Questa guida è descritta [nell'Applicazione](https://12factor.net/)a dodici fattori , descritta in precedenza nel capitolo.

>*Il \#fattore 4* specifica che i servizi di backup "devono essere esposti tramite un URL indirizzabile. In questo modo la risorsa viene disaccoppiata dall'applicazione, consentendone l'intercambiabile."

>*Il \#fattore 3* specifica che "Le informazioni di configurazione vengono spostate all'esterno del microservizio e esterne tramite uno strumento di gestione della configurazione esterno al codice".

Con questo modello, un servizio di backup può essere collegato e scollegato senza modifiche al codice. È possibile promuovere un microservizio dal controllo di controllo di accesso generale a un ambiente di gestione temporanea. Aggiornare la configurazione del microservizio in modo che punti ai servizi di backup nella gestione temporanea e inserire le impostazioni nel contenitore tramite una variabile di ambiente.

I fornitori di cloud forniscono API per comunicare con i servizi di supporto proprietari. Queste librerie incapsulano l'impianto idraulico e la complessità. Comunicare direttamente con queste API accoppia il codice al servizio di backup. È consigliabile isolare i dettagli di implementazione dell'API del fornitore. Introdurre un livello di intermediazione o un'API intermedia, esponendo operazioni generiche al codice del servizio. Questo accoppiamento libero consente di scambiare un servizio di backup per un altro o spostare il codice in un cloud pubblico diverso senza dover apportare modifiche al codice del servizio principale.

I servizi di supporto sono descritti in dettaglio Capitolo 5, Modelli di *dati cloud-nativi*e Capitolo 4, Modelli di *comunicazione cloud-nativi*.

## <a name="automation"></a>Automazione

Come hai visto, i sistemi nativi del cloud adottano microservizi, contenitori e progettazione di sistemi moderni per ottenere velocità e agilità. Ma, questa è solo una parte della storia. Come si esegue il provisioning degli ambienti cloud in cui vengono eseguiti questi sistemi? Come si distribuiscono rapidamente le funzionalità e gli aggiornamenti delle app? Come si completa il quadro completo?

Immettere la pratica ampiamente accettata di [infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), o IaC.

Con IaC, è possibile automatizzare il provisioning della piattaforma e la distribuzione delle applicazioni. Si applicano essenzialmente procedure di progettazione software, ad esempio test e controllo delle versioni, alle procedure DevOps. L'infrastruttura e le distribuzioni sono automatizzate, coerenti e ripetibili.

### <a name="automating-infrastructure"></a>Automazione dell'infrastruttura

Strumenti come [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/), Terraform e l'interfaccia della riga di comando di [Azure](https://docs.microsoft.com/cli/azure/)consentono di creare script in modo dichiarativo dell'infrastruttura cloud necessaria. I nomi, le posizioni, le capacità e i segreti delle risorse sono con parametri e dinamici. Lo script viene sottoposto a controllo delle versioni e archiviato nel controllo del codice sorgente come elemento del progetto. Si richiama lo script per eseguire il provisioning di un'infrastruttura coerente e ripetibile tra ambienti di sistema, ad esempio QA, gestione temporanea e produzione.

Sotto il cofano, IaC è idempotente, il che significa che è possibile eseguire lo stesso script più e più volte senza effetti collaterali. Se il team deve apportare una modifica, modifica ed esegue nuovamente lo script. Sono interessate solo le risorse aggiornate.

Nell'articolo [What is Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), l'autore Sam Guckenheimer descrive come,Team che implementano IaC in grado di fornire ambienti stabili in modo rapido e su larga scala. I team evitano la configurazione manuale degli ambienti e applicano la coerenza rappresentando lo stato desiderato dei propri ambienti tramite codice. Le distribuzioni dell'infrastruttura con IaC sono ripetibili e prevengono problemi di runtime causati da deriva della configurazione o dipendenze mancanti. I team DevOps possono collaborare con un insieme unificato di procedure e strumenti per distribuire le applicazioni e la relativa infrastruttura di supporto in modo rapido, affidabile e su larga scala."

### <a name="automating-deployments"></a>Automazione delle distribuzioni

[L'applicazione](https://12factor.net/)a dodici fattori , descritta in precedenza, richiede passaggi separati durante la trasformazione del codice completato in un'applicazione in esecuzione.

> *Fattore \#5* specifica che "Ogni versione deve imporre una separazione rigorosa tra le fasi di compilazione, rilascio ed esecuzione. Ognuno deve essere contrassegnato con un ID univoco e supportare la possibilità di eseguire il rollback."

I moderni sistemi CI/CD contribuiscono a soddisfare questo principio. Forniscono passaggi di distribuzione separati e contribuiscono a garantire codice coerente e di qualità che sia prontamente disponibile per gli utenti.

Figura 1-8 Mostra la separazione tra il processo di distribuzione.

![Passaggi di distribuzione in UNA pipeline CI/CD](./media/build-release-run-pipeline.png)

**Figura 1-8**. Passaggi di distribuzione in una pipeline CI/CD

Nella figura precedente, prestare particolare attenzione alla separazione dei compiti.

Lo sviluppatore costruisce una funzionalità nel proprio ambiente di sviluppo, scorrendo il cosiddetto "ciclo interno" del codice, dell'esecuzione e del debug. Al termine, tale codice viene *inserito* in un repository di codice, ad esempio GitHub, DevOps di Azure o BitBucket.When complete, that code is pushed into a code repository, such as GitHub, Azure DevOps, or BitBucket.

Il push attiva una fase di compilazione che trasforma il codice in un elemento binario. Il lavoro viene implementato con una pipeline di [integrazione continua (CI).](https://martinfowler.com/articles/continuousIntegration.html) Compila, testa e crea automaticamente pacchetti all'applicazione.

La fase di rilascio preleva l'elemento binario, applica le informazioni di configurazione dell'applicazione e dell'ambiente esterno e produce una versione non modificabile. Il rilascio viene distribuito in un ambiente specificato. Il lavoro viene implementato con una pipeline [di recapito continuo (CD).](https://martinfowler.com/bliki/ContinuousDelivery.html) Ogni versione deve essere identificabile. È possibile dire, "Questa distribuzione è in esecuzione la versione 2.1.1 dell'applicazione."

Infine, la funzionalità rilasciata viene eseguita nell'ambiente di esecuzione di destinazione. I rilasci non sono modificabili, il che significa che qualsiasi modifica deve creare una nuova versione.

Applicando queste pratiche, le organizzazioni si sono radicalmente evolute nel modo in cui spediscono il software. Molti sono passati dalle versioni trimestrali agli aggiornamenti su richiesta. L'obiettivo è quello di catturare i problemi all'inizio del ciclo di sviluppo quando sono meno costosi da risolvere. Più lunga è la durata tra le integrazioni, più costosi saranno i problemi da risolvere.  Con la coerenza nel processo di integrazione, i team possono eseguire il commit delle modifiche al codice più frequentemente, migliorando la collaborazione e la qualità del software.

### <a name="azure-pipelines"></a>Azure Pipelines

Il cloud di Azure include un nuovo servizio CI/CD intitolato [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/), che fa parte dell'offerta [DevOps](https://azure.microsoft.com/services/devops/) di Azure illustrata nella Figura 1-9.

![Azure Pipelines in DevOps](./media/devops-components.png)

**Figura 1-9**. Offerte DevOps di AzureAzure DevOps offerings

Pipeline di Azure è un servizio cloud che combina l'integrazione continua (CI) e la distribuzione continua (CD). È possibile testare, compilare e spedire automaticamente il codice a qualsiasi destinazione.

La pipeline viene definita nel codice in un file YAML insieme al resto del codice per l'app.

- La pipeline viene sottoposta a controllo delle versioni con il codice e segue la stessa struttura di diramazione.
- Si ottiene la convalida delle modifiche tramite revisioni del codice nelle richieste pull e nei criteri di compilazione del ramo.
- Ogni ramo usato può personalizzare i criteri di compilazione modificando il file azure-pipelines.yml.
- Il file della pipeline viene archiviato nel controllo della versione e può essere analizzato se si verifica un problema.

Il servizio Pipeline di Azure supporta la maggior parte dei provider Git e può generare pipeline di distribuzione per le applicazioni scritte nelle piattaforme Linux, macOS o Windows.The Azure Pipelines service supports most Git providers and can generate deployment pipelines for applications written on the Linux, macOS, or Windows platforms. Include il supporto per Java, .NET, JavaScript, Python, PHP, Go, XCode, e C .

>[!div class="step-by-step"]
>[Successivo](introduction.md)
>[precedente](candidate-apps.md)
