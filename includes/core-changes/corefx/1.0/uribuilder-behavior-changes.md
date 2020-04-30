---
ms.openlocfilehash: b3cc04d5675ea63a0a6b967e293da8a1bd79830d
ms.sourcegitcommit: d7666f6e49c57a769612602ea7857b927294ce47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "82595682"
---
### <a name="uribuilder-properties-no-longer-prepend-leading-characters"></a><span data-ttu-id="aa403-101">Le Proprietà UriBuilder non precedono più caratteri iniziali</span><span class="sxs-lookup"><span data-stu-id="aa403-101">UriBuilder properties no longer prepend leading characters</span></span>

<span data-ttu-id="aa403-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType>non antepone più un carattere `#` di primo <xref:System.UriBuilder.Query?displayProperty=nameWithType> livello e non antepone più `?` un carattere di primo livello quando ne è già presente uno.</span><span class="sxs-lookup"><span data-stu-id="aa403-102"><xref:System.UriBuilder.Fragment?displayProperty=nameWithType> no longer prepends a leading `#` character and <xref:System.UriBuilder.Query?displayProperty=nameWithType> no longer prepends a leading `?` character when one is already present.</span></span>

#### <a name="change-description"></a><span data-ttu-id="aa403-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="aa403-103">Change description</span></span>

<span data-ttu-id="aa403-104">In .NET Framework, le <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> proprietà <xref:System.UriBuilder.Query?displayProperty=nameWithType> e antepono `#` sempre `?` un carattere o rispettivamente al valore archiviato.</span><span class="sxs-lookup"><span data-stu-id="aa403-104">In .NET Framework, the <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> and <xref:System.UriBuilder.Query?displayProperty=nameWithType> properties always prepend a `#` or `?` character, respectively, to the value being stored.</span></span> <span data-ttu-id="aa403-105">Questo comportamento può comportare `#` la `?` presenza di più caratteri o nel valore archiviato se la stringa contiene già uno di questi caratteri iniziali.</span><span class="sxs-lookup"><span data-stu-id="aa403-105">This behavior can result in multiple `#` or `?` characters in the stored value if the string already contains one of these leading characters.</span></span> <span data-ttu-id="aa403-106">Ad esempio, il valore di <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> potrebbe diventare `##main`.</span><span class="sxs-lookup"><span data-stu-id="aa403-106">For example, the value of <xref:System.UriBuilder.Fragment?displayProperty=nameWithType> might become `##main`.</span></span>

<span data-ttu-id="aa403-107">A partire da .NET Core 1,0, queste proprietà non antepono più i `#` caratteri o `?` al valore archiviato se ne è già presente uno all'inizio della stringa.</span><span class="sxs-lookup"><span data-stu-id="aa403-107">Starting in .NET Core 1.0, these properties no longer prepend the `#` or `?` characters to the stored value if one is already present at the beginning of the string.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aa403-108">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="aa403-108">Version introduced</span></span>

<span data-ttu-id="aa403-109">1.0</span><span class="sxs-lookup"><span data-stu-id="aa403-109">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aa403-110">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="aa403-110">Recommended action</span></span>

<span data-ttu-id="aa403-111">Non è più necessario rimuovere in modo esplicito uno di questi caratteri iniziali durante l'impostazione dei valori delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="aa403-111">You no longer need to explicitly remove any of these leading characters when setting the property values.</span></span> <span data-ttu-id="aa403-112">Questa operazione è particolarmente utile quando si aggiungono valori, perché non è più necessario rimuovere l'oggetto principale `#` o `?` ogni volta che si aggiunge.</span><span class="sxs-lookup"><span data-stu-id="aa403-112">This is especially useful when you're appending values, because you no longer have to remove the leading `#` or `?` each time you append.</span></span>

<span data-ttu-id="aa403-113">Il frammento di codice seguente, ad esempio, Mostra la differenza di comportamento tra .NET Framework e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="aa403-113">For example, the following code snippet shows the behavior difference between .NET Framework and .NET Core.</span></span>

```csharp
var builder = new UriBuilder();
builder.Query = "one=1";
builder.Query += "&two=2";
builder.Query += "&three=3";
builder.Query += "&four=4";

Console.WriteLine(builder.Query);
```

- <span data-ttu-id="aa403-114">In .NET Framework, l'output è `????one=1&two=2&three=3&four=4`.</span><span class="sxs-lookup"><span data-stu-id="aa403-114">In .NET Framework, the output is `????one=1&two=2&three=3&four=4`.</span></span>
- <span data-ttu-id="aa403-115">In .NET Core, l'output è `?one=1&two=2&three=3&four=4`.</span><span class="sxs-lookup"><span data-stu-id="aa403-115">In .NET Core, the output is `?one=1&two=2&three=3&four=4`.</span></span>

#### <a name="category"></a><span data-ttu-id="aa403-116">Category</span><span class="sxs-lookup"><span data-stu-id="aa403-116">Category</span></span>

<span data-ttu-id="aa403-117">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="aa403-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aa403-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="aa403-118">Affected APIs</span></span>

- <xref:System.UriBuilder.Fragment?displayProperty=fullName>
- <xref:System.UriBuilder.Query?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.UriBuilder.Fragment`
- `T:System.UriBuilder.Query`

-->
