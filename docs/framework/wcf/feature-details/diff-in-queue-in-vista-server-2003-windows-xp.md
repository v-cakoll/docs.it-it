---
title: Differenze nelle funzionalità di accodamento in Windows Vista, Windows Server 2003 e Windows XP
ms.date: 03/30/2017
helpviewer_keywords:
- queues [WCF], differences in operating systems
ms.assetid: aa809d93-d0a3-4ae6-a726-d015cca37c04
ms.openlocfilehash: 5bbae7e54160923e973ff6a8adb655587adf1002
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708831"
---
# <a name="differences-in-queuing-features-in-windows-vista-windows-server-2003-and-windows-xp"></a>Differenze nelle funzionalità di accodamento in Windows Vista, Windows Server 2003 e Windows XP
In questo argomento vengono riepilogate le differenze nella funzionalità di code di Windows Communication Foundation (WCF) tra [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], e [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
## <a name="application-specific-dead-letter-queue"></a>Coda di messaggi non recapitabili specifica dell'applicazione  
 I messaggi in coda possono restare nella coda per un tempo indefinito se l'applicazione ricevente non li legge in maniera tempestiva. Questo comportamento non è consigliabile se i messaggi hanno una scadenza. I messaggi a scadenza hanno la proprietà `TimeToLive` impostata nell'associazione in coda. Questa proprietà indica per quanto tempo i messaggi possono restare nella coda prima di scadere. I messaggi scaduti vengono inviati a una coda speciale denominata coda dei messaggi non recapitabili. Un messaggio può finire in una coda di messaggi non recapitabili anche per altri motivi, ad esempio se si supera una quota della coda o si verifica un errore di autenticazione.  
  
 In genere, esiste una sola coda di messaggi non recapitabili a livello di sistema per tutte le applicazioni in coda che condividono un gestore delle code Con una coda di messaggi non recapitabili per ogni applicazione è possibile migliorare l'isolamento tra le applicazioni in coda che condividono un gestore delle code, consentendo a queste applicazioni di specificare una coda di messaggi non recapitabili specifica dell'applicazione. Un'applicazione che condivide una coda di messaggi non recapitabili con altre applicazioni deve esplorare la coda per trovare i messaggi appropriati. Con una coda di messaggi non recapitabili specifica dell'applicazione, tutti i messaggi nella relativa coda di messaggi non recapitabili sono applicabili all'applicazione.  
  
 [!INCLUDE[wv](../../../../includes/wv-md.md)] fornisce code di messaggi non recapitabili specifiche dell'applicazione. Tali code non sono invece disponibili in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)], pertanto le applicazioni devono utilizzare la coda di messaggi non recapitabili a livello di sistema.  
  
## <a name="poison-message-handling"></a>Gestione dei messaggi non elaborabili  
 Per messaggio non elaborabile si intende un messaggio che ha superato il numero massimo di tentativi di recapito all'applicazione ricevente. Questa situazione può verificarsi quando un'applicazione che legge un messaggio da una coda transazionale non può elaborare immediatamente il messaggio a causa di errori. Se l'applicazione interrompe la transazione nella quale è stato ricevuto il messaggio in coda, il messaggio viene restituito alla coda. L'applicazione tenta quindi di recuperare nuovamente il messaggio in una nuova transazione. Se il problema che causa l'interruzione della transazione non viene risolto, l'applicazione ricevente può rimanere bloccata in un ciclo continuo di ricezioni e interruzioni dello stesso messaggio fino a superare il numero massimo di tentativi di recapito. Ne consegue l'impossibilità di elaborare il messaggio.  
  
 Le differenze principali tra il servizio di accodamento messaggi (MSMQ) in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)] che riguardano la gestione di messaggi non elaborabili sono illustrate di seguito:  
  
-   MSMQ in [!INCLUDE[wv](../../../../includes/wv-md.md)] supporta le code secondarie che non sono supportate da [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. Le code secondarie vengono utilizzate nella gestione dei messaggi non elaborabili. Le code di tentativi e la coda non elaborabile sono code secondarie della coda dell'applicazione creata in base alle impostazioni di gestione dei messaggi non elaborabili. `MaxRetryCycles` stabilisce il numero delle code secondarie dei tentativi che verranno create. Di conseguenza, in caso di esecuzione in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], `MaxRetryCycles` viene ignorato e `ReceiveErrorHandling.Move` non è consentito.  
  
-   Il servizio di accodamento messaggi in [!INCLUDE[wv](../../../../includes/wv-md.md)] supporta il negative acknowledgment a differenza di [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. Un negative acknowledgment dal gestore delle code ricevente determina l'inserimento, da parte del gestore delle code mittente, del messaggio respinto nella coda dei messaggi non recapitabili. Per questa ragione, `ReceiveErrorHandling.Reject` non è consentito con [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
-   Il servizio di accodamento messaggi in [!INCLUDE[wv](../../../../includes/wv-md.md)] supporta una proprietà del messaggio che conta il numero di volte che viene tentato il recapito del messaggio. Questa proprietà del numero di interruzioni non è disponibile in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] e [!INCLUDE[wxp](../../../../includes/wxp-md.md)]. WCF gestisce il conteggio delle interruzioni in memoria, pertanto è possibile che questa proprietà non può contenere un valore accurato quando lo stesso messaggio viene letto da più di un servizio WCF in una Web farm.  
  
## <a name="remote-transactional-read"></a>Lettura transazionale in remoto  
 Il servizio di accodamento messaggi in [!INCLUDE[wv](../../../../includes/wv-md.md)] supporta le letture transazionali in remoto. Ciò consente a un'applicazione che sta leggendo da una coda di essere ospitata in un computer che è diverso da quello in cui è ospitata la coda. In questo modo è possibile disporre di una farm di servizi che leggono da una coda centrale, con conseguente aumento della velocità effettiva complessiva del sistema. Inoltre, se si verifica un errore durante la lettura e l'elaborazione del messaggio, viene eseguito il rollback della transazione e il messaggio rimane nella coda per poter essere elaborato in seguito.  
  
## <a name="see-also"></a>Vedere anche
- [Uso di code di messaggi non recapitabili per gestire gli errori di trasferimento dei messaggi](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)
- [Gestione dei messaggi non elaborabili](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
