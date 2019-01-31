---
title: 'Mitigazione: Serializzazione dei caratteri di controllo con DataContractJsonSerializer'
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31f946fa01f3d6334011098d12483445159ce54a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738118"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Mitigazione: Serializzazione dei caratteri di controllo con DataContractJsonSerializer

A partire da .NET Framework 4.7 è stato modificato il modo in cui i caratteri di controllo vengono serializzati con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, in modo da renderli conformi a ECMAScript V6 e V8. 
 
## <a name="impact"></a>Impatto

In .NET framework 4.6.2 e versioni precedenti, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non serializza alcuni caratteri di controllo speciali, ad esempio `\b`, `\f` e `\t`, in modo compatibile con gli standard ECMAScript V6 e V8.

Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8. Sono interessate le seguenti API:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
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
- [Retargeting Changes in the .NET Framework 4.7 (Reindirizzamento delle modifiche in .NET Framework 4.7)](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
