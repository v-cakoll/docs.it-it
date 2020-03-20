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
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="04498-102">Mitigazione: serializzazione dei caratteri di controllo con DataContractJsonSerializerMitigation: Serialization of control characters with the DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="04498-102">Mitigation: Serialization of control characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="04498-103">A partire da .NET Framework 4.7. <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer></span><span class="sxs-lookup"><span data-stu-id="04498-103">Starting with .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span>

## <a name="impact"></a><span data-ttu-id="04498-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="04498-104">Impact</span></span>

<span data-ttu-id="04498-105">In .NET Framework 4.6.2 e <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> versioni precedenti, non venivano `\b` `\f`serializzati `\t`alcuni caratteri di controllo speciali, ad esempio , e , in modo compatibile con gli standard ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="04498-105">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="04498-106">Per le app destinate a versioni di .NET Framework a partire da .NET Framework 4.7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="04498-106">For apps that target versions of .NET Framework starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="04498-107">Sono interessate le seguenti API:</span><span class="sxs-lookup"><span data-stu-id="04498-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="04498-108">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="04498-108">Mitigation</span></span>

<span data-ttu-id="04498-109">Per le app destinate a versioni di .NET Framework a partire da .NET Framework 4.7, questo comportamento è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="04498-109">For apps that target versions of .NET Framework starting with .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="04498-110">Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="04498-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="04498-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04498-111">See also</span></span>

- [<span data-ttu-id="04498-112">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="04498-112">Application compatibility</span></span>](application-compatibility.md)
