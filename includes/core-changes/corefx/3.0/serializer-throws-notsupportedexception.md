---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021581"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="c0394-101">Tipo di eccezione `JsonException` del serializzatore Json modificato da a`NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="c0394-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="c0394-102">In .NET Core 3.0 Preview 6 a <xref:System.Text.Json.JsonException> 8, il serializzatore genera un quando viene rilevato un tipo di raccolta derivato non supportato.</span><span class="sxs-lookup"><span data-stu-id="c0394-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="c0394-103">A partire da .NET Core 3.0 Preview <xref:System.NotSupportedException> 9, il serializzatore genera invece un eccezione.</span><span class="sxs-lookup"><span data-stu-id="c0394-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c0394-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="c0394-104">Change description</span></span>

<span data-ttu-id="c0394-105">In .NET Core 3.0 Preview 6 a Preview <xref:System.Text.Json.JsonException> 8, il serializzatore genera un quando viene rilevato un tipo di raccolta derivato non supportato.</span><span class="sxs-lookup"><span data-stu-id="c0394-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="c0394-106">Un *tipo di raccolta derivato non supportato* è qualsiasi tipo di raccolta che non è assegnabile a uno dei tipi seguenti:An unsupported derived collection type is any collection type that isn't assignable to one of the following types:</span><span class="sxs-lookup"><span data-stu-id="c0394-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="c0394-107">Stringa\<IDictionary,></span><span class="sxs-lookup"><span data-stu-id="c0394-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="c0394-108">A partire da .NET Core 3.0 Preview <xref:System.NotSupportedException> 9, il serializzatore genera un quando si rileva un tipo di raccolta non supportato.</span><span class="sxs-lookup"><span data-stu-id="c0394-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="c0394-109">Il nuovo tipo di eccezione riflette meglio il motivo per cui l'operazione di deserializzazione ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c0394-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c0394-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c0394-110">Version introduced</span></span>

<span data-ttu-id="c0394-111">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="c0394-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c0394-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c0394-112">Recommended action</span></span>

<span data-ttu-id="c0394-113">Se si sta <xref:System.Text.Json.JsonException> intercettando durante la deserializzazione, <xref:System.NotSupportedException>si potrebbe prendere in considerazione anche l'intercettazione .</span><span class="sxs-lookup"><span data-stu-id="c0394-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="c0394-114">Category</span><span class="sxs-lookup"><span data-stu-id="c0394-114">Category</span></span>

<span data-ttu-id="c0394-115">Librerie .NET di base</span><span class="sxs-lookup"><span data-stu-id="c0394-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c0394-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="c0394-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
