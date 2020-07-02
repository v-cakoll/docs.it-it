---
ms.openlocfilehash: afdf1e20db7dc564ddfb6028238604f97e00971a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614789"
---
### <a name="serialization-of-control-characters-with-datacontractjsonserializer-is-now-compatible-with-ecmascript-v6-and-v8"></a><span data-ttu-id="6fb9d-101">La serializzazione dei caratteri di controllo con DataContractJsonSerializer è ora compatibile con ECMAScript V6 e V8</span><span class="sxs-lookup"><span data-stu-id="6fb9d-101">Serialization of control characters with DataContractJsonSerializer is now compatible with ECMAScript V6 and V8</span></span>

#### <a name="details"></a><span data-ttu-id="6fb9d-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="6fb9d-102">Details</span></span>

<span data-ttu-id="6fb9d-103">In .NET Framework 4.6.2 e versioni precedenti, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> non serializza alcuni caratteri di controllo speciali, ad esempio \b, \f e \t, in modo compatibile con gli standard ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="6fb9d-103">In .NET Framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> did not serialize some special control characters, such as \b, \f, and \t, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span> <span data-ttu-id="6fb9d-104">A partire da .NET Framework 4,7, la serializzazione di questi caratteri di controllo è compatibile con ECMAScript V6 e V8.</span><span class="sxs-lookup"><span data-stu-id="6fb9d-104">Starting with .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6fb9d-105">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="6fb9d-105">Suggestion</span></span>

<span data-ttu-id="6fb9d-106">Questa funzionalità è abilitata per impostazione predefinita per le app destinate a .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="6fb9d-106">For apps that target the .NET Framework 4.7, this feature is enabled by default.</span></span> <span data-ttu-id="6fb9d-107">Se questo comportamento non è opportuno, è possibile rifiutare esplicitamente questa funzionalità aggiungendo la riga seguente alla sezione `<runtime>` del file app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="6fb9d-107">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```

| <span data-ttu-id="6fb9d-108">Nome</span><span class="sxs-lookup"><span data-stu-id="6fb9d-108">Name</span></span>    | <span data-ttu-id="6fb9d-109">Valore</span><span class="sxs-lookup"><span data-stu-id="6fb9d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6fb9d-110">Scope</span><span class="sxs-lookup"><span data-stu-id="6fb9d-110">Scope</span></span>   | <span data-ttu-id="6fb9d-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6fb9d-111">Edge</span></span>        |
| <span data-ttu-id="6fb9d-112">Version</span><span class="sxs-lookup"><span data-stu-id="6fb9d-112">Version</span></span> | <span data-ttu-id="6fb9d-113">4.7</span><span class="sxs-lookup"><span data-stu-id="6fb9d-113">4.7</span></span>         |
| <span data-ttu-id="6fb9d-114">Type</span><span class="sxs-lookup"><span data-stu-id="6fb9d-114">Type</span></span>    | <span data-ttu-id="6fb9d-115">Ridestinazione</span><span class="sxs-lookup"><span data-stu-id="6fb9d-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6fb9d-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="6fb9d-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlDictionaryWriter,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType>
