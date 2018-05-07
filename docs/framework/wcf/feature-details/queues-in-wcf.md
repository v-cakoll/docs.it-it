---
title: Code in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
ms.openlocfilehash: 96dfee3304369c300c40d595860898c51ff728aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="queues-in-windows-communication-foundation"></a>Code in Windows Communication Foundation
Negli argomenti di questa sezione viene illustrato il supporto di Windows Communication Foundation (WCF) per le code. WCF fornisce supporto per l'accodamento da sfruttando al contempo Accodamento messaggi Microsoft (precedentemente noto come MSMQ) come trasporto e consente gli scenari seguenti:  
  
-   Applicazioni a regime di controllo libero. Le applicazioni di invio possono inviare messaggi alle code senza che sia necessario sapere se l'applicazione ricevente è disponibile per l'elaborazione del messaggio. La coda fornisce un'indipendenza di elaborazione che consente a un'applicazione di invio di inviare messaggi alla coda a una velocità indipendente da quella di elaborazione dei messaggi da parte delle applicazioni riceventi. La disponibilità complessiva del sistema aumenta quando l'invio di messaggi a una coda non è strettamente associato all'elaborazione dei messaggi.  
  
-   Isolamento degli errori. È possibile che le applicazioni di invio o di ricezione di messaggi da una coda non vengano eseguite senza influire l'una sull'altra. Se, ad esempio, l'applicazione ricevente non viene eseguita, l'applicazione di invio può continuare a inviare messaggi alla coda. Quando l'applicazione ricevente è nuovamente disponibile, sarà in grado di elaborare i messaggi provenienti dalla coda. L'isolamento degli errori aumenta l'affidabilità e la disponibilità complessive del sistema.  
  
-   Distribuzione ottimale dei carichi. Le applicazioni di invio possono sovraccaricare di messaggi le applicazioni riceventi. Le code possono gestire un livello di produzione e di consumo eccessivi di messaggi non corrispondenti al fine di evitare che il destinatario venga sovraccaricato.  
  
-   Operazioni disconnesse. Le operazioni di invio, ricezione ed elaborazione possono venire disconnesse durante la comunicazione tramite reti con latenza elevata o con disponibilità limitata, ad esempio nel caso di dispositivi mobili. Le code consentono la continuazione di queste operazioni, anche quando gli endpoint sono disconnessi. Quando la connessione viene ristabilita, la coda inoltra i messaggi all'applicazione ricevente.  
  
 Per usare la funzionalità delle code in un'applicazione WCF, è possibile utilizzare una delle associazioni standard oppure è possibile creare un'associazione personalizzata se una delle associazioni standard non soddisfa i requisiti. Per altre informazioni rilevanti associazioni standard e sulla scelta di uno, vedere [procedura: i messaggi di Exchange con endpoint WCF e le applicazioni di Accodamento messaggi](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md). Per ulteriori informazioni sulla creazione di associazioni personalizzate, vedere [associazioni personalizzate](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica delle code](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 Panoramica dei concetti di accodamento dei messaggi.  
  
 [Accodamento in WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 Una panoramica del supporto di coda WCF.  
  
 [Procedura: Scambiare messaggi in coda con endpoint WCF](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 Viene illustrato come utilizzare il <xref:System.ServiceModel.NetMsmqBinding> classe per la comunicazione tra un client WCF e servizio WCF.  
  
 [Procedura: Scambiare messaggi con endpoint WCF e con applicazioni di accodamento messaggi](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 Viene illustrato come utilizzare il <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> per le comunicazioni tra applicazioni WCF e di Accodamento messaggi.  
  
 [Raggruppamento di messaggi in coda in una sessione](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 Spiega come raggruppare messaggi in una coda per agevolare l'elaborazione di messaggi correlati da parte di un'unica applicazione ricevente.  
  
 [Invio in batch di messaggi in una transazione](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 Spiega come raggruppare messaggi in una transazione.  
  
 [Uso di code di messaggi non recapitabili per gestire gli errori di trasferimento dei messaggi](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 Spiega come gestire il trasferimento dei messaggi e gli errori di recapito utilizzando le code di messaggi non recapitabili. Spiega inoltre come elaborare messaggi dalla coda di messaggi non recapitabili.  
  
 [Gestione dei messaggi non elaborabili](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 Spiega come gestire messaggi non elaborabili, ovvero messaggi che hanno superato il numero massimo di tentativi di recapito all'applicazione ricevente.  
  
 [Differenze nelle funzionalità di accodamento in Windows Vista, Windows Server 2003 e Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 Vengono riepilogate le differenze nella funzionalità code WCF tra [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], e [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
 [Protezione dei messaggi mediante la sicurezza del trasporto](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 Descrive come utilizzare la protezione del trasporto per proteggere messaggi in coda.  
  
 [Protezione dei messaggi mediante la sicurezza dei messaggi](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 Descrive come utilizzare la protezione dei messaggi per proteggere messaggi in coda.  
  
 [Risoluzione dei problemi relativi ai messaggi in coda](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)  
 Spiega come risolvere problemi di accodamento comuni.  
  
 [Procedure consigliate per le comunicazioni in coda](../../../../docs/framework/wcf/feature-details/best-practices-for-queued-communication.md)  
 Vengono illustrate le procedure consigliate per l'utilizzo di WCF comunicazioni in coda.  
  
## <a name="see-also"></a>Vedere anche  
 [Accodamento messaggi](http://msdn.microsoft.com/library/ff917e87-05d5-478f-9430-0f560675ece1)
