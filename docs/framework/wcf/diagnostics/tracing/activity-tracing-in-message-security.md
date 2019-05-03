---
title: Traccia attività relative alla protezione dei messaggi
ms.date: 03/30/2017
ms.assetid: 68862534-3b2e-4270-b097-8121b12a2c97
ms.openlocfilehash: c3bd36598fd903dc016959149e563174624d084b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912652"
---
# <a name="activity-tracing-in-message-security"></a>Traccia attività relative alla protezione dei messaggi
Questo argomento descrive la traccia attività per l'elaborazione delle operazioni di sicurezza, che si articola nelle tre fasi seguenti.  
  
- Scambio negoziazione/SCT: questa fase può verificarsi a livello di trasporto (tramite lo scambio di dati binari) o a livello di messaggio (tramite lo scambio di messaggi SOAP).  
  
- Crittografia/decrittografia dei messaggi (con verifica della firma e autenticazione): le tracce vengono riportate nell'attività di ambiente, che in genere è l'attività ProcessAction.  
  
- Autorizzazione e verifica: questa fase può verificarsi localmente oppure durante la comunicazione tra endpoint.  
  
## <a name="negotiationsct-exchange"></a>Scambio negoziazione/SCT  
 In fase di scambio negoziazione/SCT vengono creati due tipi di attività sul client: "Configurata della sessione di sicurezza" e "chiude" della sessione protetta. La prima attività contiene le tracce relative agli scambi di messaggi RST/RSTR/SCT mentre la seconda contiene le tracce relative al messaggio di annullamento.  
  
 Nel server, ogni request/reply degli scambi RST/RSTR/SCT viene visualizzato nella propria attività. Se `propagateActivity` = `true` nel server sia client, hanno lo stesso ID attività nel server e abbinati nella "Configurazione sessione di sicurezza" quando viene visualizzato in Service Trace Viewer.  
  
 Questo modello di traccia attività è valido per le autenticazioni basate su nome/password, certificato o NTLM.  
  
 Nella tabella seguente sono elencate le attività e le tracce relative allo scambio negoziazione/SCT.  
  
||Contesto in cui si verifica lo scambio negoziazione/SCT|Attività|Tracce|  
|-|-------------------------------------------------|----------------|------------|  
|Protezione a livello di trasporto<br /><br /> (HTTPS, SSL)|Alla ricezione del primo messaggio.|Le tracce vengono generate nell'attività di ambiente.|-Le tracce Exchange<br />-Canale sicuro stabilito<br />-Condivisione ottenuti dei segreti.|  
|Protezione a livello di messaggio<br /><br /> (WSHTTP)|Alla ricezione del primo messaggio.|Nel client:<br /><br /> -"Il programma di installazione sessione protetta" da "Processaction" di questo primo messaggio, per ogni request/reply degli scambi RST/RSTR/SCT.<br />-"Chiusura della sessione protetta" per lo scambio di annullamento, le "attività della chiusura del Proxy". Questa attività può essere causata da un'altra attività di ambiente, a seconda del momento di chiusura della sessione protetta.<br /><br /> Nel server:<br /><br /> -Un'attività "Processaction" per ogni request/reply per RST/SCT/Cancel nel server. Se `propagateActivity` = `true`attività RST/RSTR/SCT vengono unite con "Impostazione della sessione di sicurezza" e annullamento viene unita con l'attività "Chiudere" dal client.<br /><br /> L'attività di impostazione della sessione di sicurezza si articola in due fasi:<br /><br /> 1.  Negoziazione dell'autenticazione: questa fase è facoltativa se il client già dispone delle credenziali corrette. Questa fase può essere eseguita tramite un trasporto protetto o lo scambio di messaggi. Nel secondo caso è possibile che si verifichino 1 o 2 scambi RST/RSTR. Per questi scambi il sistema genera tracce in nuove attività di request/reply, come descritto in precedenza.<br />2.  Creazione di una sessione protetta: in tale fase si verifica un unico scambio RST/RSTR avente le stesse attività di ambiente descritte in precedenza.|-Le tracce Exchange<br />-Canale sicuro stabilito<br />-Condivisione ottenuti dei segreti.|  
  
> [!NOTE]
>  In modalità di sicurezza mista, l'autenticazione di negoziazione si verifica in scambi binari. Tuttavia, lo scambio SCT si verifica tramite lo scambio di messaggi. Nella modalità di trasporto pure, la negoziazione si verifica solo nel trasporto senza alcuna attività aggiuntiva.  
  
## <a name="message-encryption-and-decryption"></a>Crittografia e decrittografia dei messaggi  
 Nella tabella seguente sono elencate le attività e le tracce relative alla crittografia/decrittografia dei messaggi, nonché all'autenticazione della firma.  
  
||Protezione a livello di trasporto<br /><br /> (HTTPS, SSL) e del livello di messaggio<br /><br /> (WSHTTP)|  
|-|---------------------------------------------------------------------------------|  
|Momento in cui si verificano la crittografia/decrittografia dei messaggi e l'autenticazione della firma|Alla ricezione del messaggio|  
|Attività|Le tracce vengono generate nell'attività ProcessAction nel client e nel server.|  
|Tracce|-sendSecurityHeader (mittente):<br />-Firma messaggio<br />-Crittografare i dati della richiesta<br />-receiveSecurityHeader (destinatario):<br />-Verificare la firma<br />-Decrittografare i dati di risposta<br />-Autenticazione|  
  
> [!NOTE]
>  Nella modalità di trasporto pure, la crittografia/decrittografia dei messaggi si verifica solo nel trasporto senza alcuna attività aggiuntiva.  
  
## <a name="authorization-and-verification"></a>Autorizzazione e verifica  
 Nella tabella seguente sono elencate le attività e le tracce relative all'autorizzazione.  
  
||Momento in cui si verifica l'autorizzazione|Attività|Tracce|  
|-|-------------------------------------|----------------|------------|  
|Locale (impostazione predefinita)|Dopo che il messaggio è stato decrittografato nel server|Le tracce vengono generate nell'attività ProcessAction nel server.|Autorizzazione dell'utente.|  
|Remote|Dopo che il messaggio è stato decrittografato nel server|Le tracce vengono generate in una nuova attività richiamata dall'attività ProcessAction.|Autorizzazione dell'utente.|
