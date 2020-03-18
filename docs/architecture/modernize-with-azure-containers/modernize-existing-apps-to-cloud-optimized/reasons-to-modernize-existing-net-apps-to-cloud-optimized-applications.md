---
title: Motivi per modernizzare le app .NET esistenti in applicazioni ottimizzate per il cloud
description: Modernizza le applicazioni .NET esistenti con i contenitori di Azure Cloud e Windows . Motivi per modernizzare le app .NET esistenti in applicazioni ottimizzate per il cloud
ms.date: 04/28/2018
ms.openlocfilehash: 55eb3fb9b0b6c91e25bcdb23056a8a8e51463ef7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73093624"
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Motivi per modernizzare le app .NET esistenti in applicazioni ottimizzate per il cloud

Con un'applicazione ottimizzata per il cloud, è possibile distribuire rapidamente e ripetutamente applicazioni affidabili ai clienti. Ottieni agilità e affidabilità essenziali rimandando gran parte della complessità operativa della tua app alla piattaforma.

Se non riesci a commercializzare rapidamente le tue applicazioni, quando spedisci la tua app, il mercato di destinazione si sarà evoluto. Potrebbe essere troppo tardi, non importa quanto bene l'applicazione è stata progettata o progettata. Potresti non riuscire o non raggiungere il tuo pieno potenziale perché non puoi sincronizzare la distribuzione delle app con le esigenze del mercato.

La necessità di un'innovazione aziendale continua spinge i team di sviluppo e operativi al limite. L'unico modo per ottenere l'agilità di cui hai bisogno nell'innovazione aziendale continua è modernizzare le tue applicazioni con tecnologie come contenitori e principi applicativi specifici ottimizzati per il cloud.

La linea di fondo è che quando un'organizzazione crea e gestisce applicazioni che sono cloud-Optimized, può mettere le soluzioni nelle mani dei clienti prima e portare nuove idee sul mercato quando sono rilevanti.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Principi applicativi e principi ottimizzati per il cloud

I miglioramenti nel cloud si concentrano principalmente sul raggiungimento di due obiettivi: ridurre i costi e migliorare la crescita aziendale migliorando l'agilità. Questi obiettivi vengono raggiunti semplificando i processi e riducendo l'attrito quando si rilasciano e spediscono le applicazioni.

L'applicazione è ottimizzata per il cloud se puoi sviluppare l'app in modo agile in modo autonomo da altre app locali e quindi rilasciare, distribuire, ridimensionare automaticamente, monitorare e risolvere i problemi dell'app nel cloud.

La chiave è *l'agilità*. Non è possibile spedire con agilità a meno che non si riduce al minimo assoluto eventuali problemi di distribuzione-produzione e problemi dell'ambiente di sviluppo/test. I contenitori (in particolare, Docker, come standard de facto) e i servizi gestiti sono stati progettati specificamente per questo scopo.

Per ottenere l'agilità, sono necessari anche processi DevOps automatizzati basati su pipeline CI/CD che vengono rilasciate su piattaforme scalabili nel cloud. Le piattaforme CI/CD (come i servizi DevOps di Azure o Jenkins) distribuite in una piattaforma cloud scalabile e resiliente (ad esempio il servizio app di Azure o il servizio Kubernetes di Azure) sono tecnologie chiave per ottenere agilità nel cloud.

Nell'elenco seguente vengono descritti i principi o le procedure principali per le applicazioni ottimizzate per il cloud. Si noti che è possibile adottare tutti o solo alcuni di questi principi, in un approccio progressivo o incrementale:Note that you can adopt all or only some of these principles, in a progressive or incremental approach:

- **Contenitori**. I contenitori consentono di includere le dipendenze dell'applicazione con l'applicazione stessa. La containerizzazione riduce significativamente il numero di problemi che possono verificarsi durante la distribuzione in ambienti di produzione o il test in ambienti di gestione temporanea. In definitiva, i contenitori migliorano l'agilità della distribuzione delle applicazioni.

- **Cloud resiliente e scalabile.** Il cloud fornisce una piattaforma gestita, elastica, scalabile e resiliente. Queste caratteristiche sono fondamentali per ottenere miglioramenti dei costi e spedire applicazioni altamente disponibili e affidabili in una consegna continua. I servizi gestiti come i database gestiti, la cache gestita come servizio (CaaS) e l'archiviazione gestita sono componenti fondamentali per ridurre i costi di manutenzione dell'applicazione.

