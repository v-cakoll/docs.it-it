---
title: Progettazione e implementazione di servizi
ms.date: 03/30/2017
helpviewer_keywords:
- defining service contracts [WCF]
ms.assetid: 036fae20-7c55-4002-b71d-ac4466e167a3
ms.openlocfilehash: 9ddb3fe637cd0402f0ce850bc523ae8cb0c5dc37
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801969"
---
# <a name="designing-and-implementing-services"></a>Progettazione e implementazione di servizi
In questa sezione viene illustrato come definire e implementare contratti WCF. Un contratto di servizio specifica quale endpoint comunica con il mondo esterno. A un livello più concreto, è un'istruzione su un set di messaggi specifici organizzati in modelli di scambio di messaggi di base (MEP, Message Exchange Pattern) quali, ad esempio, request/reply, unidirezionale e duplex. Se un contratto di servizio è un set logicamente correlato di scambi di messaggi, un'operazione di servizio è un singolo scambio di messaggi. Un'operazione `Hello` deve, ad esempio, accettare un messaggio (quindi il chiamante può annunciare il saluto) e può o non può restituire un messaggio (a seconda del livello di cortesia dell'operazione).  
  
 Per ulteriori informazioni sui contratti e altri concetti di base di Windows Communication Foundation (WCF), vedere [concetti fondamentali di Windows Communication Foundation](fundamental-concepts.md). Questo argomento si incentra sulla comprensione dei contratti di servizio. Per ulteriori informazioni su come creare client che utilizzano contratti di servizio per connettersi ai servizi, vedere [Cenni preliminari sui client WCF](wcf-client-overview.md).  
  
## <a name="overview"></a>Panoramica di  
 In questo argomento viene fornito un orientamento concettuale di alto livello per la progettazione e l'implementazione di servizi WCF. Negli argomenti correlati vengono fornite informazioni più dettagliate sulle specifiche di progettazione e implementazione. Prima di progettare e implementare l'applicazione WCF, è consigliabile:  
  
- Comprendere cosa siano i contratti di servizio, come funzionino e come sia possibile crearne uno.  
  
- Comprendere che i contratti prevedono requisiti minimi che la configurazione di runtime o l'ambiente host potrebbe non supportare.  
  
## <a name="service-contracts"></a>Contratti di servizio  
 In un contratto di servizio viene specificato quanto segue:  
  
- Le operazioni esposte nel contratto.  
  
- Forma delle operazioni in termini di messaggi scambiati.  
  
- Tipi di dati di questi messaggi.  
  
- Posizione delle operazioni.  
  
- Protocolli e formati di serializzazione specifici usati per supportare la corretta comunicazione con il servizio.  
  
 Un contratto di ordine di acquisto può, ad esempio, includere un'operazione `CreateOrder` che accetta un input di tipi di informazioni sull'ordine e restituisce informazioni sull'esito positivo o negativo, incluso un identificatore di ordine. Può inoltre includere un'operazione `GetOrderStatus` che accetta un identificatore di ordine e restituisce informazioni sullo stato dell'ordine. Un contratto di servizio di questo tipo specificherebbe:  
  
1. Che il contratto di ordine di acquisto è costituito da operazioni `CreateOrder` e `GetOrderStatus`.  
  
2. Che le operazioni hanno specificato messaggi di input e di output.  
  
3. I dati che questi messaggi possono contenere.  
  
