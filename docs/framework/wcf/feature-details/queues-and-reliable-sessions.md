---
title: Code e sessioni affidabili
ms.date: 03/30/2017
ms.assetid: 7e794d03-141c-45ed-b6b1-6c0e104c1464
ms.openlocfilehash: af45fd86f673d0cc296f6593d9d5709d3e2b616e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596747"
---
# <a name="queues-and-reliable-sessions"></a>Code e sessioni affidabili
Le code e le sessioni affidabili sono le funzionalità di Windows Communication Foundation (WCF) che implementano la messaggistica affidabile. Negli argomenti contenuti in questa sezione vengono illustrate le funzionalità di messaggistica affidabile WCF.  
  
 La messaggistica affidabile riguarda il modo in cui un'origine di messaggistica affidabile (definita origine) trasferisce in modo affidabile i messaggi a una destinazione di messaggistica affidabile (definita destinazione).  
  
 Gli aspetti chiave della messaggistica affidabile sono i seguenti:  
  
- Garanzie di trasferimento dei messaggi inviati da un'origine a una destinazione indipendentemente dagli errori di trasporto o di trasferimento dei messaggi.  
  
- Separazione dell'origine e della destinazione, che fornisce funzioni di errore e un recupero indipendente dell'origine e della destinazione, nonché un trasferimento e un recapito affidabili dei messaggi, anche se l'origine o la destinazione non è disponibile.  
  
 La messaggistica affidabile comporta spesso il costo di una latenza elevata. Per latenza si intende il tempo che un messaggio impiega per giungere dall'origine alla destinazione. WCF fornisce pertanto i tipi di messaggistica affidabili seguenti:  
  
- [Sessioni affidabili](reliable-sessions.md), che offrono un trasferimento affidabile senza il costo di una latenza elevata  
  
- [Code in WCF](queues-in-wcf.md), che offrono trasferimenti affidabili e separazione tra l'origine e la destinazione.  
  
## <a name="reliable-sessions"></a>Sessioni affidabili  
 Le sessioni affidabili forniscono un trasferimento affidabile end-to-end dei messaggi tra un'origine e una destinazione utilizzando il protocollo WS-ReliableMessaging indipendentemente dal numero o dal tipo di intermediari che separano gli endpoint di messaggistica (origine e destinazione). In questo modo vengono inclusi tutti gli intermediari del trasporto che non utilizzano SOAP (ad esempio proxy HTTP) o gli intermediari che utilizzano SOAP (ad esempio bridge o router basati su SOAP) necessari per il flusso dei messaggi tra gli endpoint. Le sessioni affidabili utilizzano una finestra di trasferimento in memoria per mascherare gli errori a livello di messaggio SOAP e riattivare le connessioni in caso di errori di trasporto.  
  
 Le sessioni affidabili forniscono trasferimenti affidabili dei messaggi con una latenza bassa. Provvedono ai messaggi SOAP su qualsiasi proxy o intermediario, in modo equivalente a TCP per i pacchetti su bridge IP. Per ulteriori informazioni sulle sessioni affidabili, vedere [sessioni affidabili](reliable-sessions.md).  
  
## <a name="queues"></a>Code  
 Le code in WCF forniscono trasferimenti affidabili di messaggi e separazione tra le origini e le destinazioni al costo di una latenza elevata. La comunicazione accodata WCF si basa sul Accodamento messaggi (noto anche come MSMQ).  
  
 MSMQ viene fornito con Windows come opzione e viene eseguito come servizio NT. Acquisisce i messaggi da trasmettere in una coda di trasmissione per conto dell'origine e li recapita a una coda di destinazione. La coda di destinazione accetta i messaggi per conto della destinazione a cui verranno recapitati in seguito quando la destinazione richiede i messaggi. I gestori code MSMQ implementano un protocollo di trasferimento messaggi affidabile, in modo che i messaggi non vengano persi durante la trasmissione. Il protocollo può essere nativo o un protocollo basato su SOAP, come SRMP (SOAP Reliable Messagging Protocol).  
  
 La separazione, abbinata ai trasferimenti affidabili dei messaggi tra le code, consente alle applicazioni ad accoppiamento debole di comunicare in modo affidabile. A differenza delle sessioni affidabili, non è necessario che l'origine e la destinazione siano in esecuzione contemporaneamente. Questo consente implicitamente scenari in cui le code vengono di fatto utilizzate come un meccanismo di livellamento del carico nei casi in cui non vi è corrispondenza tra il tasso di produzione di messaggi dell'origine e il tasso di utilizzo di messaggi da parte della destinazione. Per ulteriori informazioni sulle code, vedere [code in WCF](queues-in-wcf.md).  
  
## <a name="see-also"></a>Vedere anche

- [Code in WCF](queues-in-wcf.md)
- [Accodamento in WCF](queuing-in-wcf.md)
- [Sessioni affidabili](reliable-sessions.md)
- [Panoramica delle sessioni affidabili](reliable-sessions-overview.md)
