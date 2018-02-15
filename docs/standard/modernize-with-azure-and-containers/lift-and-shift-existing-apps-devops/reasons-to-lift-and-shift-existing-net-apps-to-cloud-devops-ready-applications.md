---
title: Motivi di accuratezza e MAIUSC esistente app .NET per applicazioni Cloud pronto DevOps
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Motivi di accuratezza e MAIUSC esistente app .NET per applicazioni Cloud pronto DevOps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4f09ec8f5aa041057ac1256eb564e197793c8a2b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="reasons-to-lift-and-shift-existing-net-apps-to-cloud-devops-ready-applications"></a>Motivi di accuratezza e MAIUSC esistente app .NET per applicazioni Cloud pronto DevOps

Con un'applicazione DevOps Cloud pronto, è possibile rapidamente e più volte recapitare applicazioni affidabili ai clienti. Si ottengono essenziali flessibilità e affidabilità rinviando la complessità operativa dell'app alla piattaforma.

Se non è possibile ottenere le applicazioni in tempi brevi, nel momento in cui che si effettua la spedizione, l'app sul mercato che sono stati destinando l'App verrà sono stati ulteriormente sviluppati. Potrebbe essere troppo tardi, indipendentemente dalla modalità anche l'applicazione è stato progettato o progettato. Si potrebbe essere non superati o non raggiungono il pieno potenziale perché non è possibile sincronizzare la distribuzione di app con le esigenze del mercato.

La necessità di innovazione continua business inserisce i team di sviluppo e le operazioni al limite. L'unico modo per ottenere la flessibilità, che è necessario che nel innovazione business continua è modernizzazione le applicazioni con le tecnologie come contenitori e i principi di applicazione Cloud pronto DevOps specifici.

La riga inferiore è che quando un'organizzazione genera e gestisce le applicazioni che sono DevOps Cloud pronto, può inserire più rapidamente soluzioni in mani di clienti e portare nuove idee sul mercato quando sono rilevanti.

## <a name="cloud-devops-ready-application-principles-and-tenets"></a>I principi del cloud pronto DevOps applicazione e principi 

Miglioramenti nel cloud sono incentrati principalmente in due obiettivi: ridurre i costi e migliorare la crescita aziendale per migliorare l'agilità. Questi obiettivi semplificazione dei processi e riducendo le forze di attrito quando si rilascia e distribuire applicazioni.

L'applicazione è pronta DevOps se si è un agile modo-sviluppare l'applicazione in modo autonomo da altre applicazioni locali e quindi rilasciare, distribuire, scalabilità automatica, monitorare e risolvere i problemi dell'applicazione nel cloud.

La chiave è *flessibilità*. Può essere rilasciato con flessibilità, a meno che non si riduce al minimo qualsiasi distribuzione di produzione problemi e ambiente di sviluppo e test. Contenitori (in particolare, Docker, come standard di fatto) e dei servizi gestiti sono stati progettati specificamente per questo scopo.

Per ottenere una flessibilità, è necessario anche i processi automatizzati DevOps basati su pipeline CI/CD che vengono rilasciati a piattaforme scalabile nel cloud. Le piattaforme CI/CD (ad esempio Visual Studio Team Services o Jenkins) da distribuire in una piattaforma cloud scalabili e resilienti (ad esempio Azure Service Fabric o Kubernetes) sono tecnologie chiave per la flessibilità nel cloud.

Nell'elenco seguente vengono descritte le procedure consigliate per le applicazioni Cloud pronto DevOps principi principale. Si noti che è possibile adottare tutti o solo alcuni di questi principi, in un approccio progressivo o incrementale:

-   **Contenitori**. Contenitori offrono la possibilità di includere le dipendenze dell'applicazione con l'applicazione stessa. Creazione dei contenitori riduce notevolmente il numero di problemi che potrebbero verificarsi quando si distribuisce in ambienti di produzione o di test in ambienti di gestione temporanea. Infine, contenitori di migliorano la flessibilità di recapito dell'applicazione.

-   **Cloud resilienti e scalabili**. Il cloud offre una piattaforma che è gestito, elastico, scalabile e flessibile. Queste caratteristiche sono fondamentali per ottenere i miglioramenti di costo e spedire elevata disponibile e affidabile di applicazioni in una distribuzione continua. Servizi gestiti come database gestiti, gestito memorizzare nella cache come un servizio (CaaS) e l'archiviazione gestita sono i componenti fondamentali per risolvere i costi di manutenzione dell'applicazione.

