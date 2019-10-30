---
title: Motivi per modernizzare le app .NET esistenti in applicazioni ottimizzate per il cloud
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Motivi per modernizzare le app .NET esistenti in applicazioni ottimizzate per il cloud
ms.date: 04/28/2018
ms.openlocfilehash: 55eb3fb9b0b6c91e25bcdb23056a8a8e51463ef7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093624"
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Motivi per modernizzare le app .NET esistenti in applicazioni ottimizzate per il cloud

Grazie a un'applicazione ottimizzata per il cloud, è possibile distribuire rapidamente e ripetutamente applicazioni affidabili ai clienti. È possibile ottenere flessibilità e affidabilità essenziali riferendo la maggior parte della complessità operativa dell'app alla piattaforma.

Se non si riesce a ottenere rapidamente il mercato delle applicazioni, quando si distribuisce l'app, si evolverà il mercato di destinazione. Potrebbe essere troppo tardi, indipendentemente dal fatto che l'applicazione sia stata architettata o progettata. È possibile che si verifichi un errore o che non si raggiunga l'intero potenziale perché non è possibile sincronizzare la distribuzione delle app con le esigenze del mercato.

La necessità di un'innovazione aziendale continua spinge i team di sviluppo e operativi fino al limite. L'unico modo per ottenere la flessibilità necessaria nell'innovazione aziendale continua consiste nel modernizzare le applicazioni con tecnologie quali i contenitori e i principi specifici delle applicazioni ottimizzate per il cloud.

Il risultato finale è che, quando un'organizzazione crea e gestisce applicazioni ottimizzate per il cloud, può mettere le soluzioni in mano ai clienti prima e introdurre nuove idee sul mercato quando sono rilevanti.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Principi e principi per le applicazioni ottimizzate per il cloud

I miglioramenti apportati al cloud si concentrano principalmente sulla riunione di due obiettivi: Riduci i costi e migliora la crescita aziendale migliorando la flessibilità. Questi obiettivi si ottengono semplificando i processi e riducendo l'attrito quando si rilasciano e si distribuiscono applicazioni.

L'applicazione è ottimizzata per il cloud se è possibile: sviluppare un'app in modo autonomo da altre app locali e quindi rilasciare, distribuire, ridimensionare automaticamente, monitorare e risolvere i problemi dell'app nel cloud.

La chiave è l' *agilità*. Non è possibile fornire flessibilità, a meno che non si riducano a un minimo assoluto eventuali problemi di distribuzione e di produzione e di ambiente di sviluppo/test. I contenitori (in particolare, Docker, come lo standard de facto) e i servizi gestiti sono stati progettati appositamente per questo scopo.

Per ottenere agilità, sono necessari anche processi DevOps automatizzati basati su pipeline di integrazione continua/recapito continuo che si rilasciano a piattaforme scalabili nel cloud. Le piattaforme CI/CD, ad esempio Azure DevOps Services o Jenkins, che vengono distribuite in una piattaforma cloud scalabile e resiliente (ad esempio app Azure servizio o Azure Kubernetes) sono tecnologie chiave per ottenere agilità nel cloud.

L'elenco seguente descrive i principi o le procedure principali per le applicazioni ottimizzate per il cloud. Si noti che è possibile adottare tutti o solo alcuni di questi principi, in un approccio progressivo o incrementale:

- **Contenitori**. I contenitori offrono la possibilità di includere le dipendenze dell'applicazione con l'applicazione stessa. La gestione dei contenitori riduce significativamente il numero di problemi che si possono verificare durante la distribuzione negli ambienti di produzione o nel test negli ambienti di staging. Infine, i contenitori migliorano l'agilità della distribuzione di applicazioni.

- **Cloud resiliente e scalabile**. Il cloud offre una piattaforma gestita, elastica, scalabile e resiliente. Queste caratteristiche sono fondamentali per ottenere miglioramenti ai costi e distribuire applicazioni a disponibilità elevata e affidabili in un recapito continuo. I servizi gestiti come i database gestiti, la cache gestita come servizio (CaaS) e l'archiviazione gestita sono componenti fondamentali per alleviare i costi di manutenzione dell'applicazione.

