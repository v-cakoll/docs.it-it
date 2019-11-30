---
ms.openlocfilehash: e6e10b2ec451c07bf397cbdcac51ef57c29dab47
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568160"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="f55ea-101">Il tipo di eccezione del serializzatore JSON è stato modificato da `JsonException` a `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="f55ea-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="f55ea-102">In .NET Core 3,0 Preview da 6 a 8, il serializzatore genera un'<xref:System.Text.Json.JsonException> quando si verifica un tipo di raccolta derivato non supportato.</span><span class="sxs-lookup"><span data-stu-id="f55ea-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="f55ea-103">A partire da .NET Core 3,0 Preview 9, il serializzatore genera invece un <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="f55ea-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f55ea-104">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="f55ea-104">Change description</span></span>

<span data-ttu-id="f55ea-105">In .NET Core 3,0 Preview 6 fino all'anteprima 8, il serializzatore genera un'<xref:System.Text.Json.JsonException> quando si verifica un tipo di raccolta derivato non supportato.</span><span class="sxs-lookup"><span data-stu-id="f55ea-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="f55ea-106">Un *tipo di raccolta derivato non supportato* è un tipo di raccolta non assegnabile a uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f55ea-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="f55ea-107">IDictionary\<stringa, T ></span><span class="sxs-lookup"><span data-stu-id="f55ea-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="f55ea-108">A partire da .NET Core 3,0 Preview 9, il serializzatore genera un'<xref:System.NotSupportedException> quando incontra un tipo di raccolta non supportato.</span><span class="sxs-lookup"><span data-stu-id="f55ea-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="f55ea-109">Il nuovo tipo di eccezione riflette meglio il motivo per cui l'operazione di deserializzazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f55ea-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f55ea-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f55ea-110">Version introduced</span></span>

<span data-ttu-id="f55ea-111">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="f55ea-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f55ea-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f55ea-112">Recommended action</span></span>

<span data-ttu-id="f55ea-113">Se si stanno intercettando <xref:System.Text.Json.JsonException> durante la deserializzazione, potrebbe essere opportuno prendere in considerazione anche <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="f55ea-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="f55ea-114">Category</span><span class="sxs-lookup"><span data-stu-id="f55ea-114">Category</span></span>

<span data-ttu-id="f55ea-115">CoreFx</span><span class="sxs-lookup"><span data-stu-id="f55ea-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f55ea-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="f55ea-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