-   **Monitoraggio**. È possibile avere un'applicazione affidabile senza la necessità di un buon metodo per rilevare e diagnosticare le eccezioni e problemi di prestazioni dell'applicazione. È necessario ottenere approfondimenti analitica immediata e la gestione delle prestazioni dell'applicazione.

-   **DevOps delle impostazioni cultura e il recapito continuo**. Adozione di procedure Cloud pronto DevOps richiede una modifica relative alla lingua in cui i team lavorano non è più in silo indipendenti. Le pipeline/CD CI sono possibili solo se è presente un aumento della collaborazione tra sviluppatori e le operazioni IT, supportati da contenitori e gli strumenti CI/CD.

Figura 4-2 illustra i concetti di base facoltativi di un'applicazione Cloud pronto DevOps. Le altre colonne implementare, di readier l'applicazione sarà riesca a soddisfare le aspettative dei clienti.

> ![Concetti di base di un'applicazione Cloud pronto DevOps](./media/image2.png)
>
> **Figura 4-2.** Concetti di base di un'applicazione Cloud pronto DevOps

Per riepilogare, un'applicazione Cloud pronto DevOps è un approccio per la compilazione e la gestione delle applicazioni che sfrutta i vantaggi del cloud computing di modello, quando si utilizza una combinazione di contenitori, infrastruttura cloud gestita, le tecniche di applicazione resilienti, monitoraggio, il recapito continuo e DevOps, senza la necessità di riprogettare e sia necessario riscrivere le applicazioni esistenti.

L'organizzazione possa adottare gradualmente queste tecnologie e gli approcci. Non è necessario adottare tutti, in una sola volta. È possibile adottare loro in modo incrementale, in base alle priorità aziendali e le esigenze degli utenti.

## <a name="benefits-of-a-cloud-devops-ready-application"></a>Vantaggi di un'applicazione Cloud pronto DevOps

Mediante la conversione di un'applicazione esistente a un'applicazione Cloud pronto DevOps (senza la generazione di codice o riprogettazione), è possibile ottenere i vantaggi seguenti:

-   **Riduzione dei costi, poiché viene gestita l'infrastruttura gestita dal provider di cloud**. Le applicazioni cloud pronto DevOps ottengono i vantaggi del cloud mediante l'elasticità della casella del cloud, scalabilità automatica e la disponibilità elevata. Vantaggi correlati non solo per le funzionalità di calcolo (macchine virtuali e contenitori), ma dipendono anche da risorse nel cloud, quali DBaaS, CaaS e un'infrastruttura di un'applicazione potrebbe essere necessaria.

-   **Applicazione flessibile e dell'infrastruttura**. Quando esegue la migrazione al cloud, è necessario adottare errori temporanei. si verificheranno errori nel cloud. Inoltre, hardware e dell'infrastruttura cloud è "sostituibili," che aumenta l'opportunità di tempi di inattività temporaneo. Allo stesso tempo, le funzionalità cloud interna e alcune tecniche di sviluppo di applicazioni che implementano resilienza e automatizzare il ripristino rendono molto più semplice per il ripristino da errori imprevisti nel cloud.

-   **Più approfondite sulle prestazioni dell'applicazione**. Cloud come Azure Application Insights forniscono una visualizzazione per la gestione dello stato, le notifiche e sulla registrazione, gli strumenti di monitoraggio. Rendi le applicazioni di facile eseguire il debug e controllare i log di controllo. Ciò è fondamentale per un'applicazione cloud affidabile.

-   **La portabilità dell'applicazione, con le distribuzioni agile**. Contenitori (contenitori Linux o Windows basati sul motore Docker) offrono la soluzione migliore per evitare un'applicazione cloud bloccato. Utilizzando contenitori, gli host Docker e multi-cloud orchestrators, è possibile spostare da un ambiente o cloud a un altro. Contenitori di eliminano le forze di attrito che si verifica in genere nelle distribuzioni in qualsiasi ambiente (fase/test o produzione).

Tutti questi vantaggi alla fine di fornire la riduzione dei costi di chiave per il ciclo di vita dell'applicazione end-to-end.

Nelle sezioni seguenti questi vantaggi sono spiegati in maggior dettaglio e sono collegati a tecnologie specifiche.

>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](microsoft-technologies-in-cloud-devops-ready-applications.md)
