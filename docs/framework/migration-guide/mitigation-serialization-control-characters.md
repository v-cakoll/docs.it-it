---
title: Serializzazione di caratteri di controllo con DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: 209f7827e61ef72de1d64fad46dc9f241fa6edef
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346578"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Mitigazione: serializzazione dei caratteri di controllo con DataContractJsonSerializer

A partire da .NET Framework 4.7 è stato modificato il modo in cui i caratteri di controllo vengono serializzati con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, in modo da renderli conformi a ECMAScript V6 e V8. 
 
## <a name="impact"></a>Impatto

In .NET framework 4.6.2 e versioni precedenti, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non serializza alcuni caratteri di controllo speciali, ad esempio `\b`, `\f` e `\t`, in modo compatibile con gli standard ECMAScript V6 e V8.

Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8. Sono interessate le seguenti API:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a>Mitigazione

Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7, questo comportamento è abilitato per impostazione predefinita.

Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>Vedere anche

- [Compatibilità dell'applicazione](application-compatibility.md)
