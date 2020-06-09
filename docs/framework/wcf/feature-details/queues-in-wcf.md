---
title: Code in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
ms.openlocfilehash: d1fee4fdde18563ec6ccce4f0675d8581184be08
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596734"
---
# <a name="queues-in-windows-communication-foundation"></a>Code in Windows Communication Foundation
Negli argomenti di questa sezione viene illustrato il supporto di Windows Communication Foundation (WCF) per le code di. WCF fornisce il supporto per l'accodamento sfruttando Microsoft Message Queuing (precedentemente noto come MSMQ) come trasporto e consente gli scenari seguenti:  
  
- Applicazioni a regime di controllo libero. Le applicazioni di invio possono inviare messaggi alle code senza che sia necessario sapere se l'applicazione ricevente è disponibile per l'elaborazione del messaggio. La coda fornisce un'indipendenza di elaborazione che consente a un'applicazione di invio di inviare messaggi alla coda a una velocità indipendente da quella di elaborazione dei messaggi da parte delle applicazioni riceventi. La disponibilità complessiva del sistema aumenta quando l'invio di messaggi a una coda non è strettamente associato all'elaborazione dei messaggi.  
  
- Isolamento degli errori. È possibile che le applicazioni di invio o di ricezione di messaggi da una coda non vengano eseguite senza influire l'una sull'altra. Se, ad esempio, l'applicazione ricevente non viene eseguita, l'applicazione di invio può continuare a inviare messaggi alla coda. Quando l'applicazione ricevente è nuovamente disponibile, sarà in grado di elaborare i messaggi provenienti dalla coda. L'isolamento degli errori aumenta l'affidabilità e la disponibilità complessive del sistema.  
  
- Distribuzione ottimale dei carichi. Le applicazioni di invio possono sovraccaricare di messaggi le applicazioni riceventi. Le code possono gestire un livello di produzione e di consumo eccessivi di messaggi non corrispondenti al fine di evitare che il destinatario venga sovraccaricato.  
  
- Operazioni disconnesse. Le operazioni di invio, ricezione ed elaborazione possono venire disconnesse durante la comunicazione tramite reti con latenza elevata o con disponibilità limitata, ad esempio nel caso di dispositivi mobili. Le code consentono la continuazione di queste operazioni, anche quando gli endpoint sono disconnessi. Quando la connessione viene ristabilita, la coda inoltra i messaggi all'applicazione ricevente.  
  
 Per utilizzare la funzionalità code in un'applicazione WCF, è possibile utilizzare una delle associazioni standard oppure è possibile creare un'associazione personalizzata se una delle associazioni standard non soddisfa i requisiti. Per ulteriori informazioni sulle associazioni standard pertinenti e su come sceglierne una, vedere [procedura: scambiare messaggi con endpoint WCF e applicazioni di Accodamento messaggi](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md). Per altre informazioni sulla creazione di associazioni personalizzate, vedere [Associazioni personalizzate](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica delle code](queues-overview.md)  
 Panoramica dei concetti di accodamento dei messaggi.  
  
 [Accodamento in WCF](queuing-in-wcf.md)  
 Panoramica del supporto per le code WCF.  
  
 [Procedura: scambiare messaggi in coda con endpoint WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 Viene illustrato come utilizzare la <xref:System.ServiceModel.NetMsmqBinding> classe per comunicare tra un client WCF e un servizio WCF.  
  
 [Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 Viene illustrato come utilizzare <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> per la comunicazione tra WCF e le applicazioni di Accodamento messaggi.  
  
 [Raggruppamento di messaggi in coda in una sessione](grouping-queued-messages-in-a-session.md)  
 Spiega come raggruppare messaggi in una coda per agevolare l'elaborazione di messaggi correlati da parte di un'unica applicazione ricevente.  
  
 [Raggruppamento di messaggi in una transazione](batching-messages-in-a-transaction.md)  
 Spiega come raggruppare messaggi in una transazione.  
  
 [Uso di code di messaggi non recapitabili per gestire errori di trasferimento dei messaggi](using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 Spiega come gestire il trasferimento dei messaggi e gli errori di recapito utilizzando le code di messaggi non recapitabili. Spiega inoltre come elaborare messaggi dalla coda di messaggi non recapitabili.  
  
 [Gestione dei messaggi non elaborabili](poison-message-handling.md)  
 Spiega come gestire messaggi non elaborabili, ovvero messaggi che hanno superato il numero massimo di tentativi di recapito all'applicazione ricevente.  
  
 [Differenze nelle funzionalità di accodamento in Windows Vista, Windows Server 2003 e Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md)  
 Riepiloga le differenze nella funzionalità code WCF tra Windows Vista, Windows Server 2003 e Windows XP.  
  
 [Protezione dei messaggi mediante protezione del trasporto](securing-messages-using-transport-security.md)  
 Descrive come utilizzare la protezione del trasporto per proteggere messaggi in coda.  
  
 [Protezione dei messaggi mediante protezione a livello di messaggio](securing-messages-using-message-security.md)  
 Descrive come utilizzare la protezione dei messaggi per proteggere messaggi in coda.  
  
 [Risoluzione dei problemi relativi ai messaggi in coda](troubleshooting-queued-messaging.md)  
 Spiega come risolvere problemi di accodamento comuni.  
  
 [Procedure consigliate per comunicazioni in coda](best-practices-for-queued-communication.md)  
 Illustra le procedure consigliate per l'utilizzo della comunicazione accodata WCF.  
