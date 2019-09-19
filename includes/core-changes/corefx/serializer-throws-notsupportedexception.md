---
ms.openlocfilehash: 39d1b2dba8077bf9bf998775f8967d455f36b549
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119282"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="f12f0-101">Tipo di eccezione del serializzatore `JsonException` JSON modificato da a`NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="f12f0-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="f12f0-102">In .NET Core 3,0 Preview da 6 a 8, il serializzatore genera <xref:System.Text.Json.JsonException> un'errore quando viene rilevato un tipo di raccolta derivato non supportato.</span><span class="sxs-lookup"><span data-stu-id="f12f0-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="f12f0-103">A partire da .NET Core 3,0 Preview 9, il serializzatore <xref:System.NotSupportedException> genera invece un.</span><span class="sxs-lookup"><span data-stu-id="f12f0-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f12f0-104">Descrizione della modifica</span><span class="sxs-lookup"><span data-stu-id="f12f0-104">Change description</span></span>

<span data-ttu-id="f12f0-105">In .NET Core 3,0 Preview 6 fino all'anteprima 8, il serializzatore genera <xref:System.Text.Json.JsonException> un'errore quando viene rilevato un tipo di raccolta derivato non supportato.</span><span class="sxs-lookup"><span data-stu-id="f12f0-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="f12f0-106">Un *tipo di raccolta derivato non supportato* è un tipo di raccolta non assegnabile a uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f12f0-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

 - <xref:System.Collections.IList>
 - <xref:System.Collections.Generic.ICollection%601>
 - <xref:System.Collections.Generic.Stack%601>
 - <xref:System.Collections.Generic.Queue%601>`
 - <xref:System.Collections.IDictionary>
 - [<span data-ttu-id="f12f0-107">Stringa\<IDictionary, T ></span><span class="sxs-lookup"><span data-stu-id="f12f0-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="f12f0-108">A partire da .NET Core 3,0 Preview 9, il serializzatore <xref:System.NotSupportedException> genera un'eccezione quando incontra un tipo di raccolta non supportato.</span><span class="sxs-lookup"><span data-stu-id="f12f0-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="f12f0-109">Il nuovo tipo di eccezione riflette meglio il motivo per cui l'operazione di deserializzazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="f12f0-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f12f0-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="f12f0-110">Version introduced</span></span>

<span data-ttu-id="f12f0-111">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="f12f0-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f12f0-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="f12f0-112">Recommended action</span></span>

<span data-ttu-id="f12f0-113">Se si sta <xref:System.Text.Json.JsonException> eseguendo la deserializzazione, è opportuno prendere in considerazione anche l' <xref:System.NotSupportedException>intercettazione.</span><span class="sxs-lookup"><span data-stu-id="f12f0-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="f12f0-114">Category</span><span class="sxs-lookup"><span data-stu-id="f12f0-114">Category</span></span>

<span data-ttu-id="f12f0-115">CoreFx</span><span class="sxs-lookup"><span data-stu-id="f12f0-115">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f12f0-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="f12f0-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
