---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620344"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a>La deserializzazione di oggetti MailMessage serializzati in .NET Framework 4.5 può non riuscire

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, gli oggetti <xref:System.Web.Mail.MailMessage> possono includere caratteri non ASCII. In .NET Framework 4, sono supportati solo caratteri ASCII. Gli oggetti <xref:System.Web.Mail.MailMessage> che contengono caratteri non ASCII e che vengono serializzati in .NET Framework 4.5 o versione successiva non possono essere deserializzati in .NET Framework 4.

#### <a name="suggestion"></a>Suggerimento

Quando si deserializza un oggetto <xref:System.Web.Mail.MailMessage>, verificare che il codice consenta la gestione delle eccezioni.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
