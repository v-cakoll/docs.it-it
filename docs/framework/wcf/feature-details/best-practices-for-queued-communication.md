---
title: Procedure consigliate per comunicazioni in coda
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], best practices
- best practices [WCF], queued communication
ms.assetid: 446a6383-cae3-4338-b193-a33c14a49948
ms.openlocfilehash: af9ed7d64a60042297e071262be7610c4d791a51
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601348"
---
# <a name="best-practices-for-queued-communication"></a>Procedure consigliate per comunicazioni in coda
In questo argomento vengono fornite le procedure consigliate per la comunicazione in coda in Windows Communication Foundation (WCF). Nelle sezioni seguenti vengono descritte le procedure consigliate in funzione dello scenario.  
  
## <a name="fast-best-effort-queued-messaging"></a>Messaggistica in coda di tipo veloce ed efficiente  
 Per scenari che richiedono la separazione fornita dalla messaggistica in coda nonché velocità, elevate prestazioni ed efficienza, utilizzare una coda non transazionale e impostare la proprietà <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> su `false`.  
  
 È inoltre possibile scegliere di non incorrere nell'onere delle scritture su disco impostando la proprietà <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> su `false`.  
  
 La protezione ha implicazioni sulle prestazioni. Per ulteriori informazioni, vedere [considerazioni sulle prestazioni](performance-considerations.md).  
  
## <a name="reliable-end-to-end-queued-messaging"></a>Messaggistica in coda end-to-end affidabile  
 Nelle sezioni seguenti vengono descritte le procedure consigliate per scenari che richiedono messaggistica affidabile end-to-end.  
  
### <a name="basic-reliable-transfer"></a>Trasferimento affidabile di base  
 Per l'affidabilità end-to-end, impostare la proprietà <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A> su `true` per garantire il trasferimento. La proprietà <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> può essere impostata su `true` o `false` a seconda delle necessità (l'impostazione predefinita è `true`). La proprietà <xref:System.ServiceModel.MsmqBindingBase.Durable%2A> è generalmente impostata su `true` come parte dell'affidabilità end-to-end. Ciò implica un costo in termini di prestazioni, ma rende durevole il messaggio. In questo modo il messaggio non andrà perso se il gestore delle code si arresta in modo anomalo.  
  
### <a name="use-of-transactions"></a>Utilizzo delle transazioni  
 È necessario utilizzare le transazioni per garantire l'affidabilità end-to-end. Le garanzie `ExactlyOnce` assicurano solo che i messaggi vengano recapitati alla coda di destinazione. Per garantire che il messaggio venga ricevuto, utilizzare le transazioni. Se il servizio si arresta in modo anomalo e se si opera senza transazioni, è possibile che si verifichi la perdita del messaggio che sta per essere recapitato, ma che appare come effettivamente recapitato.  
  
### <a name="use-of-dead-letter-queues"></a>Utilizzo delle code dei messaggi non recapitabili  
 Le code dei messaggi non recapitabili assicurano la ricezione di una notifica se un messaggio non viene recapitato alla coda di destinazione. È possibile utilizzare la coda dei messaggi non recapitabili fornita dal sistema o una personalizzata. È generalmente consigliato l'utilizzo di una coda dei messaggi non recapitabili personalizzata poiché consente di inviare messaggi non recapitabili da una singola applicazione a un'unica coda dei messaggi non recapitabili. In caso contrario, tutti i messaggi non recapitabili che si verificano per tutte le applicazioni in esecuzione nel sistema vengono recapitati a un'unica coda. Ogni applicazione deve quindi cercare nella coda dei messaggi non recapitabili per trovare quelli pertinenti per quell'applicazione. L'utilizzo di una coda dei messaggi non recapitabili personalizzata a volte non è possibile, ad esempio quando si utilizza MSMQ 3.0.  
  
 La disattivazione delle code dei messaggi non recapitabili per la comunicazione affidabile end-to-end non è consigliata.  
  
 Per ulteriori informazioni, vedere [utilizzo di code di messaggi non recapitabili per gestire gli errori di trasferimento dei messaggi](using-dead-letter-queues-to-handle-message-transfer-failures.md).  
  
