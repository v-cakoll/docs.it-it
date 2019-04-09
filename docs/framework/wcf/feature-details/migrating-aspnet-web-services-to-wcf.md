---
title: Migrazione di servizi Web ASP.NET a WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 703088cdaae69d90d71fb950912538ea0662229b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211088"
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrazione di servizi Web ASP.NET a WCF
ASP.NET fornisce strumenti e librerie di classi .NET Framework per compilare servizi Web, oltre a funzionalità per servizi di hosting all'interno di Internet Information Services (IIS). Windows Communication Foundation (WCF) offre librerie di classi .NET Framework, strumenti e funzionalità host per consentire a entità software di comunicare utilizzando qualsiasi protocollo, compresi quelli utilizzati dai servizi Web.  La migrazione di servizi Web ASP.NET a WCF consente alle applicazioni di sfruttare i vantaggi delle nuove funzionalità e i miglioramenti apportati a WCF.  
  
 WCF offre diversi vantaggi importanti rispetto ai servizi Web ASP.NET. Strumenti per servizi Web ASP.NET sono esclusivamente per la creazione di servizi Web, WCF fornisce strumenti che possono essere utilizzati quando le entità software devono essere eseguite per comunicare tra loro. In tal modo, viene ridotto il numero di tecnologie che gli sviluppatori devono conoscere per far fronte a diversi scenari di comunicazione software. Di conseguenza saranno ridotti i costi delle risorse e i tempi di completamento per i progetti di sviluppo del software.  
  
 Anche per i progetti di sviluppo del servizio Web, WCF supporta più protocolli del servizio Web di supporto dei servizi Web ASP.NET. I protocolli aggiuntivi sono in grado di gestire soluzioni più sofisticate, tra cui sessioni e transazioni affidabili.  
  
 WCF supporta più protocolli di trasporto dei messaggi a servizi Web ASP.NET. I servizi Web ASP.NET supportano solo l'invio di messaggi utilizzando HTTP (Hypertext Transfer Protocol). WCF supporta l'invio di messaggi tramite HTTP, nonché il protocollo TCP (Transmission Control), named pipe e Microsoft Message Queuing (MSMQ). Più importante, WCF può essere estesa per supportare protocolli di trasporto aggiuntivi. Pertanto, il software sviluppato utilizzando WCF può essere adattato per operare insieme a un'ampia gamma di altri software, aumentando in tal modo il potenziale rendimento dell'investimento.  
  
 WCF fornisce funzionalità molto più ricche per la distribuzione e la gestione delle applicazioni di servizi Web ASP.NET. Oltre a un sistema di configurazione, che è dotato anche ASP.NET, WCF offre un editor di configurazione, traccia delle attività dai mittenti ai destinatari e viceversa attraverso qualsiasi numero di intermediari, un visualizzatore di tracce, la registrazione dei messaggi, un elevato numero di contatori delle prestazioni, e supporto per la Strumentazione gestione Windows.  
  
 Visti questi vantaggi potenziali di WCF rispetto all'ASP.NET Web services, se si usa o si prevede di utilizzare servizi Web ASP.NET sono disponibili diverse opzioni:  
  
-   Continuare a usare i servizi Web ASP.NET e rinunciare ai vantaggi offerti da WCF.  
  
-   Continuare a usare i servizi Web ASP.NET con l'intenzione di adottare WCF in un momento in futuro. Gli argomenti di questa sezione illustrano come ottimizzare le prospettive per poter utilizzare nuove applicazioni di servizio Web ASP.NET con le applicazioni WCF future. Negli argomenti di questa sezione illustrano anche come creare nuovo ASP.NET Web services in modo da renderlo più semplice eseguirne la migrazione a WCF. Tuttavia, se è importante proteggere i servizi oppure sono richieste garanzie di affidabilità o transazione, o se personalizzate funzionalità di gestione dovranno essere costruita, quindi è un'opzione migliore per adottare WCF. WCF è progettato espressamente per questi scenari.  
  
-   Adottare WCF per i nuovi sviluppi, pur continuando a mantenere le applicazioni di servizio Web ASP.NET esistenti. Questa è molto probabilmente la scelta ottimale. Produce i vantaggi di WCF, durante la riserva il costo della modifica delle applicazioni esistenti per utilizzarlo. In questo scenario, le nuove applicazioni WCF possono coesistere con le applicazioni ASP.NET esistenti. Le nuove applicazioni WCF sarà in grado di utilizzare servizi Web ASP.NET esistenti e WCF può essere utilizzato per programmare nuove funzionalità operative in applicazioni ASP.NET esistenti grazie alla modalità di compatibilità ASP.NET di WCF.  
  
-   Adottare WCF ed eseguire la migrazione di applicazioni di servizio Web ASP.NET esistenti a WCF. È possibile scegliere questa opzione per migliorare le applicazioni esistenti con le funzionalità fornite da WCF o per riprodurre le funzionalità dei servizi Web ASP.NET esistenti all'interno di nuove, più potenti applicazioni WCF.  
  
> [!NOTE]
>  Prestare attenzione se un servizio WCF è ospitato da IIS 5.x e ASP.NET sia disinstallato. Quando un servizio WCF è ospitato da IIS 5.x, il codice per il servizio può essere richiesto se ASP.NET è disinstallato. Quando ASP.NET è disinstallato in un sistema operativo che esegue IIS 5.x e WCF viene disinstallato, un file con estensione svc viene considerato un file di testo e il contenuto, compreso qualsiasi codice sorgente, viene restituito al richiedente.  
  
 In questa sezione vengono descritte queste opzioni in modo dettagliato, vengono confrontati i servizi Web ASP.NET a WCF e vengono fornite istruzioni su come eseguire la migrazione di codice dei servizi Web ASP.NET a WCF.  
  
## <a name="see-also"></a>Vedere anche

- [Preparazione all'adozione di Windows Communication Foundation: facilitazione della migrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
- [Preparazione all'adozione di Windows Communication Foundation: facilitazione dell'integrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
- [Uso di Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)
- [Confronto tra i servizi Web ASP.NET e WCF basato sullo scopo e gli standard usati](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)
- [Confronto tra servizi Web ASP.NET e WCF basato sullo sviluppo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
