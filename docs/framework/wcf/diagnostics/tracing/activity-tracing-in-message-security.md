---
title: "Traccia attività relative alla protezione dei messaggi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 60156e284c55d765de417fe891185d1aba720816
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="activity-tracing-in-message-security"></a>Traccia attività relative alla protezione dei messaggi
Questo argomento descrive la traccia attività per l'elaborazione delle operazioni di sicurezza, che si articola nelle tre fasi seguenti.  
  
-   Scambio negoziazione/SCT: questa fase può verificarsi a livello di trasporto (tramite lo scambio di dati binari) o a livello di messaggio (tramite lo scambio di messaggi SOAP).  
  
-   Crittografia/decrittografia dei messaggi (con verifica della firma e autenticazione): le tracce vengono riportate nell'attività di ambiente, che in genere è l'attività ProcessAction.  
  
-   Autorizzazione e verifica: questa fase può verificarsi localmente oppure durante la comunicazione tra endpoint.  
  
## <a name="negotiationsct-exchange"></a>Scambio negoziazione/SCT  
 La fase di scambio negoziazione/SCT prevede la creazione di due tipi di attività nel client: l'impostazione della sessione di sicurezza e la chiusura della sessione protetta. La prima attività contiene le tracce relative agli scambi di messaggi RST/RSTR/SCT mentre la seconda contiene le tracce relative al messaggio di annullamento.  
  
 Nel server, ogni request/reply degli scambi RST/RSTR/SCT viene visualizzato nella propria attività. Se `propagateActivity` = `true` server sia nel client, hanno lo stesso ID attività del server e vengono incluse nella "impostazione sessione di sicurezza" quando viene visualizzato tramite Service Trace Viewer.  
  
 Questo modello di traccia attività è valido per le autenticazioni basate su nome/password, certificato o NTLM.  
  
 Nella tabella seguente sono elencate le attività e le tracce relative allo scambio negoziazione/SCT.  
  
||Contesto in cui si verifica lo scambio negoziazione/SCT|Activities|Tracce|  
|-|-------------------------------------------------|----------------|------------|  
|Protezione a livello di trasporto<br /><br /> (HTTPS, SSL)|Alla ricezione del primo messaggio.|Le tracce vengono generate nell'attività di ambiente.|-Scambio di tracce<br />-Canale sicuro stabilito<br />-Condividere l'ottenimento dei segreti.|  
|Protezione a livello di messaggio<br /><br /> (WSHTTP)|Alla ricezione del primo messaggio.|Nel client:<br /><br /> -"Il programma di installazione sessione protetta" da "Elaborazione azione" di questo primo messaggio per ogni request/reply degli scambi RST/RSTR/SCT.<br />-"Chiudi sessione protetta" per lo scambio di annullamento, all'esterno di "attività di chiusura del Proxy." Questa attività può essere causata da un'altra attività di ambiente, a seconda del momento di chiusura della sessione protetta.<br /><br /> Nel server:<br /><br /> -L'attività "Elaborazione azione" uno per ogni request/reply degli scambi RST/SCT/Cancel nel server. Se `propagateActivity` = `true`, le attività RST/RSTR/SCT vengono unite con "Set della sessione di sicurezza" e l'annullamento viene unita con l'attività "Chiudere" dal client.<br /><br /> L'attività di impostazione della sessione di sicurezza si articola in due fasi:<br /><br /> 1.  Negoziazione dell'autenticazione: questa fase è facoltativa se il client già dispone delle credenziali corrette. Questa fase può essere eseguita tramite un trasporto protetto o lo scambio di messaggi. Nel secondo caso è possibile che si verifichino 1 o 2 scambi RST/RSTR. Per questi scambi il sistema genera tracce in nuove attività di request/reply, come descritto in precedenza.<br />2.  Creazione di una sessione protetta: in tale fase si verifica un unico scambio RST/RSTR avente le stesse attività di ambiente descritte in precedenza.|-Scambio di tracce<br />-Canale sicuro stabilito<br />-Condividere l'ottenimento dei segreti.|  
  
> [!NOTE]
>  In modalità di sicurezza mista, l'autenticazione di negoziazione si verifica in scambi binari. Tuttavia, lo scambio SCT si verifica tramite lo scambio di messaggi. Nella modalità di trasporto pure, la negoziazione si verifica solo nel trasporto senza alcuna attività aggiuntiva.  
  
## <a name="message-encryption-and-decryption"></a>Crittografia e decrittografia dei messaggi  
 Nella tabella seguente sono elencate le attività e le tracce relative alla crittografia/decrittografia dei messaggi, nonché all'autenticazione della firma.  
  
||Protezione a livello di trasporto<br /><br /> (HTTPS, SSL) e del livello di messaggio<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|Momento in cui si verificano la crittografia/decrittografia dei messaggi e l'autenticazione della firma|Alla ricezione del messaggio|  
|Activities|Le tracce vengono generate nell'attività ProcessAction nel client e nel server.|  
|Tracce|-sendSecurityHeader (mittente):<br />-Firma messaggio<br />-Crittografare i dati di richiesta<br />-receiveSecurityHeader (destinatario):<br />-Verificare la firma<br />-Decrittografare i dati di risposta<br />-Autenticazione|  
  
> [!NOTE]
>  Nella modalità di trasporto pure, la crittografia/decrittografia dei messaggi si verifica solo nel trasporto senza alcuna attività aggiuntiva.  
  
## <a name="authorization-and-verification"></a>Autorizzazione e verifica  
 Nella tabella seguente sono elencate le attività e le tracce relative all'autorizzazione.  
  
||Momento in cui si verifica l'autorizzazione|Activities|Tracce|  
|-|-------------------------------------|----------------|------------|  
|Locale (impostazione predefinita)|Dopo che il messaggio è stato decrittografato nel server|Le tracce vengono generate nell'attività ProcessAction nel server.|Autorizzazione dell'utente.|  
|Remote|Dopo che il messaggio è stato decrittografato nel server|Le tracce vengono generate in una nuova attività richiamata dall'attività ProcessAction.|Autorizzazione dell'utente.|