### <a name="use-of-poison-message-handling"></a>Utilizzo della gestione dei messaggi non elaborabili  
 La gestione dei messaggi non elaborabili consente il ripristino dopo un errore per proseguire l'elaborazione dei messaggi.  
  
 Quando si utilizza la funzionalità di gestione dei messaggi non elaborabili, verificare che la proprietà <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A> sia impostata sul valore appropriato. L'impostazione della proprietà su <xref:System.ServiceModel.ReceiveErrorHandling.Drop> significa che i dati vanno persi. L'impostazione della proprietà su <xref:System.ServiceModel.ReceiveErrorHandling.Fault> genera invece errori nell'host del servizio quando viene rilevato un messaggio non elaborabile. Se si utilizza MSMQ 3.0, <xref:System.ServiceModel.ReceiveErrorHandling.Fault> è l'opzione migliore per evitare perdite di dati e per spostare il messaggio non elaborabile. Se si utilizza MSMQ 4.0, <xref:System.ServiceModel.ReceiveErrorHandling.Move> costituisce l'approccio consigliato. Il campo <xref:System.ServiceModel.ReceiveErrorHandling.Move> sposta un messaggio non elaborabile fuori dalla coda consentendo al servizio di proseguire nell'elaborazione di nuovi messaggi. Il servizio dei messaggi non elaborabili è in grado quindi di elaborare separatamente il messaggio non elaborabile.  
  
 Per ulteriori informazioni, vedere [gestione di messaggi non elaborabili](poison-message-handling.md).  
  
## <a name="achieving-high-throughput"></a>Raggiungimento di velocità effettive elevate  
 Per raggiungere velocità effettive elevate in un singolo endpoint, utilizzare gli elementi seguenti:  
  
- Batch transazionale. Il batch transazionale garantisce la lettura di molti messaggi in una singola transazione. In questo modo vengono ottimizzati i commit della transazione, aumentando le prestazioni complessive. Lo svantaggio del batch consiste nel fatto che se si verifica un errore in un singolo messaggio all'interno di un batch, verrà eseguito il rollback dell'intero batch e i messaggi dovranno essere elaborati uno alla volta fino a che il batch non sarà nuovamente sicuro. Nella maggior parte dei casi i messaggi non elaborabili sono rari, pertanto il batch è il modo preferito per aumentare le prestazioni del sistema, in particolare quando vi sono altri gestori delle risorse che partecipano alla transazione. Per ulteriori informazioni, vedere [invio in batch di messaggi in una transazione](batching-messages-in-a-transaction.md).  
  
- Concorrenza. La concorrenza aumenta la velocità effettiva, ma può anche provocare conflitti nelle risorse condivise. Per ulteriori informazioni, vedere [Concurrency](../samples/concurrency.md).  
  
- Limitazione. Per ottenere prestazioni ottimali, limitare il numero di messaggi nella pipeline del dispatcher. Per un esempio di come eseguire questa operazione, vedere [limitazione delle richieste](../samples/throttling.md).  
  
 Quando si utilizza il batch, è necessario sapere che la concorrenza e la limitazione danno luogo a batch simultanei.  
  
 Per ottenere una velocità effettiva e una disponibilità maggiori, utilizzare una farm di servizi WCF in grado di leggere dalla coda. In questo caso, tutti i servizi interessati devono esporre lo stesso contratto nello stesso endpoint. L'approccio della farm funziona in modo ottimale per applicazioni che hanno elevate frequenze di produzione di messaggi poiché consente a un certo numero di servizi di leggere dalla stessa coda.  
  
 Quando si utilizzano le farm, è necessario sapere che le letture transazionali remote non sono supportate in MSMQ 3.0. MSMQ 4.0 supporta le letture transazionali remote.  
  
 Per ulteriori informazioni, vedere [invio in batch di messaggi in una transazione](batching-messages-in-a-transaction.md) e [differenze nelle funzionalità di Accodamento in Windows Vista, Windows Server 2003 e Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md).  
  
