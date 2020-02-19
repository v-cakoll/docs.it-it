---
title: Serializzazione di caratteri di controllo con DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: b6468bc4ae37765d969a1f92b16967cc656ab7ff
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452630"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Mitigazione: serializzazione dei caratteri di controllo con DataContractJsonSerializer

A partire da .NET Framework 4,7, il modo in cui i caratteri di controllo vengono serializzati con la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> è stato modificato per essere conforme a ECMAScript V6 e V8. 
 
## <a name="impact"></a>Impatto

In .NET Framework 4.6.2 e versioni precedenti, il <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non ha serializzato alcuni caratteri di controllo speciali, ad esempio `\b`, `\f`e `\t`, in modo compatibile con gli standard ECMAScript V6 e V8.

Per le app destinate a versioni di .NET Framework a partire da .NET Framework 4,7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8. Sono interessate le seguenti API:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a>Attenuazione

Per le app destinate a versioni di .NET Framework che iniziano con .NET Framework 4,7, questo comportamento è abilitato per impostazione predefinita.

Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>Vedere anche

- [Compatibilità delle applicazioni](application-compatibility.md)
