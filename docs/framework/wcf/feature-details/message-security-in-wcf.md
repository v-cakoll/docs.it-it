---
title: Protezione dei messaggi in WCF
ms.date: 03/30/2017
ms.assetid: a80efb59-591a-4a37-bb3c-8fffa6ca0b7d
ms.openlocfilehash: 6875339df327371a79bc9b9072aca2df0bc7d3f6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602661"
---
# <a name="message-security-in-wcf"></a>Protezione dei messaggi in WCF

Windows Communication Foundation (WCF) dispone di due modalità principali per fornire sicurezza ( `Transport` e `Message` ) e una terza modalità ( `TransportWithMessageCredential` ) che combina i due. In questo argomento viene illustrata la sicurezza dei messaggi e i motivi per cui è consigliabile utilizzarla.

## <a name="what-is-message-security"></a>Informazioni sulla sicurezza dei messaggi

La sicurezza dei messaggi si avvale della specifica WS-Security per proteggere i messaggi. La specifica WS-Security descrive i miglioramenti apportati alla messaggistica SOAP per garantire riservatezza, integrità e autenticazione a livello di messaggio SOAP (anziché a livello di trasporto).

In breve, la sicurezza dei messaggi differisce dalla protezione del trasporto in quanto incapsula le credenziali e le attestazioni di sicurezza in ogni messaggio insieme a qualsiasi tipo di sicurezza del messaggio (con firma o crittografia). L'applicazione diretta della protezione al messaggio modificando il contenuto consente al messaggio protetto di essere indipendente per quanto concerne gli aspetti della protezione. Questo rende possibili alcuni scenari che non sono accessibili quando si utilizza la protezione del trasporto.

## <a name="reasons-to-use-message-security"></a>Motivi per utilizzare la sicurezza dei messaggi

Nella protezione a livello di messaggio tutte le informazioni sulla protezione sono incapsulate nel messaggio. Di conseguenza, proteggere il messaggio con una protezione a livello di messaggio anziché una protezione a livello di trasporto offre i vantaggi seguenti:

- Protezione end-to-end. La sicurezza del trasporto, ad esempio Secure Sockets Layer (SSL), protegge i messaggi solo quando la comunicazione è da punto a punto. Se il messaggio viene instradato a uno o più intermediari SOAP (ad esempio un router) prima di raggiungere il destinatario finale, il messaggio stesso non è più protetto dopo essere stato letto da un intermediario durante la trasmissione. Inoltre, le informazioni di autenticazione del client sono disponibili solo per il primo intermediario e devono essere ritrasmesse al destinatario finale in modalità fuori banda, se necessario. Questo si applica anche se l'intera route utilizza la protezione SSL tra i singoli hop. Poiché la sicurezza dei messaggi si applica direttamente al messaggio e protegge il codice XML in esso contenuto, la sicurezza segue il messaggio indipendentemente dal numero di intermediari coinvolti prima che il messaggio raggiunga il destinatario finale. Ciò rende possibile un reale scenario di sicurezza end-to-end.

- Maggiore flessibilità. È possibile firmare o crittografare parti del messaggio, anziché l'intero messaggio. Di conseguenza, gli intermediari possono visualizzare le parti del messaggio destinate a loro. Se il mittente vuole rendere visibili alcune informazioni nel messaggio agli intermediari ma vuole assicurare che non vengano manomesse, può scegliere di firmarlo solamente, senza crittografarlo. Poiché la firma è parte del messaggio, il destinatario finale può verificare che le informazioni nel messaggio siano state ricevute intatte. In uno scenario potrebbe essere presente un servizio intermedio SOAP che indirizza il messaggio secondo il valore dell'intestazione Action. Per impostazione predefinita, WCF non crittografa il valore dell'azione, ma lo firma se viene utilizzata la sicurezza dei messaggi. Pertanto, queste informazioni sono disponibili a tutti gli intermediari, ma nessuno può modificarle.

- Supporto di più trasporti. È possibile inviare messaggi protetti sui più trasporti diversi, ad esempio named pipe e TCP, senza dover utilizzare il protocollo per la protezione. Con la protezione a livello di trasporto, tutte le informazioni di sicurezza sono limitate all'ambito di una sola particolare connessione del trasporto e non sono disponibili dal contenuto del messaggio stesso. La sicurezza dei messaggi protegge il messaggio indipendentemente dal trasporto utilizzato per trasmettere il messaggio e il contesto di sicurezza è direttamente incorporato nel messaggio.

- Supporto per un ampio set di credenziali e attestazioni. La sicurezza dei messaggi è basata sulla specifica WS-Security che fornisce un framework estensibile capace di trasmettere qualsiasi tipo di attestazione all'interno del messaggio SOAP. A differenza della sicurezza del trasporto, il set di meccanismi di autenticazione, o attestazioni, che è possibile utilizzare non è limitato dalle funzionalità di trasporto. La sicurezza dei messaggi WCF include più tipi di autenticazione e trasmissione delle attestazioni e può essere estesa per supportare tipi aggiuntivi, se necessario. Per questi motivi, ad esempio, un scenario di credenziali federate non è possibile senza la sicurezza dei messaggi. Per ulteriori informazioni sugli scenari di federazione supportati da WCF, vedere [Federazione e token emessi](federation-and-issued-tokens.md).

## <a name="how-message-and-transport-security-compare"></a>Confronto tra la sicurezza dei messaggi e del trasporto

### <a name="pros-and-cons-of-transport-level-security"></a>Vantaggi e svantaggi della protezione a livello di trasporto

La protezione del trasporto offre i vantaggi seguenti:

- Non richiede che le parti in comunicazione capiscano i concetti di sicurezza a livello di XML. Può migliorare l'interoperabilità, ad esempio, quando viene utilizzato HTTPS per proteggere la comunicazione.

- Prestazioni generalmente migliorate.

- Sono disponibili acceleratori hardware.

- Il flusso è supportato.

 La protezione del trasporto offre gli svantaggi seguenti:

- Solo connessione hop-to-hop.

- Set di credenziali limitato e non estensibile.

- Dipende dal trasporto.

### <a name="disadvantages-of-message-level-security"></a>Svantaggi della protezione a livello di messaggio

La sicurezza dei messaggi offre gli svantaggi seguenti:

- Prestazioni

- Impossibile utilizzare il flusso dei messaggi.

- Richiede l'implementazione di meccanismi di sicurezza a livello del contenuto XML e il supporto della specifica WS-Security. Ciò può influire sull'interoperabilità.

## <a name="see-also"></a>Vedere anche

- [Securing Services and Clients](securing-services-and-clients.md)
- [Sicurezza del trasporto](transport-security.md)
- [Procedura: usare le funzionalità di sicurezza a livello di trasporto e le credenziali a livello di messaggio](how-to-use-transport-security-and-message-credentials.md)
- [Microsoft Patterns and Practices, Capitolo 3: Implementazione della protezione a livello di trasporto e di messaggio (il contenuto potrebbe essere in inglese)](https://docs.microsoft.com/previous-versions/msp-n-p/ff647370(v=pandp.10))
