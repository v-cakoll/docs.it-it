---
title: Traccia attività relative alla protezione dei messaggi
ms.date: 03/30/2017
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
ms.openlocfilehash: bb8a4c6782cc52de393eacc2458e216d0f069866
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933520"
---
# <a name="activity-tracing-in-message-security"></a>Traccia attività relative alla protezione dei messaggi
Questo argomento descrive la traccia attività per l'elaborazione delle operazioni di sicurezza, che si articola nelle tre fasi seguenti.  
  
- Scambio negoziazione/SCT: questa fase può verificarsi a livello di trasporto (tramite lo scambio di dati binari) o a livello di messaggio (tramite lo scambio di messaggi SOAP).  
  
- Crittografia/decrittografia dei messaggi (con verifica della firma e autenticazione): le tracce vengono riportate nell'attività di ambiente, che in genere è l'attività ProcessAction.  
  
- Autorizzazione e verifica: questa fase può verificarsi localmente oppure durante la comunicazione tra endpoint.  
  
## <a name="negotiationsct-exchange"></a>Scambio negoziazione/SCT  
 Nella fase di scambio negoziazione/SCT vengono creati due tipi di attività nel client: "Configura sessione protetta" e "Chiudi sessione protetta". La prima attività contiene le tracce relative agli scambi di messaggi RST/RSTR/SCT mentre la seconda contiene le tracce relative al messaggio di annullamento.  
  
 Nel server, ogni request/reply degli scambi RST/RSTR/SCT viene visualizzato nella propria attività. Se `propagateActivity` sianelserver`true` che nel client, le attività nel server hanno lo stesso ID e vengono visualizzate insieme nell'"installazione della sessione protetta" quando vengono visualizzate tramite il Visualizzatore di tracce dei servizi. =  
  
 Questo modello di traccia attività è valido per le autenticazioni basate su nome/password, certificato o NTLM.  
  
 Nella tabella seguente sono elencate le attività e le tracce relative allo scambio negoziazione/SCT.  
  
||Contesto in cui si verifica lo scambio negoziazione/SCT|Attività|Tracce|  
|-|-------------------------------------------------|----------------|------------|  
|Protezione a livello di trasporto<br /><br /> (HTTPS, SSL)|Alla ricezione del primo messaggio.|Le tracce vengono generate nell'attività di ambiente.|-Tracce di Exchange<br />-Stabilito canale sicuro<br />-Condividere i segreti ottenuti.|  
|Protezione a livello di messaggio<br /><br /> (WSHTTP)|Alla ricezione del primo messaggio.|Nel client:<br /><br /> -"Configurare la sessione protetta" fuori dall'azione di elaborazione del primo messaggio, per ogni Request/Reply per RST/RSTR/SCT.<br />-"Chiudi la sessione protetta" per lo scambio di annullamento, dall'attività di chiusura del proxy. Questa attività può essere causata da un'altra attività di ambiente, a seconda del momento di chiusura della sessione protetta.<br /><br /> Nel server:<br /><br /> -Un'attività "Elaborazione azione" per ogni richiesta/risposta per RST/SCT/Annulla nel server. Se `propagateActivity` ,leattività`true`RST/RSTR/SCT vengono unite con "Configura sessione di sicurezza" e Annulla viene unita all'attività di chiusura dal client. =<br /><br /> L'attività di impostazione della sessione di sicurezza si articola in due fasi:<br /><br /> 1.  Negoziazione dell'autenticazione: questa fase è facoltativa se il client già dispone delle credenziali corrette. Questa fase può essere eseguita tramite un trasporto protetto o lo scambio di messaggi. Nel secondo caso è possibile che si verifichino 1 o 2 scambi RST/RSTR. Per questi scambi il sistema genera tracce in nuove attività di request/reply, come descritto in precedenza.<br />2.  Creazione di una sessione protetta: in tale fase si verifica un unico scambio RST/RSTR avente le stesse attività di ambiente descritte in precedenza.|-Tracce di Exchange<br />-Stabilito canale sicuro<br />-Condividere i segreti ottenuti.|  
  
> [!NOTE]
> In modalità di sicurezza mista, l'autenticazione di negoziazione si verifica in scambi binari. Tuttavia, lo scambio SCT si verifica tramite lo scambio di messaggi. Nella modalità di trasporto pure, la negoziazione si verifica solo nel trasporto senza alcuna attività aggiuntiva.  
  
## <a name="message-encryption-and-decryption"></a>Crittografia e decrittografia dei messaggi  
 Nella tabella seguente sono elencate le attività e le tracce relative alla crittografia/decrittografia dei messaggi, nonché all'autenticazione della firma.  
  
||Protezione a livello di trasporto<br /><br /> (HTTPS, SSL) e del livello di messaggio<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|Momento in cui si verificano la crittografia/decrittografia dei messaggi e l'autenticazione della firma|Alla ricezione del messaggio|  
|Attività|Le tracce vengono generate nell'attività ProcessAction nel client e nel server.|  
|Tracce|-sendSecurityHeader (mittente):<br />-Messaggio di firma<br />-Crittografa dati richiesta<br />-receiveSecurityHeader (ricevitore):<br />-Verifica firma<br />-Decrittografare i dati di risposta<br />-Autenticazione|  
  
> [!NOTE]
> Nella modalità di trasporto pure, la crittografia/decrittografia dei messaggi si verifica solo nel trasporto senza alcuna attività aggiuntiva.  
  
## <a name="authorization-and-verification"></a>Autorizzazione e verifica  
 Nella tabella seguente sono elencate le attività e le tracce relative all'autorizzazione.  
  
||Momento in cui si verifica l'autorizzazione|Attività|Tracce|  
|-|-------------------------------------|----------------|------------|  
|Locale (impostazione predefinita)|Dopo che il messaggio è stato decrittografato nel server|Le tracce vengono generate nell'attività ProcessAction nel server.|Autorizzazione dell'utente.|  
|Remote|Dopo che il messaggio è stato decrittografato nel server|Le tracce vengono generate in una nuova attività richiamata dall'attività ProcessAction.|Autorizzazione dell'utente.|