4. Istruzioni categoriali sull'infrastruttura di comunicazione necessaria per elaborare correttamente i messaggi. Questi dettagli includono, ad esempio, indicazioni sulla necessità della protezione, e sui tipi di sicurezza eventualmente necessari, per stabilire una corretta comunicazione.  
  
 Per fornire questo tipo di informazioni ad altre applicazioni su molte piattaforme (incluse piattaforme non Microsoft), i contratti di servizio XML vengono pubblicamente espressi in formati XML standard, ad esempio [Web Services Description Language](https://www.w3.org/TR/2001/NOTE-wsdl-20010315) (WSDL) e [XML Schema](https://www.w3.org/XML/Schema) (XSD), tra gli altri. Gli sviluppatori operanti su molte piattaforme possono usare queste informazioni pubbliche sui contratti per creare applicazioni che possano comunicare con il servizio, perché comprendono il linguaggio della specifica e perché tali linguaggi sono progettati per consentire l'interoperabilità descrivendo i tipi, i formati e i protocolli pubblici supportati dal servizio. Per ulteriori informazioni sul modo in cui WCF gestisce questo tipo di informazioni, vedere [Metadata](./feature-details/metadata.md).  
  
 I contratti possono essere espressi in molti modi e, sebbene WSDL e XSD siano eccellenti per descrivere i servizi in modo accessibile, sono linguaggi difficili da utilizzare direttamente e costituiscono semplici descrizioni di un servizio, non implementazioni del contratto di servizio. Pertanto, le applicazioni WCF utilizzano attributi, interfacce e classi gestiti sia per definire la struttura di un servizio che per implementarla.  
  
 Il contratto risultante definito nei tipi gestiti può essere *esportato* come metadati, WSDL e XSD, quando richiesto dai client o da altri implementatori del servizio. Il risultato è un modello di programmazione semplice, che può essere descritto (utilizzando metadati pubblici) per qualsiasi applicazione client. I dettagli dei messaggi SOAP sottostanti, le informazioni relative al trasporto e alla sicurezza e così via, possono essere lasciati a WCF, che esegue automaticamente le conversioni necessarie da e verso il sistema dei tipi di contratto di servizio nel sistema di tipi XML.  
  
 Per ulteriori informazioni sulla progettazione di contratti, vedere [progettazione di contratti di servizio](designing-service-contracts.md). Per ulteriori informazioni sull'implementazione di contratti, vedere [implementazione di contratti di servizio](implementing-service-contracts.md).  
  
### <a name="messages-up-front-and-center"></a>Orientamento ai messaggi  
 L'utilizzo di interfacce, classi e metodi gestiti per modellare le operazioni di servizio è piuttosto semplice se si utilizzano abitualmente firme dei metodi in stile RPC (Remote Procedure Call), in cui il passaggio di parametri in un metodo e la restituzione di valori costituiscono la forma standard per richiedere la funzionalità di un oggetto o di un altro tipo di codice. Ad esempio, i programmatori che utilizzano linguaggi gestiti come Visual Basic C++ e com possono applicare le proprie conoscenze sull'approccio di tipo RPC (usando oggetti o interfacce) per la creazione di contratti di servizio WCF senza riscontrare i problemi inerenti i sistemi di oggetti distribuiti di tipo RPC. L'orientamento ai servizi offre il vantaggio di una programmazione orientata ai messaggi, ad accoppiamento debole, mantenendo comunque la semplicità della programmazione RPC.  
  
 Molti programmatori preferiscono utilizzare interfacce di programmazione di applicazioni orientate ai messaggi, ad esempio le code di messaggi come Microsoft MSMQ, gli spazi dei nomi <xref:System.Messaging> di .NET Framework o l'invio di XML non strutturato nelle richieste HTTP, solo per citarne alcune. Per ulteriori informazioni sulla programmazione a livello di messaggio, vedere [utilizzo di contratti di messaggio](./feature-details/using-message-contracts.md), [programmazione a livello di canale del servizio](./extending/service-channel-level-programming.md)e [interoperabilità con applicazioni POX](./feature-details/interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>Informazioni sulla gerarchia di requisiti  
 Un contratto di servizio raggruppa le operazioni, specifica il modello di scambio dei messaggi, i tipi di messaggio e i tipi di dati contenuti nei messaggi e indica le categorie di comportamento runtime che un'implementazione deve avere per supportare il contratto (se, ad esempio, è necessario che i messaggi siano crittografati e firmati). Il contratto di servizio stesso non specifica con precisione in che modo vengono soddisfatti questi requisiti, ma solo che devono essere soddisfatti. Il tipo di crittografia e la modalità di firma di un messaggio dipendono dall'implementazione e dalla configurazione di un servizio conforme.  
  
 Si noti il modo in cui il contratto richiede certe caratteristiche dell'implementazione del contratto di servizio e della configurazione di runtime per l'aggiunta di un comportamento. Il set dei requisiti che devono essere soddisfatti per esporre un servizio affinché possa essere usato si basa sul set di requisiti precedente. Se un contratto prevede requisiti per l'implementazione, un'implementazione può richiedere ancora più caratteristiche di configurazione e associazioni che consentono l'esecuzione del servizio. Infine, anche l'applicazione host deve supportare tutti i requisiti aggiunti dalla configurazione e dalle associazioni del servizio.  
  
 Questo processo di requisito aggiuntivo è importante da tenere presente durante la progettazione, l'implementazione, la configurazione e l'hosting di un'applicazione di servizio Windows Communication Foundation (WCF). Il contratto può, ad esempio, specificare che deve essere supportata una sessione. In questo caso sarà quindi necessario configurare le associazioni per supportare il requisito contrattuale o l'implementazione del servizio non funzionerà. Se il servizio richiede invece l'autenticazione integrata di Windows ed è ospitato in Internet Information Services (IIS), nell'applicazione Web in cui risiede il servizio deve essere attivata l'autenticazione integrata di Windows e disattivato il supporto di utenti anonimi. Per ulteriori informazioni sulle funzionalità e l'effetto dei diversi tipi di applicazioni host del servizio, vedere [servizi di hosting](hosting-services.md).  
  
## <a name="see-also"></a>Vedere anche

- [Progettazione dei contratti di servizio](designing-service-contracts.md)
- [Implementazione dei contratti di servizio](implementing-service-contracts.md)