- **Monitoraggio**. Non è possibile avere un'applicazione affidabile senza avere un metodo efficace per rilevare e diagnosticare le eccezioni e i problemi di prestazioni delle applicazioni. È necessario ottenere informazioni dettagliate di utilità pratica tramite la gestione delle prestazioni delle applicazioni e l'analisi immediata.

- **Impostazioni cultura DevOps e recapito continuo**. L'adozione di procedure DevOps richiede una modifica culturale in cui i team non lavorano più in silo indipendenti. Le pipeline di integrazione continua/recapito continuo sono possibili solo in presenza di una maggiore collaborazione tra i team operativi di sviluppo e IT, supportati da contenitori e strumenti di integrazione continua/distribuzione continua.

La figura 4-2 illustra i principali pilastri facoltativi di un'applicazione ottimizzata per il cloud. Maggiore è il numero di pilastri implementati, il più idoneo per soddisfare le aspettative dei clienti.

![Diagramma che denomina i pilastri principali di un'applicazione ottimizzata per il cloud.](./media/main-pillars-cloud-optimized-application.png)

**Figura 4-2**. Principali pilastri di un'applicazione ottimizzata per il cloud

Per riepilogare, un'applicazione ottimizzata per il cloud è un approccio alla creazione e alla gestione di applicazioni che sfruttano i vantaggi del modello di cloud computing, usando una combinazione di contenitori, infrastruttura cloud gestita, tecniche applicative resilienti, monitoraggio, recapito continuo e DevOps, tutto senza la necessità di riprogettare e ricodificare le applicazioni esistenti.

L'organizzazione può adottare gradualmente tali tecnologie e approcci. Non è necessario comprenderle tutte in una sola volta. È possibile adottarli in modo incrementale, a seconda delle priorità aziendali e delle esigenze degli utenti.

## <a name="benefits-of-a-cloud-optimized-application"></a>Vantaggi di un'applicazione ottimizzata per il cloud

È possibile ottenere i vantaggi seguenti convertendo un'applicazione esistente in un'applicazione ottimizzata per il cloud (senza riprogettare o codificare):

- **Costi ridotti, perché l'infrastruttura gestita viene gestita dal provider di servizi cloud**. Le applicazioni ottimizzate per il cloud ottengono i vantaggi del cloud usando l'elasticità predefinita del cloud, la scalabilità automatica e la disponibilità elevata. I vantaggi sono correlati non solo alle funzionalità di calcolo (VM e contenitori), ma dipendono anche dalle risorse nel cloud, ad esempio DBaaS, CaaS e da qualsiasi infrastruttura necessaria per un'applicazione.

- **Applicazione e infrastruttura resilienti**. Quando si esegue la migrazione al cloud, è necessario adottare errori temporanei. si verificheranno errori nel cloud. Inoltre, l'infrastruttura cloud e l'hardware sono "sostituibili", che aumentano le opportunità di tempi di inattività temporanei. Allo stesso tempo, le funzionalità cloud interne e alcune tecniche di sviluppo di applicazioni che implementano la resilienza e automatizzano il ripristino rendono molto più semplice recuperare da errori imprevisti nel cloud.

- **Informazioni approfondite sulle prestazioni dell'applicazione**. Gli strumenti di monitoraggio cloud come applicazione Azure Insights forniscono la visualizzazione per la gestione dell'integrità, la registrazione e le notifiche. I log di controllo facilitano il debug e il controllo delle applicazioni, fondamentali per un'applicazione cloud affidabile.

- **Portabilità delle applicazioni, con distribuzioni agile**. I contenitori, ovvero i contenitori Linux o Windows basati sul motore Docker, offrono la soluzione migliore per evitare un'applicazione bloccata dal cloud. Con i contenitori, gli host Docker e gli agenti di orchestrazione con più cloud, è possibile spostarsi facilmente da un ambiente o da un cloud a un altro. I contenitori eliminano la frizione che in genere si verifica nelle distribuzioni in qualsiasi ambiente (fase/test/produzione).

Tutti questi vantaggi forniscono infine riduzioni dei costi chiave per il ciclo di vita dell'applicazione end-to-end.

Nelle sezioni seguenti questi vantaggi vengono illustrati in modo più dettagliato e sono collegati a tecnologie specifiche.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](microsoft-technologies-in-cloud-optimized-applications.md)
