---
title: Migrazione di servizi Web ASP.NET a WCF
ms.date: 03/30/2017
ms.assetid: 1adbb931-f0b1-47f3-9caf-169e4edc9907
ms.openlocfilehash: 7d43c66952d17a91e38ae1b086478b9416321b8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="migrating-aspnet-web-services-to-wcf"></a>Migrazione di servizi Web ASP.NET a WCF
ASP.NET fornisce strumenti e librerie di classi .NET Framework per compilare servizi Web, oltre a funzionalità per servizi di hosting all'interno di Internet Information Services (IIS). Windows Communication Foundation (WCF) fornisce funzionalità di hosting per consentire a entità software per comunicare utilizzando qualsiasi protocollo, compresi quelli utilizzati dai servizi Web, gli strumenti e librerie di classi .NET Framework.  La migrazione di servizi Web ASP.NET a WCF consente alle applicazioni di sfruttare i vantaggi delle nuove funzionalità e i miglioramenti apportati a WCF.  
  
 WCF ha molti importanti vantaggi rispetto ai servizi Web ASP.NET. Strumenti per servizi Web ASP.NET sono esclusivamente per la compilazione di servizi Web, WCF fornisce strumenti che possono essere utilizzati quando entità software devono essere eseguite per comunicare tra loro. In tal modo, viene ridotto il numero di tecnologie che gli sviluppatori devono conoscere per far fronte a diversi scenari di comunicazione software. Di conseguenza saranno ridotti i costi delle risorse e i tempi di completamento per i progetti di sviluppo del software.  
  
 Anche per i progetti di sviluppo del servizio Web, WCF supporta più protocolli del servizio Web di supporto per servizi Web ASP.NET. I protocolli aggiuntivi sono in grado di gestire soluzioni più sofisticate, tra cui sessioni e transazioni affidabili.  
  
 WCF supporta più protocolli di trasporto dei messaggi a servizi Web ASP.NET. I servizi Web ASP.NET supportano solo l'invio di messaggi utilizzando HTTP (Hypertext Transfer Protocol). WCF supporta l'invio di messaggi tramite HTTP, nonché il protocollo TCP (Transmission Control), named pipe e Accodamento messaggi Microsoft (MSMQ). Più importante, WCF può essere estesa per supportare protocolli di trasporto aggiuntivi. Pertanto, software sviluppato utilizzando WCF può essere adattato per operare assieme a un'ampia gamma di altri software, aumentando in tal modo il potenziale rendimento dell'investimento.  
  
 WCF fornisce funzionalità molto più ricche per la distribuzione e la gestione delle applicazioni di servizi Web ASP.NET. Oltre a un sistema di configurazione che dispone anche di ASP.NET, WCF offre un editor di configurazione, la traccia di attività dai mittenti ai destinatari e viceversa attraverso qualsiasi numero di intermediari, un visualizzatore di tracce, la registrazione dei messaggi, un elevato numero di contatori delle prestazioni, e supporto per Strumentazione gestione Windows.  
  
 Visti questi vantaggi potenziali di WCF relativo al Web ASP.NET services, se si utilizza o si sta pensando di utilizzare servizi Web ASP.NET vengono offerte diverse opzioni:  
  
-   Continuare a usare i servizi Web ASP.NET e rinunciare ai vantaggi offerti da WCF.  
  
-   Continuare a usare i servizi Web ASP.NET con l'intenzione di adottare WCF in un momento in futuro. Negli argomenti di questa sezione spiegano come ottimizzare le prospettive per poter usare nuove applicazioni di servizio Web ASP.NET con le future applicazioni WCF. Negli argomenti di questa sezione viene inoltre illustrato come compilare nuovo Web di ASP.NET servizi mirati a facilitare la loro migrazione a WCF. Tuttavia, è importante proteggere i servizi, se sono richieste garanzie di affidabilità o transazione, o se personalizzato è funzionalità di gestione deve essere costruita, quindi è preferibile adottare WCF. WCF è progettato espressamente per questi scenari.  
  
-   Adottare WCF per i nuovi sviluppi, pur continuando a mantenere le applicazioni di servizio Web ASP.NET esistenti. Questa è molto probabilmente la scelta ottimale. Produce i vantaggi di WCF, durante la riserva il costo della modifica delle applicazioni esistenti per utilizzarlo. In questo scenario, le nuove applicazioni WCF possono coesistere con le applicazioni ASP.NET esistenti. Le nuove applicazioni WCF sarà in grado di utilizzare servizi Web ASP.NET esistenti e WCF può essere utilizzato per programmare nuove funzionalità operative in applicazioni ASP.NET esistenti in modalità di compatibilità ASP.NET di WCF.  
  
-   Adottare WCF e la migrazione di applicazioni di servizio Web ASP.NET esistenti a WCF. È possibile scegliere questa opzione per migliorare le applicazioni esistenti con le funzionalità fornite da WCF, oppure per sostituire le funzionalità dei servizi Web ASP.NET esistenti all'interno di nuove, più potenti applicazioni WCF.  
  
> [!NOTE]
>  Prestare attenzione se un servizio WCF è ospitato da IIS 5.x e ASP.NET sia disinstallato. Quando un servizio WCF è ospitato da IIS 5.x, il codice per il servizio può essere richiesto se ASP.NET è disinstallato. Quando ASP.NET è disinstallato in un sistema operativo che esegue IIS 5.x e WCF viene disinstallato, un file con estensione svc viene considerato un file di testo e il contenuto, compreso qualsiasi codice sorgente, viene restituito al richiedente.  
  
 In questa sezione vengono descritte queste opzioni in modo dettagliato, vengono confrontati i servizi Web ASP.NET a WCF e vengono fornite istruzioni su come eseguire la migrazione di codice dei servizi Web ASP.NET a WCF.  
  
## <a name="see-also"></a>Vedere anche  
 [Preparazione all'adozione di Windows Communication Foundation: semplificazione della migrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)  
 [Preparazione dell'adozione di Windows Communication Foundation: semplificazione dell'integrazione futura](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)  
 [Adozione di Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/adopting-wcf.md)  
 [Confronto tra i servizi Web ASP.NET e WCF in base a scopo e standard usati](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used.md)  
 [Confronto tra servizi Web ASP.NET e WCF in base allo sviluppo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
