---
title: Serializzazione dei caratteri di controllo con DataContractJsonSerializerSerialization of control characters with DataContractJsonSerializer
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: b60b78f9ee944552fafbe75754ecd29d60dd4093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181205"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Mitigazione: serializzazione dei caratteri di controllo con DataContractJsonSerializerMitigation: Serialization of control characters with the DataContractJsonSerializer

A partire da .NET Framework 4.7. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>

## <a name="impact"></a>Impatto

In .NET Framework 4.6.2 e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> versioni precedenti, non venivano `\b` `\f`serializzati `\t`alcuni caratteri di controllo speciali, ad esempio , e , in modo compatibile con gli standard ECMAScript V6 e V8.

Per le app destinate a versioni di .NET Framework a partire da .NET Framework 4.7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8. Sono interessate le seguenti API:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a>Strategia di riduzione del rischio

Per le app destinate a versioni di .NET Framework a partire da .NET Framework 4.7, questo comportamento è abilitato per impostazione predefinita.

Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

## <a name="see-also"></a>Vedere anche

- [Compatibilità tra le versioni](application-compatibility.md)
