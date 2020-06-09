---
title: Contratti
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], contracts
- contracts [WCF]
- Windows Communication Foundation [WCF], contracts
ms.assetid: c8364183-4ac1-480b-804a-c5e6c59a5d7d
ms.openlocfilehash: 1cd7e54d50e7116c71c040df1965674a4fdaff13
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595596"
---
# <a name="contracts"></a>Contratti
In questa sezione viene illustrato come definire e implementare contratti di Windows Communication Foundation (WCF). Un contratto di servizio specifica quale endpoint comunica con il mondo esterno. A un livello più concreto, è un'istruzione su un set di messaggi specifici organizzati in modelli di scambio di messaggi di base (MEP, Message Exchange Pattern) quali, ad esempio, request/reply, unidirezionale e duplex. Se un contratto di servizio è un set logicamente correlato di scambi di messaggi, un'operazione di servizio è un singolo scambio di messaggi. Un'operazione `Hello` deve, ad esempio, accettare un messaggio (quindi il chiamante può annunciare il saluto) e può o non può restituire un messaggio (a seconda del livello di cortesia dell'operazione).  
  
 Per ulteriori informazioni sui contratti e altri concetti di base relativi a WCF, vedere [concetti fondamentali Windows Communication Foundation](../fundamental-concepts.md). Questo argomento si incentra sulla comprensione dei contratti di servizio. Per ulteriori informazioni su come creare client che utilizzano contratti di servizio per connettersi ai servizi, vedere [Cenni preliminari sui client WCF](../wcf-client-overview.md). Per ulteriori informazioni sui canali client, l'architettura client e altri problemi relativi ai client, vedere [client](clients.md).  
  
## <a name="overview"></a>Panoramica  
 In questo argomento viene fornito un orientamento concettuale di alto livello per la progettazione e l'implementazione di servizi WCF. Negli argomenti correlati vengono fornite informazioni più dettagliate sulle specifiche di progettazione e implementazione. Prima di progettare e implementare l'applicazione WCF, è consigliabile:  
  
- Comprendere cosa siano i contratti di servizio, come funzionino e come sia possibile crearne uno.  
  
- Comprendere che i contratti prevedono requisiti minimi che la configurazione di runtime o l'ambiente host potrebbe non supportare.  
  
## <a name="service-contracts"></a>Contratti di servizio  
 Un contratto di servizio è un'istruzione che fornisce informazioni sugli argomenti seguenti:  
  
- Raggruppamento di operazioni in un servizio.  
  
- Forma delle operazioni in termini di messaggi scambiati.  
  
- Tipi di dati di questi messaggi.  
  
- Posizione delle operazioni.  
  
- Protocolli e formati di serializzazione specifici usati per supportare la corretta comunicazione con il servizio.  
  
 Un contratto di ordine di acquisto può, ad esempio, includere un'operazione `CreateOrder` che accetta un input di tipi di informazioni sull'ordine e restituisce informazioni sull'esito positivo o negativo, incluso un identificatore di ordine. Può inoltre includere un'operazione `GetOrderStatus` che accetta un identificatore di ordine e restituisce informazioni sullo stato dell'ordine. Un contratto di servizio di questo tipo specificherebbe:  
  
- Che il contratto di ordine di acquisto è costituito da operazioni `CreateOrder` e `GetOrderStatus`.  
  
- Che le operazioni hanno specificato messaggi di input e di output.  
  
- I dati che questi messaggi possono contenere.  
  
