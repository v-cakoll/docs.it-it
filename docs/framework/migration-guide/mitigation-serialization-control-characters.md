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
ms.openlocfilehash: 0a00edbf2d5833349de14986f2a57a2c943f3ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33388433"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="d8a65-102">Mitigazione: Serializzazione dei caratteri di controllo con DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="d8a65-102">Mitigation: Serialization of Control Characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="d8a65-103">A partire da .NET Framework 4.7 è stato modificato il modo in cui i caratteri di controllo vengono serializzati con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, in modo da renderli conformi a ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="d8a65-103">Starting with the .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="d8a65-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="d8a65-104">Impact</span></span>

<span data-ttu-id="d8a65-105">In .NET framework 4.6.2 e versioni precedenti, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non serializza alcuni caratteri di controllo speciali, ad esempio `\b`, `\f` e `\t`, in modo compatibile con gli standard ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="d8a65-105">In the .NET framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="d8a65-106">Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="d8a65-106">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="d8a65-107">Sono interessate le seguenti API:</span><span class="sxs-lookup"><span data-stu-id="d8a65-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="d8a65-108">Mitigazione</span><span class="sxs-lookup"><span data-stu-id="d8a65-108">Mitigation</span></span>

<span data-ttu-id="d8a65-109">Per le applicazioni destinate a versioni di .NET Framework a partire dalla 4.7, questo comportamento è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d8a65-109">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="d8a65-110">Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="d8a65-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="d8a65-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8a65-111">See also</span></span>
[<span data-ttu-id="d8a65-112">Retargeting Changes in the .NET Framework 4.7 (Reindirizzamento delle modifiche in .NET Framework 4.7)</span><span class="sxs-lookup"><span data-stu-id="d8a65-112">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
