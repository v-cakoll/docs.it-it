---
title: Definizione di cloud nativo
description: Informazioni sui pilastri fondamentali che forniscono il fondamento per i sistemi nativi del cloud
author: robvet
ms.date: 08/20/2019
ms.openlocfilehash: 33977ff736fc5cbfcf86ed6479e8d0b927b87a63
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895610"
---
# <a name="defining-cloud-native"></a>Definizione del cloud nativo

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Interrompi le operazioni e il testo di dieci dei tuoi colleghi. Chiedere loro di definire il termine "cloud native". La possibilità di ottenere otto risposte diverse.

Il cloud nativo sta per cambiare il modo in cui si pensa alla costruzione di sistemi aziendali critici.

I sistemi nativi del cloud sono progettati per adottare modifiche rapide, scalabilità elevata e resilienza.

Cloud native Computing Foundation fornisce una [definizione ufficiale](https://github.com/cncf/foundation/blob/master/charter.md):

> *Le tecnologie native del cloud consentono alle organizzazioni di creare ed eseguire applicazioni scalabili in ambienti dinamici moderni, ad esempio cloud pubblici, privati e ibridi. I contenitori, le mesh dei servizi, i microservizi, l'infrastruttura non modificabile e le API dichiarative esemplificano questo approccio.*

> *Queste tecniche consentono sistemi a regime di controllo libero, resilienti, gestibili e osservabili. Combinati con un'automazione affidabile, consentono ai tecnici di apportare modifiche a un elevato livello di frequenza e prevedibili con una fatica minima.*

Le applicazioni sono diventate sempre più complesse con gli utenti che ne richiedono sempre di più. Gli utenti si aspettano velocità di risposta rapida, funzionalità innovative e nessun tempo di inattività. I problemi di prestazioni, gli errori ricorrenti e l'impossibilità di muoversi velocemente non sono più accettabili. Si passerà facilmente al tuo concorrente.

Cloud native è molto su *velocità* e *agilità*. I sistemi aziendali si evolvono dall'abilitazione di funzionalità aziendali a armi di trasformazione strategica, accelerando la velocità e la crescita dell'azienda. È fondamentale ottenere immediatamente le idee sul mercato.

Di seguito sono riportate alcune società che hanno implementato queste tecniche. Valutare la velocità, l'agilità e la scalabilità configurate.

| Company | Esperienza |
| :-------- | :-------- |
| [Netflix](https://www.infoq.com/news/2013/06/netflix/) | In produzione sono presenti oltre 600 servizi. Distribuisce centinaia di volte al giorno. |
| [Uber](https://eng.uber.com/micro-deploy/) | In produzione sono presenti oltre 1000 servizi. Distribuisce diverse migliaia di volte ogni settimana. |
| [WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf) | In produzione sono presenti 300 servizi. Distribuisce 1.000 volte al giorno. |

Come si può vedere, Netflix, Uber e WeChat espongono sistemi costituiti da centinaia di microservizi indipendenti. Questo stile di architettura consente loro di rispondere rapidamente alle condizioni di mercato. Possono aggiornare immediatamente piccole aree di un'applicazione dinamica e complessa e ridimensionare singolarmente le aree in base alle esigenze.

La velocità e l'agilità del cloud nativo derivano da diversi fattori. Il primo è l'infrastruttura cloud. Cinque pilastri fondamentali aggiuntivi illustrati nella figura 1-3 forniscono anche il fondamento per i sistemi nativi del cloud.

![Pilastri di base nativi del cloud](./media/cloud-native-foundational-pillars.png)

**Figura 1-3**. Pilastri di base nativi del cloud

Per comprendere meglio il significato di ogni pilastro,

## <a name="the-cloud"></a>Il cloud...

I sistemi nativi del Cloud sfruttano al meglio il modello del servizio cloud.

Progettato per prosperare in un ambiente cloud virtualizzato e dinamico, questi sistemi fanno ampio uso dell'infrastruttura di calcolo [PaaS (Platform as a Service)](https://azure.microsoft.com/overview/what-is-paas/) e dei servizi gestiti. Gestiscono l'infrastruttura sottostante come con provisioning *Disposable* in pochi minuti e ridimensionato, ridimensionato, spostato o eliminato su richiesta, tramite l'automazione.

Prendere in considerazione il concetto di DevOps di [animali domestici e bestiame](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313)ampiamente accettato. In una data center tradizionale, i server vengono considerati come *animali domestici*: un computer fisico, dato un nome significativo e curato. Per la scalabilità, è possibile aggiungere altre risorse allo stesso computer (scalabilità verticale). Se il server si ammala, è necessario invitarlo di nuovo all'integrità. Se il server non è più disponibile, tutti gli avvisi.

Il modello del servizio *bestiame* è diverso. Si esegue il provisioning di ogni istanza come macchina virtuale o contenitore. Sono identici e vengono assegnati a un identificatore di sistema, ad esempio Service-01, Service-02 e così via. La scalabilità viene eseguita creandone più di una (scalabilità orizzontale). Quando una non è più disponibile, nessuno lo rileva.

Il modello di bestiame abbraccia l' *infrastruttura non modificabile*. I server non vengono ripristinati o modificati. Se si verifica un errore o se è necessario un aggiornamento, questo viene eliminato e ne viene eseguito il provisioning, il tutto con l'automazione.

I sistemi nativi del cloud adottano il modello di servizio bestiame. Continuano a funzionare con l'infrastruttura di scalabilità orizzontale o orizzontale senza considerare i computer su cui sono in esecuzione.

La piattaforma cloud di Azure supporta questo tipo di infrastruttura estremamente elastica con funzionalità di ridimensionamento automatico, correzione automatica e monitoraggio.

## <a name="modern-design"></a>Progettazione moderna

Come progettare un'app nativa del cloud? Come dovrebbe apparire l'architettura? Quali sono i principi, i modelli e le procedure consigliate da rispettare? Quali sono le problematiche di infrastruttura e operativa?

### <a name="the-twelve-factor-application"></a>Applicazione a dodici fattori

Una metodologia ampiamente accettata per la creazione di applicazioni basate sul cloud è l' [applicazione a dodici fattori](https://12factor.net/). Viene descritto un set di principi e procedure che gli sviluppatori seguono per costruire applicazioni ottimizzate per ambienti cloud moderni. Viene fornita particolare attenzione alla portabilità tra ambienti e automazione dichiarativa.

Sebbene sia applicabile a qualsiasi applicazione basata su Web, molti professionisti lo considerano come fondamenta solide per la creazione di app native del cloud. I sistemi basati su questi principi possono distribuire e ridimensionare rapidamente e aggiungere funzionalità per rispondere rapidamente alle modifiche del mercato.

Nella tabella seguente viene evidenziata la metodologia a dodici fattori:

|    |  Fattore | Spiegazione  |
| :-------- | :-------- | :-------- |
| 1 | Codebase | Una singola codebase per ogni microservizio, archiviato nel proprio repository. Con il controllo della versione, è possibile eseguire la distribuzione in più ambienti (QA, staging, produzione). |
| 2 | Dipendenze | Ogni microservizio isola e impacchetta le proprie dipendenze, accettando le modifiche senza alcun effetto sull'intero sistema. |
| 3 | Configurazioni  | Le informazioni di configurazione vengono spostate al di fuori del microservizio ed esternalizzate tramite uno strumento di gestione della configurazione all'esterno del codice. La stessa distribuzione può propagarsi tra gli ambienti con la configurazione corretta applicata.  |
| 4 | Servizi di supporto | Le risorse ausiliarie (archivi dati, cache, broker di messaggi) devono essere esposte tramite un URL indirizzabile. Questa operazione separa la risorsa dall'applicazione, consentendo l'interscambiabilità.  |
| 5 | Compilazione, versione, esecuzione | Ogni versione deve applicare una rigorosa separazione tra le fasi di compilazione, rilascio ed esecuzione. Ogni deve essere contrassegnato con un ID univoco e supportare la possibilità di eseguire il rollback. I sistemi di integrazione continua/recapito continuo moderni contribuiscono a soddisfare questo principio. |
| 6 | Processi | Ogni microservizio deve essere eseguito in un processo distinto, isolato da altri servizi in esecuzione. Externalize lo stato richiesto a un servizio di supporto, ad esempio una cache distribuita o un archivio dati. |
| 7 | Binding porta | Ogni microservizio deve essere autonomo con le interfacce e le funzionalità esposte sulla relativa porta. In questo modo viene fornito l'isolamento da altri microservizi. |
| 8 | Concorrenza | I servizi vengono scalati orizzontalmente in un numero elevato di processi identici (copie) identici rispetto alla scalabilità verticale di una singola istanza large nel computer più potente disponibile. |
| 9 | Disponibilità | Le istanze del servizio devono essere eliminate, prediligendo le startup veloci per aumentare le opportunità di scalabilità e gli arresti normali per lasciare il sistema in uno stato corretto. I contenitori Docker insieme a un agente di orchestrazione soddisfano intrinsecamente questo requisito. |
| 10 | Parità sviluppo/prod | Mantieni gli ambienti nel ciclo di vita dell'applicazione nel modo più simile possibile, evitando costosi collegamenti. In questo caso, l'adozione di contenitori può contribuire significativamente con la promozione dello stesso ambiente di esecuzione. |
| 11 | Registrazione | Considera i log generati dai microservizi come flussi di eventi. È possibile elaborarli con un aggregatore di eventi e propagarli a strumenti di gestione dei log e di data mining quali monitoraggio di Azure o Splunk e infine l'archiviazione a lungo termine. |
| 12 | Processi amministrativi | Eseguire attività amministrative/di gestione come processi unidirezionali. Le attività possono includere la pulizia dei dati e il pull delle analisi per un report. Gli strumenti che eseguono queste attività devono essere richiamati dall'ambiente di produzione, ma separatamente dall'applicazione. |

Nel libro, [oltre all'app a dodici](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)fattori, l'autore Kevin Hoffman Details ognuno dei 12 fattori originali (scritti in 2011). Inoltre, il libro offre tre fattori aggiuntivi che riflettono la progettazione di applicazioni cloud moderne di oggi.

|    |  Nuovo fattore | Spiegazione  |
| :-------- | :-------- | :-------- |
| 13 | API First | Rendere tutto un servizio. Si supponga che il codice venga utilizzato da un client front-end, un gateway o un altro servizio. |
| 14 | Telemetria | In una workstation è possibile ottenere visibilità approfondita dell'applicazione e del relativo comportamento. Nel cloud non è necessario. Assicurarsi che la progettazione includa la raccolta di dati di monitoraggio, specifici del dominio e integrità/sistema. |
| 15 | Autenticazione/autorizzazione  | Implementare l'identità dall'inizio. Prendere in considerazione le funzionalità [RBAC (controllo degli accessi in base al ruolo)](https://docs.microsoft.com/azure/role-based-access-control/overview) disponibili nei cloud pubblici.  |

Si farà riferimento a molti dei 12 fattori più importanti in questo capitolo e nel corso del libro.

### <a name="critical-design-considerations"></a>Considerazioni di progettazione critiche

Oltre alle linee guida fornite dalla metodologia a dodici fattori, è necessario prendere alcune decisioni di progettazione cruciali quando si costruiscono sistemi distribuiti.

*Comunicazione*

In che modo le applicazioni client front-end comunicano con i servizi Core back-end? Si consente la comunicazione diretta? In alternativa, è possibile astrarre i servizi back-end con una facciata del gateway che fornisce flessibilità, controllo e sicurezza?

In che modo i servizi di base back-end comunicano tra loro? Si consentiranno chiamate HTTP dirette che possono compromettere le prestazioni e l'agilità? Oppure si può prendere in considerazione la messaggistica disaccoppiata con le tecnologie di Accodamento e di argomento?

La comunicazione è illustrata in dettaglio nel capitolo 4, *modelli di comunicazione nativi del cloud*.

*Resilienza*

Un'architettura di microservizi sposta il sistema da in-process a comunicazioni di rete out-of-process. In un'architettura distribuita, cosa accade quando il servizio B non risponde a una chiamata di rete dal servizio A? In alternativa, cosa accade quando il servizio C diventa temporaneamente non disponibile e altri servizi che la chiamano sono bloccati?

La resilienza è illustrata in dettaglio nel capitolo 6 sulla *resilienza nativa del cloud*.

*Dati distribuiti*

Per impostazione predefinita, ogni microservizio incapsula i propri dati, esponendo le operazioni tramite la relativa interfaccia pubblica. In tal caso, come si esegue una query sui dati o si implementa una transazione tra più servizi?

I dati distribuiti sono trattati nei dettagli del capitolo 5, *modelli di dati nativi del cloud*.

*Identità*

In che modo il servizio identificherà chi vi accede e quali autorizzazioni hanno?

L'identità è illustrata in dettaglio capitolo 8, *identità*.

## <a name="microservices"></a>Microservizi

I sistemi nativi del cloud comprendono i microservizi, uno stile di architettura diffuso per la creazione di applicazioni moderne.

Progettato come un set distribuito di piccoli servizi indipendenti che interagiscono attraverso un'infrastruttura condivisa, i microservizi condividono le caratteristiche seguenti:

- Ogni implementa una funzionalità aziendale specifica all'interno di un contesto di dominio più grande.

- Ogni viene sviluppato in modo autonomo e può essere distribuito in modo indipendente.

- Ognuno di essi è indipendente dall'incapsulamento della propria tecnologia di archiviazione dati (SQL, NoSQL) e della piattaforma di programmazione.

- Ogni viene eseguito in un processo e comunica con altri usando protocolli di comunicazione standard, ad esempio HTTP/HTTPS, WebSocket o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).

- Si compongono insieme per formare un'applicazione.

La figura 1-4 contrasta l'approccio di un'applicazione monolitica con un approccio basato su microservizi. Si noti che il monolito è costituito da un'architettura a più livelli, che viene eseguita in un singolo processo. Viene in genere utilizzato un database relazionale. L'approccio basato su microservizi, tuttavia, separa le funzionalità in servizi indipendenti che includono la logica e i dati. Ogni microservizio ospita il proprio archivio dati.

![Distribuzione monolitica rispetto ai microservizi](./media/monolithic-vs-microservices.png)

**Figura 1-4.** Distribuzione monolitica rispetto ai microservizi

Si noti che i microservizi innalzano di livello il principio "un solo codebase, un'applicazione" dall' [applicazione a dodici fattori](https://12factor.net/), descritta in precedenza nel capitolo.

> *Il \#fattore 1 specifica "una singola codebase per ogni microservizio, archiviato nel proprio repository. Con il controllo della versione, è possibile eseguire la distribuzione in più ambienti.*

### <a name="why-microservices"></a>Perché usare i microservizi?

I microservizi offrono agilità.

In precedenza nel capitolo è stata confrontata un'applicazione di eCommerce creata come Monolith con i microservizi. Nell'esempio abbiamo visto alcuni vantaggi evidenti:

- Ogni microservizio ha un ciclo di vita autonomo e può evolvere in modo indipendente e distribuito di frequente. Non è necessario attendere una versione trimestrale per la distribuzione di nuove funzionalità o aggiornamenti. È possibile aggiornare un'area di piccole dimensioni di un'applicazione complessa con meno rischi di compromettere l'intero sistema.

- Ogni microservizio può essere ridimensionato in modo indipendente. Anziché ridimensionare l'intera applicazione come singola unità, è possibile scalare solo i servizi che richiedono una maggiore potenza di elaborazione o la larghezza di banda di rete. Questo approccio con granularità fine per la scalabilità consente un maggiore controllo del sistema e consente di ridurre i costi complessivi quando si ridimensionano le parti del sistema, non tutti gli elementi.

Una guida di riferimento eccellente per comprendere i microservizi è [microservizi .NET: architettura per le applicazioni .NET in contenitori](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook). Il libro approfondisce la progettazione e l'architettura di microservizi. È un complemento per un' [architettura di riferimento del microservizio con stack completo](https://github.com/dotnet-architecture/eShopOnContainers) disponibile come download gratuito da Microsoft.

### <a name="developing-microservices"></a>Sviluppo di microservizi

I microservizi possono essere creati con qualsiasi piattaforma di sviluppo moderna.

La piattaforma Microsoft .NET Core è un'ottima scelta. Disponibile e open source, offre molte funzionalità predefinite per semplificare lo sviluppo di microservizi. .NET Core è multipiattaforma. Le applicazioni possono essere compilate ed eseguite su Windows, macOS e la maggior parte delle versioni di Linux.

.NET Core è altamente efficiente e ha un punteggio ottimale rispetto a node. js e ad altre piattaforme in competizione. È interessante notare che [TechEmpower](https://www.techempower.com/) ha condotto un ampio set di [benchmark delle prestazioni](https://www.techempower.com/benchmarks/#section=data-r17&hw=ph&test=plaintext) in molti Framework e piattaforme di applicazioni Web. .NET Core ha un punteggio nelle prime 10, ben oltre node. js e altre piattaforme in competizione.

.NET Core è gestito da Microsoft e dalla community .NET su GitHub.

## <a name="containers"></a>Contenitori

Attualmente, è naturale conoscere il termine *contenitore* indicato in qualsiasi conversazione relativa al *cloud nativo*. Nel libro The [cloud native patterns](https://www.manning.com/books/cloud-native-patterns), l'autore di Cornelia Davis osserva che "i contenitori sono un ottimo strumento per il software nativo del cloud". Il cloud native Computing Foundation colloca la contenitori di microservizi come primo passaggio della [mappa dei percorsi nativi del cloud](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) : linee guida per le aziende che iniziano il percorso nativo del cloud.

Inserimento un microservizio è semplice e diretto. Il codice, le relative dipendenze e il runtime sono inclusi in un file binario denominato [immagine del contenitore](https://docs.docker.com/glossary/?term=image). Le immagini vengono archiviate in un [Registro contenitori](https://caylent.com/container-registries/), che funge da repository o da libreria per le immagini. Un registro di sistema può trovarsi nel computer di sviluppo, nella data center o in un cloud pubblico. Docker gestisce un registro di sistema pubblico tramite [Docker Hub](https://hub.docker.com/). Il cloud di Azure include un [Registro contenitori](https://azure.microsoft.com/services/container-registry/) per archiviare le immagini dei contenitori vicino alle applicazioni cloud in cui vengono eseguite.

Quando necessario, l'immagine viene trasformata in un'istanza del contenitore in esecuzione. L'istanza di viene eseguita in qualsiasi computer in cui è installato un motore di [runtime del contenitore](https://kubernetes.io/docs/setup/production-environment/container-runtimes/) . È possibile avere tutte le istanze del servizio in contenitori in base alle esigenze.

La figura 1-5 mostra tre microservizi diversi, ognuno nel relativo contenitore, in esecuzione in un singolo host.

![Più contenitori in esecuzione in un host contenitore](./media/hosting-mulitple-containers.png)

**Figura 1-5**. Più contenitori in esecuzione in un host contenitore

Si noti che ogni contenitore mantiene il proprio set di dipendenze e Runtime, che può essere diverso. Qui vengono visualizzate diverse versioni del microservizio prodotto in esecuzione nello stesso host. Ogni contenitore condivide una sezione del sistema operativo host sottostante, della memoria e del processore, ma è isolata l'una dall'altra.

Si noti il modo in cui il modello di contenitore abbraccia il principio "dipendenze" dall' [applicazione a dodici fattori](https://12factor.net/).

> *Il \#fattore 2 specifica che "ogni microservizio isola e impacchetta le proprie dipendenze, accettando le modifiche senza influire sull'intero sistema".*

I contenitori supportano i carichi di lavoro Linux e Windows. Il cloud di Azure accetta entrambi. È interessante notare che si tratta di Linux, non di Windows Server, che è diventato il sistema operativo più diffuso in Azure.

Sebbene esistano molti fornitori di contenitori, Docker ha acquisito la quota di Lion del mercato. La società ha guidato lo spostamento del contenitore software. È diventato lo standard de facto per la creazione di pacchetti, la distribuzione e l'esecuzione di applicazioni native del cloud.

### <a name="why-containers"></a>Vantaggi dei contenitori

I contenitori offrono la portabilità e garantiscono la coerenza tra gli ambienti. Incapsulando tutto in un singolo pacchetto, si *isola* il microservizio e le relative dipendenze dall'infrastruttura sottostante.

È possibile distribuire lo stesso contenitore in qualsiasi ambiente con il motore di runtime docker. I carichi di lavoro in contenitori eliminano anche i costi di pre-configurazione di ogni ambiente con Framework, librerie software e motori di Runtime.

Condividendo il sistema operativo e le risorse host sottostanti, i contenitori hanno un footprint molto più ridotto rispetto a una macchina virtuale completa. Le dimensioni più piccole aumentano la *densità*, o il numero di microservizi, che un determinato host può eseguire in una sola volta.

### <a name="container-orchestration"></a>Orchestrazione dei contenitori

Sebbene strumenti come Docker creino immagini ed eseguano contenitori, è necessario anche strumenti per gestirli. La gestione dei contenitori viene eseguita con un programma software speciale denominato agente di orchestrazione del contenitore. Quando si opera su larga scala, l'orchestrazione del contenitore è essenziale.

La figura 1-6 illustra le attività di gestione fornite dagli agenti di orchestrazione dei contenitori.

![Operazioni eseguite dagli agenti di orchestrazione del contenitore](./media/what-container-orchestrators-do.png)

**Figura 1-6**. Operazioni eseguite dagli agenti di orchestrazione del contenitore

Nella tabella seguente vengono descritte le attività comuni dell'orchestrazione.

|  Attività | Spiegazione  |
| :-------- | :-------- |
| Pianificazione | Eseguire automaticamente il provisioning delle istanze del contenitore.|
| Affinità/anti-affinità | Eseguire il provisioning di contenitori vicini o lontani tra loro, in modo da garantire disponibilità e prestazioni. |
| Monitoraggio dell’integrità | Rilevare e correggere automaticamente gli errori.|
| Failover | Eseguire automaticamente il provisioning dell'istanza non riuscita in computer integri.|
| Scalabilità | Aggiungere o rimuovere automaticamente un'istanza del contenitore per soddisfare la domanda.|
| Rete | Gestire una sovrapposizione di rete per la comunicazione del contenitore.|
| Individuazione dei servizi | Consente ai contenitori di individuarsi reciprocamente.|
| Aggiornamenti in sequenza | Coordinare gli aggiornamenti incrementali senza alcuna distribuzione del tempo di inattività. Esegue automaticamente il rollback delle modifiche problematiche.|

Si noti che gli agenti di orchestrazione adottano i principi di disposizione e di concorrenza dall' [applicazione a dodici fattori](https://12factor.net/), illustrata in precedenza nel capitolo.

> *Il \#fattore 9 specifica che le istanze del servizio devono essere monouso, prediligendo le startup veloci per aumentare le opportunità di scalabilità e gli arresti normali per lasciare il sistema in uno stato corretto. I contenitori Docker insieme a un agente di orchestrazione soddisfano questo requisito ".*

> *Il \#fattore 8 specifica che "i servizi vengono scalati orizzontalmente in un numero elevato di piccoli processi identici (copie), anziché eseguire la scalabilità verticale di una singola istanza large nel computer più potente disponibile".*

Sebbene esistano diversi agenti di orchestrazione dei contenitori, [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) è diventato lo standard de facto per il mondo nativo del cloud. Si tratta di una piattaforma portabile, estensibile e open source per la gestione dei carichi di lavoro in contenitori.

È possibile ospitare la propria istanza di Kubernetes, ma è necessario eseguire il provisioning e la gestione delle risorse, che possono essere complesse. Le funzionalità cloud di Azure Kubernetes come servizio gestito, [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). Un servizio gestito consente di sfruttare appieno le funzionalità, senza doverle installare e gestire.

I servizi di Azure Kubernetes sono trattati nel capitolo 2 relativo alla *scalabilità delle applicazioni native del cloud*.

## <a name="backing-services"></a>Servizi di supporto

I sistemi nativi del cloud dipendono da molte risorse ausiliarie diverse, ad esempio archivi dati, broker di messaggi, monitoraggio e servizi di identità. Questi servizi sono noti come [servizi di supporto](https://12factor.net/backing-services).

 La figura 1-7 illustra molti servizi di supporto comuni utilizzati dai sistemi nativi del cloud.

![Servizi di supporto comuni](./media/common-backing-services.png)

**Figura 1-7**. Servizi di supporto comuni

I servizi di supporto promuovono il principio di "senza stato" dall' [applicazione a dodici fattori](https://12factor.net/), illustrata in precedenza nel capitolo.

>*Il \#fattore 6* specifica che "ogni microservizio deve essere eseguito nel proprio processo, isolato da altri servizi in esecuzione. Externalize lo stato richiesto a un servizio di supporto, ad esempio una cache distribuita o un archivio dati ".

È possibile ospitare i propri servizi di backup, ma in questo esempio si è responsabili della gestione delle licenze, del provisioning e della gestione di tali risorse.

I provider di servizi cloud offrono un'ampia gamma di *servizi di backup gestiti.* Anziché possedere il servizio, è sufficiente utilizzarlo. Il provider gestisce la risorsa su larga scala e ha la responsabilità di prestazioni, sicurezza e manutenzione. Il monitoraggio, la ridondanza e la disponibilità sono incorporati nel servizio. I provider supportano completamente i servizi gestiti: aprire un ticket e risolvere il problema.

I sistemi nativi del cloud favoriscono i servizi di backup gestiti dai fornitori di cloud. Il risparmio di tempo e manodopera è eccezionale. Il rischio operativo di ospitare i propri e i problemi riscontrati può comportare un costo elevato.

Una procedura consigliata consiste nel considerare un servizio di backup come *risorsa collegata*, associato in modo dinamico a un microservizio con informazioni (un URL e credenziali) archiviate in una configurazione esterna. Questa guida è stata digitata nell' [applicazione a dodici fattori](https://12factor.net/), illustrata in precedenza nel capitolo.

>*Il \#fattore 4* indica che i servizi di backup devono essere esposti tramite un URL indirizzabile. Questa operazione separa la risorsa dall'applicazione, consentendone l'interscambiabilità. "

>*Il \#fattore 3* specifica che "le informazioni di configurazione vengono spostate al di fuori del microservizio ed esternalizzate tramite uno strumento di gestione della configurazione all'esterno del codice".

Con questo modello, è possibile collegare e scollegare un servizio di supporto senza modifiche al codice. È possibile alzare di livello un microservizio da QA a un ambiente di gestione temporanea. È possibile aggiornare la configurazione del microservizio in modo che punti ai servizi di supporto in gestione temporanea e inserire le impostazioni nel contenitore tramite una variabile di ambiente.

I fornitori di servizi cloud offrono API per comunicare con i propri servizi di supporto proprietari. Queste librerie incapsulano le tubature e la complessità. La comunicazione diretta con queste API condurrà strettamente il codice al servizio di backup. È consigliabile isolare i dettagli di implementazione dell'API del fornitore. Introduce un livello di intermediazione, o un'API intermedia, che espone operazioni generiche al codice del servizio. Questo accoppiamento libero consente di scambiare un servizio di supporto per un altro o di spostare il codice in un cloud pubblico diverso senza dover apportare modifiche al codice del servizio principale.

I servizi di supporto sono descritti in dettaglio nel capitolo 5, *modelli di dati nativi del cloud*e capitolo 4, *modelli di comunicazione nativi del cloud*.

## <a name="automation"></a>Automazione

Come si è visto, i sistemi nativi del cloud adottano i microservizi, i contenitori e la progettazione moderna del sistema per ottenere velocità e agilità. Ma questa è solo una parte della storia. Come si esegue il provisioning degli ambienti cloud su cui vengono eseguiti questi sistemi? In che modo è possibile distribuire rapidamente le funzionalità e gli aggiornamenti delle app? Come è possibile arrotondare il quadro completo?

Immettere la pratica ampiamente accettata dell' [infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)o IaC.

Con IaC è possibile automatizzare il provisioning della piattaforma e la distribuzione di applicazioni. Si applicano essenzialmente procedure di progettazione software come test e controllo delle versioni alle procedure DevOps. L'infrastruttura e le distribuzioni sono automatiche, coerenti e ripetibili.

### <a name="automating-infrastructure"></a>Automazione dell'infrastruttura

Strumenti come [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/), bonifica e l'interfaccia della riga di comando di [Azure](https://docs.microsoft.com/cli/azure/)consentono di creare script in modo dichiarativo dell'infrastruttura cloud necessaria. I nomi delle risorse, le località, le capacità e i segreti sono parametrizzati e dinamici. Lo script viene sottoposto a controllo delle versioni e archiviato nel controllo del codice sorgente come elemento del progetto. Si richiama lo script per eseguire il provisioning di un'infrastruttura coerente e ripetibile negli ambienti di sistema, ad esempio QA, staging e produzione.

In realtà, IaC è idempotente, il che significa che è possibile eseguire lo stesso script senza effetti collaterali. Se il team deve apportare una modifica, viene modificato ed eseguito nuovamente lo script. Sono interessate solo le risorse aggiornate.

In questo articolo, [che cos'è l'infrastruttura come codice](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code), l'autore di Sam Guckenheimer descrive in che modo i team che implementano IaC possono fornire ambienti stabili in modo rapido e scalabile. I team evitano la configurazione manuale degli ambienti e impongono la coerenza rappresentando lo stato desiderato dei propri ambienti tramite codice. Le distribuzioni dell'infrastruttura con IaC sono ripetibili ed evitano problemi di runtime causati dalla mancata configurazione o dalle dipendenze mancanti. I team DevOps possono collaborare con una serie unificata di procedure e strumenti per distribuire applicazioni e la loro infrastruttura di supporto in modo rapido, affidabile e scalabile ".

### <a name="automating-deployments"></a>Automazione delle distribuzioni

L' [applicazione a dodici fattori](https://12factor.net/), descritta in precedenza, richiede passaggi distinti durante la trasformazione del codice completato in un'applicazione in esecuzione.

> *Il \#fattore 5* indica che ogni versione deve applicare una stretta separazione tra le fasi di compilazione, rilascio ed esecuzione. Ogni deve essere contrassegnato con un ID univoco e supportare la possibilità di eseguire il rollback ".

I sistemi di integrazione continua/recapito continuo moderni contribuiscono a soddisfare questo principio. Forniscono passaggi di distribuzione distinti che consentono di garantire un codice coerente e di qualità immediatamente disponibile per gli utenti.

La figura 1-8 Mostra la separazione tra il processo di distribuzione.

![Passaggi per le distribuzioni nella pipeline CI/CD](./media/build-release-run-pipeline.png)

**Figura 1-8**. Passaggi di distribuzione in una pipeline CI/CD

Nella figura precedente, prestare particolare attenzione alla separazione delle attività.

Lo sviluppatore costruisce una funzionalità nel proprio ambiente di sviluppo, scorrendo il cosiddetto "ciclo interno" di codice, esecuzione ed esecuzione del debug. Al termine, viene eseguito il *push* del codice in un repository di codice, ad esempio GitHub, Azure DevOps o bitbucket.

Il push attiva una fase di compilazione che trasforma il codice in un artefatto binario. Il lavoro viene implementato con una pipeline di [integrazione continua (ci)](https://martinfowler.com/articles/continuousIntegration.html) . Compila, testa e crea automaticamente i pacchetti dell'applicazione.

La fase di rilascio preleva l'artefatto binario, applica le informazioni di configurazione dell'ambiente e dell'applicazione esterna e produce una versione non modificabile. La versione viene distribuita in un ambiente specificato. Il lavoro viene implementato con una pipeline di [recapito continuo (CD)](https://martinfowler.com/bliki/ContinuousDelivery.html) . Ogni versione deve essere identificabile. Si può dire che "questa distribuzione esegue la versione 2.1.1 dell'applicazione".

Infine, la funzionalità rilasciata viene eseguita nell'ambiente di esecuzione di destinazione. Le versioni non sono modificabili, pertanto qualsiasi modifica deve creare una nuova versione.

Applicando queste procedure, le organizzazioni si sono evolute radicalmente nel modo in cui distribuiscono il software. Molti sono passati da versioni trimestrali a aggiornamenti su richiesta. L'obiettivo è quello di rilevare i problemi nelle fasi iniziali del ciclo di sviluppo quando sono meno costosi da risolvere. Maggiore è la durata tra le integrazioni, i problemi più costosi diventano la risoluzione.  Con la coerenza del processo di integrazione, i team possono eseguire il commit delle modifiche del codice con maggiore frequenza, ottenendo una migliore collaborazione e qualità del software.

### <a name="azure-pipelines"></a>Azure Pipelines

Il cloud di Azure include un nuovo servizio CI/CD denominato [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/), che fa parte dell'offerta [DevOps di Azure](https://azure.microsoft.com/services/devops/) illustrata nella figura 1-9.

![Azure Pipelines in DevOps](./media/devops-components.png)

**Figura 1-9**. Offerte di Azure DevOps

Azure Pipelines è un servizio cloud che combina integrazione continua (CI) e recapito continuo (CD). È possibile testare, compilare e distribuire il codice automaticamente a qualsiasi destinazione.

Si definisce la pipeline nel codice in un file YAML insieme al resto del codice per l'app.

- Per la pipeline viene eseguita la versione con il codice e viene seguita la stessa struttura di diramazione.
- È possibile ottenere la convalida delle modifiche tramite le revisioni del codice nelle richieste pull e nei criteri di compilazione del ramo.
- Ogni ramo usato può personalizzare i criteri di compilazione modificando il file Azure-Pipelines. yml.
- Il file della pipeline viene archiviato nel controllo della versione ed è possibile esaminarlo in caso di problemi.

Il servizio Azure Pipelines supporta la maggior parte dei provider git e può generare pipeline di distribuzione per le applicazioni scritte nelle piattaforme Linux, macOS o Windows. Include il supporto per Java, .NET, JavaScript, Python, PHP, go, XCode e C++.

>[!div class="step-by-step"]
>[Precedente](introduction.md)
>[successivo](candidate-apps.md)
