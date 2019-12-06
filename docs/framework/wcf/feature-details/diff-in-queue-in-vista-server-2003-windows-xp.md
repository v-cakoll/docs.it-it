---
title: Differenze nelle funzionalità di accodamento in Windows Vista, Windows Server 2003 e Windows XP
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], differences in operating systems
ms.assetid: aa809d93-d0a3-4ae6-a726-d015cca37c04
ms.openlocfilehash: 77491981bdef7d02da6894cbbee93c779972d803
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837428"
---
# <a name="differences-in-queuing-features-in-windows-vista-windows-server-2003-and-windows-xp"></a>Differenze nelle funzionalità di accodamento in Windows Vista, Windows Server 2003 e Windows XP
In questo argomento vengono riepilogate le differenze nella funzionalità di Accodamento Windows Communication Foundation (WCF) tra Windows Vista, [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]e [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
## <a name="application-specific-dead-letter-queue"></a>Coda di messaggi non recapitabili specifica dell'applicazione  
 I messaggi in coda possono restare nella coda per un tempo indefinito se l'applicazione ricevente non li legge in maniera tempestiva. Questo comportamento non è consigliabile se i messaggi hanno una scadenza. I messaggi a scadenza hanno la proprietà `TimeToLive` impostata nell'associazione in coda. Questa proprietà indica per quanto tempo i messaggi possono restare nella coda prima di scadere. I messaggi scaduti vengono inviati a una coda speciale denominata coda dei messaggi non recapitabili. Un messaggio può finire in una coda di messaggi non recapitabili anche per altri motivi, ad esempio se si supera una quota della coda o si verifica un errore di autenticazione.  
  
 In genere, esiste una sola coda di messaggi non recapitabili a livello di sistema per tutte le applicazioni in coda che condividono un gestore delle code Con una coda di messaggi non recapitabili per ogni applicazione è possibile migliorare l'isolamento tra le applicazioni in coda che condividono un gestore delle code, consentendo a queste applicazioni di specificare una coda di messaggi non recapitabili specifica dell'applicazione. Un'applicazione che condivide una coda di messaggi non recapitabili con altre applicazioni deve esplorare la coda per trovare i messaggi appropriati. Con una coda di messaggi non recapitabili specifica dell'applicazione, tutti i messaggi nella relativa coda di messaggi non recapitabili sono applicabili all'applicazione.  
  
 Windows Vista fornisce le code dei messaggi non recapitabili specifici dell'applicazione. Tali code non sono invece disponibili in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)], pertanto le applicazioni devono utilizzare la coda di messaggi non recapitabili a livello di sistema.  
  
## <a name="poison-message-handling"></a>Gestione dei messaggi non elaborabili  
 Per messaggio non elaborabile si intende un messaggio che ha superato il numero massimo di tentativi di recapito all'applicazione ricevente. Questa situazione può verificarsi quando un'applicazione che legge un messaggio da una coda transazionale non può elaborare immediatamente il messaggio a causa di errori. Se l'applicazione interrompe la transazione nella quale è stato ricevuto il messaggio in coda, il messaggio viene restituito alla coda. L'applicazione tenta quindi di recuperare nuovamente il messaggio in una nuova transazione. Se il problema che causa l'interruzione della transazione non viene risolto, l'applicazione ricevente può rimanere bloccata in un ciclo continuo di ricezioni e interruzioni dello stesso messaggio fino a superare il numero massimo di tentativi di recapito. Ne consegue l'impossibilità di elaborare il messaggio.  
  
 Di seguito sono riportate le differenze principali tra Accodamento messaggi (MSMQ) in Windows Vista, [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]e [!INCLUDE[wxp](../../../../includes/wxp-md.md)] rilevanti per la gestione dei veleni:  
  
- MSMQ in Windows Vista supporta le code secondarie, mentre [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)] non supportano le code secondarie. Le code secondarie vengono utilizzate nella gestione dei messaggi non elaborabili. Le code di tentativi e la coda non elaborabile sono code secondarie della coda dell'applicazione creata in base alle impostazioni di gestione dei messaggi non elaborabili. `MaxRetryCycles` stabilisce il numero delle code secondarie dei tentativi che verranno create. Di conseguenza, in caso di esecuzione in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], `MaxRetryCycles` viene ignorato e `ReceiveErrorHandling.Move` non è consentito.  
  
- MSMQ in Windows Vista supporta il riconoscimento negativo, mentre [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)] non lo sono. Un negative acknowledgment dal gestore delle code ricevente determina l'inserimento, da parte del gestore delle code mittente, del messaggio respinto nella coda dei messaggi non recapitabili. Per questa ragione, `ReceiveErrorHandling.Reject` non è consentito con [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
- MSMQ in Windows Vista supporta una proprietà del messaggio che mantiene il conteggio del numero di tentativi di recapito dei messaggi. Questa proprietà del numero di interruzioni non è disponibile in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. WCF mantiene il conteggio delle interruzioni in memoria, pertanto è possibile che questa proprietà non contenga un valore accurato quando lo stesso messaggio viene letto da più di un servizio WCF in una Web farm.  
  
## <a name="remote-transactional-read"></a>Lettura transazionale in remoto  
 MSMQ in Windows Vista supporta le letture transazionali remote. Ciò consente a un'applicazione che sta leggendo da una coda di essere ospitata in un computer che è diverso da quello in cui è ospitata la coda. In questo modo è possibile disporre di una farm di servizi che leggono da una coda centrale, con conseguente aumento della velocità effettiva complessiva del sistema. Inoltre, se si verifica un errore durante la lettura e l'elaborazione del messaggio, viene eseguito il rollback della transazione e il messaggio rimane nella coda per poter essere elaborato in seguito.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di code di messaggi non recapitabili per gestire gli errori di trasferimento dei messaggi](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)
- [Gestione dei messaggi non elaborabili](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