- **Monitoraggio**. Non è possibile disporre di un'applicazione affidabile senza disporre di un buon modo per rilevare e diagnosticare le eccezioni e i problemi di prestazioni dell'applicazione. È necessario ottenere informazioni utili attraverso la gestione delle prestazioni delle applicazioni e l'analisi istantanea.

- **Cultura DevOps e distribuzione continua.** L'adozione delle pratiche DevOps richiede un cambiamento culturale in cui i team non lavorano più in silos indipendenti. Le pipeline CI/CD sono possibili solo quando vi è una maggiore collaborazione tra i team di sviluppo e le operazioni IT, supportati da contenitori e strumenti CI/CD.

Nella figura 4-2 sono riportati i principali pilastri facoltativi di un'applicazione ottimizzata per il cloud. Più pilastri implementi, più la tua applicazione sarà riuscire a soddisfare le aspettative dei tuoi clienti.

![Diagramma che assegna un nome ai pilastri principali di un'applicazione ottimizzata per il cloud.](./media/main-pillars-cloud-optimized-application.png)

**Come grafico 4-2.** Principali pilastri di un'applicazione ottimizzata per il cloud

Per riassumere, un'applicazione ottimizzata per il cloud è un approccio alla creazione e alla gestione di applicazioni che sfrutta il modello di cloud computing, utilizzando una combinazione di contenitori, infrastruttura cloud gestita, tecniche di applicazione resilienti, monitoraggio, distribuzione continua e DevOps, il tutto senza la necessità di riprogettare e ricodificare le applicazioni esistenti.

L'organizzazione può adottare queste tecnologie e approcci gradualmente. Non devi abbracciarli tutti, tutti in una volta. È possibile adottarli in modo incrementale, a seconda delle priorità aziendali e delle esigenze degli utenti.

## <a name="benefits-of-a-cloud-optimized-application"></a>Vantaggi di un'applicazione ottimizzata per il cloud

È possibile ottenere i vantaggi seguenti convertendo un'applicazione esistente in un'applicazione ottimizzata per il cloud (senza riprogettazione o codifica):

- **Riduzione dei costi, poiché l'infrastruttura gestita viene gestita dal provider di cloud.** Le applicazioni ottimizzate per il cloud ottengono i vantaggi del cloud utilizzando l'elasticità, la scalabilità automatica e la disponibilità elevata del cloud. I vantaggi sono correlati non solo alle funzionalità di calcolo (VM e contenitori), ma dipendono anche dalle risorse nel cloud, ad esempio DBaaS, CaaS e da qualsiasi infrastruttura necessaria per un'applicazione.

- **Applicazione e infrastruttura resilienti**. Quando si esegue la migrazione al cloud, è necessario adottare errori temporanei; si verificheranno errori nel cloud. Inoltre, l'infrastruttura cloud e l'hardware sono "sostituibili", il che aumenta le opportunità di tempi di inattività temporanei. Allo stesso tempo, le funzionalità del cloud interno e alcune tecniche di sviluppo delle applicazioni che implementano la resilienza e automatizzano il ripristino semplificano il ripristino da errori imprevisti nel cloud.

- **Informazioni più approfondite sulle prestazioni dell'applicazione**. Gli strumenti di monitoraggio cloud come Azure Application Insights forniscono la visualizzazione per la gestione dell'integrità, la registrazione e le notifiche. I log di controllo semplificano il debug e il controllo delle applicazioni, fondamentali per un'applicazione cloud affidabile.

- **Portabilità dell'applicazione, con distribuzioni agili.** I contenitori (contenitori Linux o Windows basati su Docker Engine) offrono la soluzione migliore per evitare un'applicazione bloccata nel cloud. Utilizzando contenitori, host Docker e orchestratori multi-cloud, è possibile passare facilmente da un ambiente o cloud a un altro. I contenitori eliminano l'attrito che in genere si verifica nelle distribuzioni in qualsiasi ambiente (fase/test/produzione).

Tutti questi vantaggi in ultima analisi forniscono una riduzione dei costi chiave per il ciclo di vita delle applicazioni end-to-end.

Nelle sezioni seguenti, questi vantaggi sono spiegati in modo più dettagliato e sono collegati a tecnologie specifiche.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](microsoft-technologies-in-cloud-optimized-applications.md)
