---
title: Motivi per cui rinnovare le app .NET esistenti per le applicazioni ottimizzato per il Cloud
description: Modernizzare le applicazioni .NET esistenti con contenitori Windows e il Cloud di Azure | Motivi per cui rinnovare le app .NET esistenti per le applicazioni ottimizzato per il Cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 17838381f42a760caa7fba7e09ab798c6284bccb
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44509960"
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Motivi per cui rinnovare le app .NET esistenti per le applicazioni ottimizzato per il Cloud

Con un'applicazione ottimizzato per il Cloud, consente rapidamente e continuativamente di fornire applicazioni affidabili ai clienti. È ottenere affidabilità e flessibilità essenziale posticipando la complessità operativa dell'app per la piattaforma.

Se non è possibile ottenere le applicazioni sul mercato velocemente, nel momento in cui che si invia le tue app, si sono verrà evolute nel mercato che si sono stati come destinazione. Potrebbe essere troppo tardi, indipendentemente da come l'applicazione è stata progettata o decodificata. Si potrebbe essere non superati o non raggiungono l'intero potenziale perché non è possibile sincronizzare la distribuzione di app con le esigenze del mercato.

La necessità di innovazione aziendale continua effettua il push ai team di sviluppo e operazioni con il valore limite. L'unico modo per ottenere la flessibilità che è necessario l'innovazione continua business è tramite la modernizzazione delle applicazioni con le tecnologie come i contenitori e i principi di applicazione specifico ottimizzato per il Cloud.

La conclusione è che quando un'organizzazione crea e gestisce le applicazioni che sono ottimizzate per la Cloud, è possibile inserire più rapidamente soluzioni messi a disposizione dei clienti e nuove idee sul mercato quando sono rilevanti.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Principi e i principi dell'applicazione ottimizzato per il cloud 

Miglioramenti nel cloud sono incentrati principalmente su due obiettivi: ridurre i costi e migliorare la crescita aziendale grazie al miglioramento dell'agilità. Questi obiettivi semplificando i processi e ridurre gli attriti quando si rilascia e distribuire applicazioni.

L'applicazione è ottimizzato per il Cloud se can aggiuntivo un'agile modo-sviluppa la tua app in modo autonomo da altre App in locale e quindi rilasciare, distribuire, la scalabilità automatica, monitorare e risolvere i problemi dell'app nel cloud.

La chiave è *agilità*. Non è possibile spedire con agilità a meno che non è ridurre al minimo qualsiasi distribuzione alla produzione problemi e problemi di ambiente di sviluppo/test. Contenitori (in particolare, Docker, come uno standard de facto) e i servizi gestiti sono stati progettati per questo scopo specifico.

Per ottenere flessibilità, è necessario anche i processi DevOps automatizzati basati su pipeline CI/CD che rilasciano alle piattaforme scalabili nel cloud. Piattaforme di integrazione continua/recapito Continuo (come Azure DevOps Services o Jenkins) da distribuire in una piattaforma cloud scalabile e resiliente (ad esempio servizio App di Azure, Azure Service Fabric o Azure Kubernetes Service) sono tecnologie fondamentali per ottenere flessibilità sul cloud.

Nell'elenco seguente descrive i principi principale o procedure consigliate per le applicazioni ottimizzato per il Cloud. Si noti che è possibile adottare tutti o solo alcuni di questi principi, in un approccio graduale o incrementale:

-   **I contenitori**. I contenitori offrono la possibilità di includere le dipendenze dell'applicazione con l'applicazione stessa. Containerizzazione riduce notevolmente il numero di problemi che possono verificarsi quando si distribuisce in ambienti di produzione o di test in ambienti di staging. In definitiva, i contenitori di migliorano la flessibilità di distribuzione delle applicazioni.

-   **Cloud resilienti e scalabili**. Il cloud offre una piattaforma che è gestito, elastico, scalabile e resiliente. Queste caratteristiche sono fondamentali per ottenere i miglioramenti di costi e fornire elevata disponibile e affidabile delle applicazioni in una distribuzione continua. Servizi gestiti, ad esempio database gestiti, gestiti nella cache come un servizio (CaaS) e archiviazione gestita sono i componenti fondamentali per risolvere i costi di manutenzione dell'applicazione.

