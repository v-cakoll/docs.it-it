---
ms.openlocfilehash: 43da6233b70927e7320874772976b9e93a0bd69f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721726"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="42e97-101">Firma di JsonFactoryConverter. CreateConverter modificata</span><span class="sxs-lookup"><span data-stu-id="42e97-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="42e97-102">Per facilitare la composizione delle <xref:System.Text.Json.Serialization.JsonConverterFactory> classi, il <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> metodo è stato reso pubblico e viene fornito un secondo argomento di tipo <xref:System.Text.Json.JsonSerializerOptions> .</span><span class="sxs-lookup"><span data-stu-id="42e97-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="42e97-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="42e97-103">Change description</span></span>

<span data-ttu-id="42e97-104">La firma del `CreateConverter` metodo in .NET Core precedente alla versione 3,0 Preview 8 era:</span><span class="sxs-lookup"><span data-stu-id="42e97-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="42e97-105">In .NET Core 3,0 Preview 8 e versioni successive, è:</span><span class="sxs-lookup"><span data-stu-id="42e97-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="42e97-106">Prima di questa modifica, era difficile comporre convertitori di fabbrica Sealed, dal momento che non esisteva un modo semplice per ottenere il <xref:System.Text.Json.Serialization.JsonConverter%601> .</span><span class="sxs-lookup"><span data-stu-id="42e97-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="42e97-107">Rendendo pubblico il metodo factory e passando l'oggetto corrente, <xref:System.Text.Json.JsonSerializerOptions> è possibile creare una composizione molto più flessibile.</span><span class="sxs-lookup"><span data-stu-id="42e97-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="42e97-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="42e97-108">Version introduced</span></span>

<span data-ttu-id="42e97-109">3,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="42e97-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="42e97-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="42e97-110">Recommended action</span></span>

<span data-ttu-id="42e97-111">È necessario aggiornare e ricompilare le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="42e97-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="42e97-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="42e97-112">Affected APIs</span></span>

- <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>

<!-- For tool use only

#### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
