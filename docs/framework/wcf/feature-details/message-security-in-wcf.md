---
title: Protezione dei messaggi in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a80efb59-591a-4a37-bb3c-8fffa6ca0b7d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 21cbeff554be6da77ce28e87b7f82ffdd58f542d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="message-security-in-wcf"></a>Protezione dei messaggi in WCF
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ha due modalità principali per garantire la protezione (`Transport` e `Message`) e una terza modalità (`TransportWithMessageCredential`) che rappresenta una combinazione delle due. In questo argomento viene illustrata la sicurezza dei messaggi e i motivi per cui è consigliabile utilizzarla.  
  
## <a name="what-is-message-security"></a>Informazioni sulla sicurezza dei messaggi  
 La sicurezza dei messaggi si avvale della specifica WS-Security per proteggere i messaggi. Tale specifica descrive i miglioramenti apportati alla messaggistica SOAP per assicurare riservatezza, integrità e autenticazione a livello di messaggio SOAP (anziché a livello del trasporto).  
  
 In breve, la sicurezza dei messaggi differisce dalla protezione del trasporto in quanto incapsula le credenziali e le attestazioni di sicurezza in ogni messaggio insieme a qualsiasi tipo di sicurezza del messaggio (con firma o crittografia). L'applicazione diretta della protezione al messaggio modificando il contenuto consente al messaggio protetto di essere indipendente per quanto concerne gli aspetti della protezione. Questo rende possibili alcuni scenari che non sono accessibili quando si utilizza la protezione del trasporto.  
  
## <a name="reasons-to-use-message-security"></a>Motivi per utilizzare la sicurezza dei messaggi  
 Nella protezione a livello di messaggio tutte le informazioni sulla protezione sono incapsulate nel messaggio. Di conseguenza, proteggere il messaggio con una protezione a livello di messaggio anziché una protezione a livello di trasporto offre i vantaggi seguenti:  
  
-   Protezione end-to-end. La sicurezza del trasporto, ad esempio Secure Sockets Layer (SSL), protegge i messaggi solo quando la comunicazione è da punto a punto. Se il messaggio viene instradato a uno o più intermediari SOAP (ad esempio un router) prima di raggiungere il destinatario finale, il messaggio stesso non è più protetto dopo essere stato letto da un intermediario durante la trasmissione. Inoltre, le informazioni di autenticazione del client sono disponibili solo per il primo intermediario e devono essere ritrasmesse al destinatario finale in modalità fuori banda, se necessario. Questo si applica anche se l'intera route utilizza la protezione SSL tra i singoli hop. Poiché la sicurezza dei messaggi si applica direttamente al messaggio e protegge il codice XML in esso contenuto, la sicurezza segue il messaggio indipendentemente dal numero di intermediari coinvolti prima che il messaggio raggiunga il destinatario finale. Ciò rende possibile un reale scenario di sicurezza end-to-end.  
  
-   Maggiore flessibilità. È possibile firmare o crittografare parti del messaggio, anziché l'intero messaggio. Di conseguenza, gli intermediari possono visualizzare le parti del messaggio destinate a loro. Se il mittente vuole rendere visibili alcune informazioni nel messaggio agli intermediari ma vuole assicurare che non vengano manomesse, può scegliere di firmarlo solamente, senza crittografarlo. Poiché la firma è parte del messaggio, il destinatario finale può verificare che le informazioni nel messaggio siano state ricevute intatte. In uno scenario potrebbe essere presente un servizio intermedio SOAP che indirizza il messaggio secondo il valore dell'intestazione Action. Per impostazione predefinita, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non crittografa il valore Action ma lo firma se viene utilizzata la sicurezza dei messaggi. Pertanto, queste informazioni sono disponibili a tutti gli intermediari, ma nessuno può modificarle.  
  
-   Supporto di più trasporti. È possibile inviare messaggi protetti sui più trasporti diversi, ad esempio named pipe e TCP, senza dover utilizzare il protocollo per la protezione. Con la protezione a livello di trasporto, tutte le informazioni di sicurezza sono limitate all'ambito di una sola particolare connessione del trasporto e non sono disponibili dal contenuto del messaggio stesso. La sicurezza dei messaggi protegge il messaggio indipendentemente dal trasporto utilizzato per trasmettere il messaggio e il contesto di sicurezza è direttamente incorporato nel messaggio.  
  
-   Supporto per un ampio set di credenziali e attestazioni. La sicurezza dei messaggi è basata sulla specifica WS-Security che fornisce un framework estensibile capace di trasmettere qualsiasi tipo di attestazione all'interno del messaggio SOAP. A differenza della sicurezza del trasporto, il set di meccanismi di autenticazione, o attestazioni, che è possibile utilizzare non è limitato dalle funzionalità di trasporto. La sicurezza dei messaggi in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] include più tipi di autenticazione e trasmissione delle attestazioni e può essere estesa per supportare tipi aggiuntivi, se necessario. Per questi motivi, ad esempio, un scenario di credenziali federate non è possibile senza la sicurezza dei messaggi. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]scenari della federazione WCF supporta, vedere [federazione e i token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="how-message-and-transport-security-compare"></a>Confronto tra la sicurezza dei messaggi e del trasporto  
  
### <a name="pros-and-cons-of-transport-level-security"></a>Vantaggi e svantaggi della protezione a livello di trasporto  
 La protezione del trasporto offre i vantaggi seguenti:  
  
-   Non richiede che le parti in comunicazione capiscano i concetti di sicurezza a livello di XML. Può migliorare l'interoperabilità, ad esempio, quando viene utilizzato HTTPS per proteggere la comunicazione.  
  
-   Prestazioni generalmente migliorate.  
  
-   Sono disponibili acceleratori hardware.  
  
-   Il flusso è supportato.  
  
 La protezione del trasporto offre gli svantaggi seguenti:  
  
-   Solo connessione hop-to-hop.  
  
-   Set di credenziali limitato e non estensibile.  
  
-   Dipende dal trasporto.  
  
### <a name="disadvantages-of-message-level-security"></a>Svantaggi della protezione a livello di messaggio  
 La sicurezza dei messaggi offre gli svantaggi seguenti:  
  
-   Prestazioni  
  
-   Impossibile utilizzare il flusso dei messaggi.  
  
-   Richiede l'implementazione di meccanismi di sicurezza a livello del contenuto XML e il supporto della specifica WS-Security. Ciò può influire sull'interoperabilità.  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione di servizi e client](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [Procedura: utilizzare la sicurezza del trasporto e le credenziali del messaggio](../../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)  
 [Microsoft Patterns and Practices, capitolo 3: implementazione di trasporto e messaggio di sicurezza di livello](http://go.microsoft.com/fwlink/?LinkId=88897)