- Istruzioni categoriali sull'infrastruttura di comunicazione necessaria per elaborare correttamente i messaggi. Questi dettagli includono, ad esempio, indicazioni sulla necessità della protezione, e sui tipi di sicurezza eventualmente necessari, per stabilire una corretta comunicazione.  
  
 Per fornire questo tipo di informazioni alle applicazioni su altre piattaforme (incluse piattaforme non Microsoft), i contratti di servizio XML vengono pubblicamente espressi in formati XML standard, ad esempio [Web Services Description Language (WSDL)](https://www.w3.org/TR/2001/NOTE-wsdl-20010315) e [XML Schema (XSD)](https://www.w3.org/XML/Schema), tra gli altri. Gli sviluppatori operanti su molte piattaforme possono usare queste informazioni pubbliche sui contratti per creare applicazioni che possano comunicare con il servizio, perché comprendono il linguaggio della specifica e perché tali linguaggi sono progettati per consentire l'interoperabilità descrivendo i tipi, i formati e i protocolli pubblici supportati dal servizio. Per ulteriori informazioni sul modo in cui WCF gestisce questo tipo di informazioni, vedere [Metadata](metadata.md).  
  
 I contratti possono essere però espressi in molti modi e, sebbene WSDL e XSD siano linguaggi eccellenti per descrivere i servizi in maniera accessibile, sono però difficili da usare in modo diretto e sono, in ogni caso, semplici descrizioni di un servizio, che non riguardano le implementazioni del contratto di servizio. Pertanto, le applicazioni WCF utilizzano attributi, interfacce e classi gestiti sia per definire la struttura di che per implementare un servizio.  
  
 Il contratto risultante definito nei tipi gestiti può essere convertito (chiamato anche *esportato*) come metadati, WSDL e XSD, quando richiesto dai client o da altri implementatori del servizio, in particolare su altre piattaforme. Il risultato è un modello di programmazione semplice, che può essere descritto usando metadati pubblici per qualsiasi applicazione client. I dettagli dei messaggi SOAP sottostanti, ad esempio le informazioni relative al trasporto e alla sicurezza, possono essere lasciati a WCF, che esegue automaticamente le conversioni necessarie da e verso il sistema dei tipi di contratto di servizio nel sistema di tipi XML.  
  
 Per ulteriori informazioni sulla progettazione di contratti, vedere [progettazione di contratti di servizio](../designing-service-contracts.md). Per ulteriori informazioni sull'implementazione di contratti, vedere [implementazione di contratti di servizio](../implementing-service-contracts.md).  
  
 Inoltre, WCF consente di sviluppare contratti di servizio interamente a livello di messaggio. Per ulteriori informazioni sullo sviluppo di contratti di servizio a livello di messaggio, vedere [utilizzo dei contratti di messaggio](using-message-contracts.md). Per ulteriori informazioni sullo sviluppo di servizi in codice XML non SOAP, vedere [interoperabilità con applicazioni POX](interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Informazioni sulla gerarchia di requisiti  
 Un contratto di servizio raggruppa le operazioni, specifica il MEP, i tipi di messaggio e i tipi di dati contenuti nei messaggi e indica le categorie di comportamento di runtime che un'implementazione deve avere per supportare il contratto (se, ad esempio, è necessario che i messaggi siano crittografati e firmati). Il contratto di servizio stesso non specifica, tuttavia, con precisione in che modo questi requisiti siano soddisfatti, indica solo che devono essere soddisfatti. Il tipo di crittografia e la modalità di firma di un messaggio dipendono dall'implementazione e dalla configurazione di un servizio conforme.  
  
 Si noti il modo in cui il contratto richiede certe caratteristiche dell'implementazione del contratto di servizio e della configurazione di runtime per l'aggiunta di un comportamento. Il set dei requisiti che devono essere soddisfatti per esporre un servizio affinché possa essere usato si basa sul set di requisiti precedente. Se un contratto prevede requisiti per l'implementazione, un'implementazione può richiedere ancora più caratteristiche di configurazione e associazioni che consentono l'esecuzione del servizio. Infine, anche l'applicazione host deve supportare tutti i requisiti aggiunti dalla configurazione e dalle associazioni del servizio.  
  
 Questo processo di requisito aggiuntivo è importante da tenere presente quando si progetta, implementa, configura e ospita l'applicazione di servizio Windows Communication Foundation (WCF). Il contratto può, ad esempio, specificare che deve essere supportata una sessione. In questo caso sarà quindi necessario configurare le associazioni per supportare il requisito contrattuale o l'implementazione del servizio non funzionerà. Se il servizio richiede invece l'Autenticazione integrata di Windows ed è ospitato in Internet Information Services (IIS), nell'applicazione Web in cui risiede il servizio deve essere attivata l'Autenticazione integrata di Windows e disattivato il supporto di utenti anonimi. Per ulteriori informazioni sulle funzionalità e l'effetto dei diversi tipi di applicazioni host del servizio, vedere [hosting](hosting.md).  
  
## <a name="see-also"></a>Vedere anche

- [Endpoint: indirizzi, associazioni e contratti](endpoints-addresses-bindings-and-contracts.md)
- [Progettazione dei contratti di servizio](../designing-service-contracts.md)
- [Implementazione dei contratti di servizio](../implementing-service-contracts.md)
