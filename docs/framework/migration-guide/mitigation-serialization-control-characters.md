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
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="a655f-102">Mitigazione: serializzazione dei caratteri di controllo con DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="a655f-102">Mitigation: Serialization of control characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="a655f-103">A partire da .NET Framework 4,7, il modo in cui i caratteri di controllo vengono serializzati con la <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> è stato modificato per essere conforme a ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="a655f-103">Starting with .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="a655f-104">Impatto</span><span class="sxs-lookup"><span data-stu-id="a655f-104">Impact</span></span>

<span data-ttu-id="a655f-105">In .NET Framework 4.6.2 e versioni precedenti, il <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non ha serializzato alcuni caratteri di controllo speciali, ad esempio `\b`, `\f`e `\t`, in modo compatibile con gli standard ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="a655f-105">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="a655f-106">Per le app destinate a versioni di .NET Framework a partire da .NET Framework 4,7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="a655f-106">For apps that target versions of .NET Framework starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="a655f-107">Sono interessate le seguenti API:</span><span class="sxs-lookup"><span data-stu-id="a655f-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a><span data-ttu-id="a655f-108">Attenuazione</span><span class="sxs-lookup"><span data-stu-id="a655f-108">Mitigation</span></span>

<span data-ttu-id="a655f-109">Per le app destinate a versioni di .NET Framework che iniziano con .NET Framework 4,7, questo comportamento è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a655f-109">For apps that target versions of .NET Framework starting with .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="a655f-110">Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="a655f-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="a655f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a655f-111">See also</span></span>

- [<span data-ttu-id="a655f-112">Compatibilità delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="a655f-112">Application compatibility</span></span>](application-compatibility.md)
