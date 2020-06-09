---
title: Migrazione di servizi Web ASP.NET a WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: fa707a4246d5bc9940417072c098b2973140f878
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598801"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrazione di servizi Web ASP.NET a WCF
ASP.NET fornisce strumenti e librerie di classi .NET Framework per compilare servizi Web, oltre a funzionalità per servizi di hosting all'interno di Internet Information Services (IIS). Windows Communication Foundation (WCF) fornisce le librerie di classi, gli strumenti e le funzionalità di hosting di .NET Framework per consentire a entità software di comunicare utilizzando qualsiasi protocollo, compresi quelli utilizzati dai servizi Web.  La migrazione di servizi Web ASP.NET a WCF consente alle applicazioni di sfruttare le nuove funzionalità e i miglioramenti specifici di WCF.  
  
 WCF offre diversi vantaggi importanti rispetto ai servizi Web ASP.NET. Sebbene gli strumenti dei servizi Web di ASP.NET siano esclusivamente per la creazione di servizi Web, WCF fornisce strumenti che possono essere usati quando è necessario che le entità software siano in grado di comunicare tra loro. In tal modo, viene ridotto il numero di tecnologie che gli sviluppatori devono conoscere per far fronte a diversi scenari di comunicazione software. Di conseguenza saranno ridotti i costi delle risorse e i tempi di completamento per i progetti di sviluppo del software.  
  
 Anche per i progetti di sviluppo di servizi Web, WCF supporta più protocolli del servizio Web rispetto al supporto dei servizi Web ASP.NET. I protocolli aggiuntivi sono in grado di gestire soluzioni più sofisticate, tra cui sessioni e transazioni affidabili.  
  
 WCF supporta più protocolli per il trasporto di messaggi rispetto ai servizi Web di ASP.NET. I servizi Web ASP.NET supportano solo l'invio di messaggi utilizzando HTTP (Hypertext Transfer Protocol). WCF supporta l'invio di messaggi tramite HTTP, nonché il Transmission Control Protocol (TCP), Named Pipes e Microsoft Message Queuing (MSMQ). Più importante, WCF può essere esteso per supportare protocolli di trasporto aggiuntivi. Pertanto, il software sviluppato con WCF può essere adattato per interagire con una più ampia gamma di software, aumentando così il potenziale ritorno sull'investimento.  
  
 WCF offre funzionalità molto più ricche per la distribuzione e la gestione delle applicazioni rispetto a quanto fornito dai servizi Web di ASP.NET. Oltre a un sistema di configurazione, in cui è disponibile anche ASP.NET, WCF offre un editor di configurazione, una traccia delle attività dai mittenti ai destinatari e un numero qualsiasi di intermediari, un visualizzatore di tracce, una registrazione dei messaggi, un numero elevato di contatori delle prestazioni e il supporto per Strumentazione gestione Windows.  
  
 Considerati questi potenziali vantaggi di WCF rispetto ai servizi Web di ASP.NET, se si usa o si sta valutando l'uso di servizi Web ASP.NET sono disponibili diverse opzioni:  
  
- Continuare a usare i servizi Web di ASP.NET e rinunciare ai vantaggi offerti da WCF.  
  
- Continua a usare i servizi Web di ASP.NET con l'intenzione di adottare WCF in un determinato momento in futuro. Negli argomenti di questa sezione viene illustrato come ottimizzare le prospettive per poter utilizzare le nuove applicazioni del servizio Web ASP.NET insieme alle applicazioni WCF future. Negli argomenti di questa sezione viene inoltre illustrato come creare nuovi servizi Web ASP.NET in modo da semplificare la migrazione in WCF. Tuttavia, se è importante proteggere i servizi o se sono richieste garanzie di affidabilità o transazioni oppure se è necessario costruire funzionalità di gestione personalizzate, è preferibile adottare WCF. WCF è progettato per scenari di questo tipo.  
  
- Adottare WCF per un nuovo sviluppo, continuando a mantenere le applicazioni del servizio Web ASP.NET esistenti. Questa è molto probabilmente la scelta ottimale. Produce i vantaggi di WCF, risparmiando il costo della modifica delle applicazioni esistenti per utilizzarlo. In questo scenario, le nuove applicazioni WCF possono coesistere con le applicazioni ASP.NET esistenti. Le nuove applicazioni WCF saranno in grado di utilizzare i servizi Web ASP.NET esistenti e WCF può essere utilizzato per programmare nuove funzionalità operative in applicazioni ASP.NET esistenti in base alla modalità di compatibilità ASP.NET di WCF.  
  
- Adottare WCF ed eseguire la migrazione di applicazioni del servizio Web ASP.NET esistenti in WCF. È possibile scegliere questa opzione per migliorare le applicazioni esistenti con le funzionalità fornite da WCF o per riprodurre la funzionalità dei servizi Web ASP.NET esistenti all'interno di applicazioni WCF nuove e più potenti.  
  
> [!NOTE]
> È necessario prestare attenzione se un servizio WCF è ospitato da IIS 5. x e ASP.NET viene disinstallato. Quando un servizio WCF è ospitato da IIS 5. x, è possibile richiedere il codice per il servizio in caso di disinstallazione di ASP.NET. Quando ASP.NET viene disinstallato in un sistema operativo che esegue IIS 5. x e WCF viene disinstallato, un file con estensione svc viene considerato come un file di testo e il contenuto, incluso qualsiasi codice sorgente, viene restituito al richiedente.  
  
 Questa sezione descrive in dettaglio queste opzioni, confronta i servizi Web di ASP.NET con WCF e fornisce istruzioni su come eseguire la migrazione del codice dei servizi Web ASP.NET in WCF.  
  
## <a name="see-also"></a>Vedere anche

- [Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura](anticipating-adopting-wcf-migration.md)
- [Preparazione all'adozione di Windows Communication Foundation: facilitare l'integrazione futura](anticipating-adopting-the-wcf-easing-future-integration.md)
- [Uso di Windows Communication Foundation](adopting-wcf.md)
- [Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati](comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
- [Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo](comparing-aspnet-web-services-to-wcf-based-on-development.md)
