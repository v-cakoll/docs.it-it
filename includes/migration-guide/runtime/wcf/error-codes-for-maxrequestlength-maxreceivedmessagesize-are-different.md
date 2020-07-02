---
ms.openlocfilehash: 3aafb14b65f7c0f9e5d77927809547f9d4b96e1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620371"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>I codici di errore per maxRequestLength o maxReceivedMessageSize sono diversi

#### <a name="details"></a>Dettagli

I messaggi nei servizi Web WCF ospitati in Internet Information Services (IIS) o ASP.NET Development Server che superano maxRequestLength (in ASP.NET) o maxReceivedMessageSize (in WCF) hanno un codice di errore diverso. Il codice di stato HTTP è cambiato da 400 (Richiesta non valida) a 413 (Entità troppo grande) e i messaggi che superano la soglia impostata da maxRequestLength o da maxReceivedMessageSize generano un'eccezione <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>. Sono inclusi i casi in cui la modalità di trasferimento è Streamed.

#### <a name="suggestion"></a>Suggerimento

Questa modifica semplifica il debug nei casi in cui la lunghezza del messaggio supera i limiti consentiti da ASP.NET o WCF. È necessario modificare qualsiasi codice che esegue l'elaborazione in base a un codice di stato HTTP 400.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime|
