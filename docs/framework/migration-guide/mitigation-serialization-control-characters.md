---
title: Serializzazione di caratteri di controllo con DataContractJsonSerializer
description: Informazioni sul modo in cui la serializzazione dei caratteri di controllo è cambiata per essere conforme a ECMAScript V6 e V8 in .NET Framework 4,7.
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: a317884da014097a7a60aef2cef4ec146ccb04f7
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475385"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="65668-103">Mitigazione: serializzazione dei caratteri di controllo con DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="65668-103">Mitigation: Serialization of control characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="65668-104">A partire da .NET Framework 4,7, il modo in cui i caratteri di controllo vengono serializzati con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> è stato modificato per essere conforme a ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="65668-104">Starting with .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span>

## <a name="impact"></a><span data-ttu-id="65668-105">Impatto</span><span class="sxs-lookup"><span data-stu-id="65668-105">Impact</span></span>

<span data-ttu-id="65668-106">In .NET Framework 4.6.2 e nelle versioni precedenti, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> non serializza alcuni caratteri di controllo speciali, ad esempio `\b` , `\f` e `\t` , in modo compatibile con gli standard ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="65668-106">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="65668-107">Per le app destinate a versioni di .NET Framework a partire da .NET Framework 4,7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="65668-107">For apps that target versions of .NET Framework starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="65668-108">Sono interessate le seguenti API:</span><span class="sxs-lookup"><span data-stu-id="65668-108">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="65668-109">Strategia di riduzione del rischio</span><span class="sxs-lookup"><span data-stu-id="65668-109">Mitigation</span></span>

<span data-ttu-id="65668-110">Per le app destinate a versioni di .NET Framework che iniziano con .NET Framework 4,7, questo comportamento è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="65668-110">For apps that target versions of .NET Framework starting with .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="65668-111">Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="65668-111">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="65668-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65668-112">See also</span></span>

- [<span data-ttu-id="65668-113">Compatibilità tra le versioni</span><span class="sxs-lookup"><span data-stu-id="65668-113">Application compatibility</span></span>](application-compatibility.md)