## <a name="queuing-with-unit-of-work-semantics"></a>Accodamento con unità di semantica del lavoro  
 In alcuni scenari i messaggi raggruppati in una coda possono essere correlati insieme e, pertanto, il loro ordine è significativo. In tali scenari, viene elaborato un gruppo di messaggi correlati come singola unità. Ciò significa che tutti i messaggi vengono elaborati correttamente oppure che nessun di essi viene elaborato. Per implementare tale comportamento, utilizzare sessioni con code.  
  
 Per ulteriori informazioni, vedere [raggruppamento di messaggi in coda in una sessione](grouping-queued-messages-in-a-session.md).  
  
## <a name="correlating-request-reply-messages"></a>Correlazione di messaggi request/reply  
 Sebbene le code siano tipicamente unidirezionali, in alcuni scenari è necessario determinare una correlazione tra una risposta ricevuta a una richiesta inviata precedentemente. Se tale correlazione viene richiesta, è consigliato applicare al messaggio la propria intestazione del messaggio SOAP contenente informazioni sulla correlazione. In genere, il mittente allega questa intestazione al messaggio e il destinatario, dopo aver elaborato il messaggio e aver risposto con un messaggio nuovo in una coda di risposte, allega l'intestazione del messaggio del mittente contenente le informazioni sulla correlazione così che il mittente possa identificare il messaggio di risposta con il messaggio di richiesta.  
  
## <a name="integrating-with-non-wcf-applications"></a>Integrazione con applicazioni non WCF  
 Utilizzare `MsmqIntegrationBinding` per l'integrazione di servizi o client WCF con client o servizi non WCF. L'applicazione non WCF può essere un'applicazione MSMQ scritta utilizzando System. Messaging, COM+, Visual Basic o C++.  
  
 Quando si utilizza `MsmqIntegrationBinding`, è necessario sapere che:  
  
- Il corpo di un messaggio WCF non è uguale al corpo di un messaggio MSMQ. Quando si invia un messaggio WCF utilizzando un'associazione in coda, il corpo del messaggio WCF viene inserito all'interno di un messaggio MSMQ. L'infrastruttura MSMQ vede solo il messaggio MSMQ ignorando queste informazioni aggiuntive.  
  
- `MsmqIntegrationBinding` supporta i tipi di serializzazione più comuni. In base al tipo di serializzazione, il tipo del corpo del messaggio generico, <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>, prende parametri di tipo diverso. <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.ByteArray>, ad esempio, richiede `MsmqMessage\<byte[]>`<xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat.Stream> e `MsmqMessage<Stream>` richiede .  
  
- Con la serializzazione XML, è possibile specificare il tipo noto utilizzando l' `KnownTypes` attributo nell' [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento utilizzato per determinare la modalità di deserializzazione del messaggio XML.  
  
## <a name="see-also"></a>Vedere anche

- [Accodamento in WCF](queuing-in-wcf.md)
- [Procedura: scambiare messaggi in coda con endpoint WCF](how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Procedura: scambiare messaggi con endpoint WCF e con applicazioni del sistema di accodamento dei messaggi](how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Raggruppamento di messaggi in coda in una sessione](grouping-queued-messages-in-a-session.md)
- [Raggruppamento di messaggi in una transazione](batching-messages-in-a-transaction.md)
- [Uso di code di messaggi non recapitabili per gestire errori di trasferimento dei messaggi](using-dead-letter-queues-to-handle-message-transfer-failures.md)
- [Gestione dei messaggi non elaborabili](poison-message-handling.md)
- [Differenze nelle funzionalità di accodamento in Windows Vista, Windows Server 2003 e Windows XP](diff-in-queue-in-vista-server-2003-windows-xp.md)
- [Protezione dei messaggi mediante protezione del trasporto](securing-messages-using-transport-security.md)
- [Protezione dei messaggi mediante protezione a livello di messaggio](securing-messages-using-message-security.md)
- [Risoluzione dei problemi relativi ai messaggi in coda](troubleshooting-queued-messaging.md)
