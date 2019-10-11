---
ms.openlocfilehash: f5b0064f9f01923c6353fd8e2b274bd7407ccbd8
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237383"
---
### <a name="jsonfactoryconvertercreateconverter-signature-changed"></a><span data-ttu-id="66443-101">Firma di JsonFactoryConverter. CreateConverter modificata</span><span class="sxs-lookup"><span data-stu-id="66443-101">JsonFactoryConverter.CreateConverter signature changed</span></span>

<span data-ttu-id="66443-102">Per semplificare la composizione di classi <xref:System.Text.Json.Serialization.JsonConverterFactory>, il metodo <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> è stato reso pubblico e dato un secondo argomento di tipo <xref:System.Text.Json.JsonSerializerOptions>.</span><span class="sxs-lookup"><span data-stu-id="66443-102">To facilitate the composition of <xref:System.Text.Json.Serialization.JsonConverterFactory> classes, the <xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter%2A> method has been made public and given a second argument of type <xref:System.Text.Json.JsonSerializerOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="66443-103">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="66443-103">Change description</span></span>

<span data-ttu-id="66443-104">La firma del metodo `CreateConverter` in .NET Core prima della versione 3,0 Preview 8 era:</span><span class="sxs-lookup"><span data-stu-id="66443-104">The signature of the `CreateConverter` method in .NET Core prior to version 3.0 Preview 8 was:</span></span> 

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        protected abstract JsonConverter CreateConverter(Type typeToConvert);
    }
}
```

<span data-ttu-id="66443-105">In .NET Core 3,0 Preview 8 e versioni successive, è:</span><span class="sxs-lookup"><span data-stu-id="66443-105">In .NET Core 3.0 Preview 8 and later versions, it is:</span></span>

```csharp
namespace System.Text.Json.Serialization
{
    public abstract class JsonConverterFactory : JsonConverter
    {
        public abstract JsonConverter CreateConverter(Type typeToConvert, JsonSerializerOptions options);
    }
}
```

<span data-ttu-id="66443-106">Prima di questa modifica, era difficile comporre convertitori di fabbrica Sealed, dal momento che non esisteva un modo semplice per ottenere il <xref:System.Text.Json.Serialization.JsonConverter%601>.</span><span class="sxs-lookup"><span data-stu-id="66443-106">Before this change, it was difficult to compose sealed factory converters, since there was no easy way to get the <xref:System.Text.Json.Serialization.JsonConverter%601> from it.</span></span> <span data-ttu-id="66443-107">Rendere pubblico il metodo factory e passare anche il @no__t corrente-0 consente una composizione molto più flessibile.</span><span class="sxs-lookup"><span data-stu-id="66443-107">Making the factory method public and also passing the current <xref:System.Text.Json.JsonSerializerOptions> allow for much more flexible composition.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="66443-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="66443-108">Version introduced</span></span>

<span data-ttu-id="66443-109">3,0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="66443-109">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="66443-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="66443-110">Recommended action</span></span>

<span data-ttu-id="66443-111">È necessario aggiornare e ricompilare le classi derivate.</span><span class="sxs-lookup"><span data-stu-id="66443-111">Derived classes need to be updated and recompiled.</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="66443-112">API interessate</span><span class="sxs-lookup"><span data-stu-id="66443-112">Affected APIs</span></span>

<span data-ttu-id="66443-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> (Indici per tabelle con ottimizzazione per la memoria).</span><span class="sxs-lookup"><span data-stu-id="66443-113"><xref:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>.</span></span>

<!-- For tool use only

### Affected APIs

- `M:System.Text.Json.Serialization.JsonConverterFactory.CreateConverter(System.Type,System.Text.Json.JsonSerializerOptions)`

-->