-   **Monitoraggio**. È possibile avere un'applicazione affidabile senza che sia un buon metodo per rilevare e diagnosticare le eccezioni e problemi di prestazioni dell'applicazione. È necessario ottenere informazioni operative dettagliate tramite analitica immediata e gestione delle prestazioni.

-   **DevOps dalle impostazioni cultura e il recapito continuo**. Adozione di procedure consigliate di DevOps è necessario un cambiamento culturale in cui i team lavorano non è più in silo indipendenti. Pipeline CI/CD sono possibili solo quando esiste un aumento della collaborazione tra lo sviluppo e i team IT, supportati da contenitori e gli strumenti di integrazione continua/recapito Continuo.

Figura 4-2 illustra i concetti di base facoltativi di un'applicazione ottimizzato per il Cloud. I più concetti fondamentali di implementare, di readier l'applicazione abbia esito positivo nel soddisfare le aspettative dei clienti.

> ![Concetti di base di un'applicazione ottimizzato per il Cloud](./media/image2.png)
>
> **Figura 4-2**. Concetti di base di un'applicazione ottimizzato per il Cloud

Per riepilogare, un'applicazione ottimizzato per il Cloud è un approccio alla creazione e la gestione di applicazioni che sfrutta i vantaggi del cloud computing del modello, quando si usa una combinazione di contenitori, infrastruttura cloud gestito, le tecniche di applicazioni resilienti, monitoraggio, il recapito continuo e DevOps, senza la necessità di riprogettare ed ricodifica delle applicazioni esistenti.

L'organizzazione può adottare gradualmente le tecnologie e gli approcci. Non è necessario adottare tutte, tutti contemporaneamente. È possibile adottare loro in modo incrementale, a seconda delle esigenze degli utenti e le priorità aziendali.

## <a name="benefits-of-a-cloud-optimized-application"></a>Vantaggi di un'applicazione ottimizzato per il Cloud

Mediante la conversione di un'applicazione esistente a un'applicazione ottimizzato per il Cloud (senza riarchitettare o codifica), è possibile ottenere i vantaggi seguenti:

-   **Ridurre i costi, poiché viene gestita l'infrastruttura gestita dal provider di servizi cloud**. Ottimizzato per il cloud le applicazioni ottengono i vantaggi del cloud con elasticità out-of-the-box del cloud, scalabilità automatica e la disponibilità elevata. I vantaggi correlati non solo per le funzionalità di calcolo (macchine virtuali e contenitori), ma anche in base alle risorse nel cloud, come DBaaS, CaaS e qualsiasi infrastruttura potrebbe essere necessaria un'applicazione.

-   **Infrastruttura e applicazioni resilienti**. Quando esegue la migrazione al cloud, è necessario gestire gli errori temporanei; si verificheranno errori nel cloud. Inoltre, hardware e dell'infrastruttura cloud sono "sostituibili," aumentando opportunità per il tempo di inattività temporaneo. Allo stesso tempo, le funzionalità cloud interno e alcune tecniche di sviluppo di applicazioni che implementano la resilienza e automazione del ripristino rendono molto più semplice per il ripristino da errori imprevisti nel cloud.

-   **Informazioni più dettagliate sulle prestazioni dell'applicazione**. Il cloud come Azure Application Insights è fornire una visualizzazione per la gestione dell'integrità, la registrazione e le notifiche, gli strumenti di monitoraggio. I log di controllo facilitano l'applicazioni di eseguire il debug e di controllo, fondamentali per un'applicazione cloud affidabile.

-   **Portabilità delle applicazioni, con le distribuzioni di agile**. I contenitori (contenitori Linux o Windows basati sul motore di Docker) offrono la migliore soluzione per evitare un'applicazione bloccata al cloud. Usando i contenitori, gli host Docker e gli agenti di orchestrazione di multi-cloud, puoi spostare da un ambiente e da cloud a un altro. I contenitori di eliminano i conflitti si verifica in genere nelle distribuzioni in qualsiasi ambiente (fase, test o produzione).

Tutti questi vantaggi forniscono in definitiva la riduzione dei costi chiave per il ciclo di vita dell'applicazione end-to-end.

Nelle sezioni seguenti, questi vantaggi sono illustrati in modo più dettagliato e sono collegati a tecnologie specifiche.

>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](microsoft-technologies-in-cloud-optimized-applications.md)
