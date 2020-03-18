---
ms.openlocfilehash: 3bce796191e0ebe6dbe4650457abe5a20c383f02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147562"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="ff77f-101">Firma JsonFactoryConverter.CreateConverter modificata</span><span class="sxs-lookup"><span data-stu-id="ff77f-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="ff77f-102">Per facilitare <xref:System.Text.Json.Serialization.JsonConverterFactory> la composizione <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> delle classi, il metodo è <xref:System.Text.Json.JsonSerializerOptions>stato reso pubblico e fornito un secondo argomento di tipo .</span><span class="sxs-lookup"><span data-stu-id="ff77f-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ff77f-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="ff77f-103">Change description</span></span>

<span data-ttu-id="ff77f-104">La firma `CreateConverter` del metodo in .NET Core prima della versione 3.0 Preview 8 era:</span><span class="sxs-lookup"><span data-stu-id="ff77f-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="ff77f-105">In .NET Core 3.0 Preview 8 e versioni successive, è:In .NET Core 3.0 Preview 8 and later versions, it is:</span><span class="sxs-lookup"><span data-stu-id="ff77f-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="ff77f-106">Prima di questo cambiamento, era difficile comporre convertitori di fabbrica sigillati, dal momento che non c'era un modo semplice per ottenere il <xref:System.Text.Json.Serialization.JsonConverter%601> da esso.</span><span class="sxs-lookup"><span data-stu-id="ff77f-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="ff77f-107">Rendere pubblico il metodo factory <xref:System.Text.Json.JsonSerializerOptions> e anche il passaggio della corrente consentono una composizione molto più flessibile.</span><span class="sxs-lookup"><span data-stu-id="ff77f-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ff77f-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="ff77f-108">Version introduced</span></span>

<span data-ttu-id="ff77f-109">3.0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="ff77f-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ff77f-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="ff77f-110">Recommended action</span></span>

<span data-ttu-id="ff77f-111">Le classi derivate devono essere aggiornate e ricompilate.</span><span class="sxs-lookup"><span data-stu-id="ff77f-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ff77f-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="ff77f-112">Affected APIs</span></span>

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
