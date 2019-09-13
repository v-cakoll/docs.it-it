---
ms.openlocfilehash: e16f0c8ede5e1a24d4fc4606c3c25225ea72e750
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70930061"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="95632-101">Firma di JsonFactoryConverter. CreateConverter modificata</span><span class="sxs-lookup"><span data-stu-id="95632-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="95632-102">Per facilitare la composizione delle <xref:System.Text.Json.Serialization.JsonConverterFactory> classi, il <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> metodo è stato reso pubblico e viene fornito un secondo argomento di <xref:System.Text.Json.JsonSerializerOptions>tipo.</span><span class="sxs-lookup"><span data-stu-id="95632-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="details"></a><span data-ttu-id="95632-103">Dettagli</span><span class="sxs-lookup"><span data-stu-id="95632-103">Details</span></span>

<span data-ttu-id="95632-104">La firma del `CreateConverter` metodo in .NET Core precedente alla versione 3,0 Preview 8 era:</span><span class="sxs-lookup"><span data-stu-id="95632-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span> 

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="95632-105">In .NET Core 3,0 Preview 8 e versioni successive, è:</span><span class="sxs-lookup"><span data-stu-id="95632-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="95632-106">Prima di questa modifica, era difficile comporre convertitori di fabbrica Sealed, dal momento che non esisteva un modo <xref:System.Text.Json.Serialization.JsonConverter%601> semplice per ottenere il.</span><span class="sxs-lookup"><span data-stu-id="95632-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="95632-107">Rendendo pubblico il metodo factory e passando l'oggetto corrente <xref:System.Text.Json.JsonSerializerOptions> , è possibile creare una composizione molto più flessibile.</span><span class="sxs-lookup"><span data-stu-id="95632-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="95632-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="95632-108">Version introduced</span></span>

<span data-ttu-id="95632-109">3,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="95632-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="95632-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="95632-110">Recommended action</span></span>

<span data-ttu-id="95632-111">È necessario aggiornare e ricompilare le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="95632-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="95632-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="95632-112">Affected APIs</span></span>

<span data-ttu-id="95632-113">[https://login.microsoftonline.com/consumers/](<xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="95632-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span></span>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
