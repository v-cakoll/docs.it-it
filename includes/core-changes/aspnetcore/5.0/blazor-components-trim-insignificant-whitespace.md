---
ms.openlocfilehash: ca369c4e3f78648c6e8e0bcb5d54711d3009a769
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174263"
---
### <a name="blazor-insignificant-whitespace-trimmed-from-components-at-compile-time"></a><span data-ttu-id="2acf2-101">Blazer: spazi vuoti non significativi rimossi dai componenti in fase di compilazione</span><span class="sxs-lookup"><span data-stu-id="2acf2-101">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>

<span data-ttu-id="2acf2-102">A partire da ASP.NET Core 5,0 Preview 7, il compilatore Razor omette gli spazi vuoti non significativi nei componenti blazer (file*Razor* ) in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="2acf2-102">Starting with ASP.NET Core 5.0 Preview 7, the Razor compiler omits insignificant whitespace in Blazor components (*.razor* files) at compile time.</span></span> <span data-ttu-id="2acf2-103">Per informazioni, vedere Issue [DotNet/aspnetcore # 23568](https://github.com/dotnet/aspnetcore/issues/23568).</span><span class="sxs-lookup"><span data-stu-id="2acf2-103">For discussion, see issue [dotnet/aspnetcore#23568](https://github.com/dotnet/aspnetcore/issues/23568).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="2acf2-104">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="2acf2-104">Version introduced</span></span>

<span data-ttu-id="2acf2-105">5,0 Anteprima 7</span><span class="sxs-lookup"><span data-stu-id="2acf2-105">5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="2acf2-106">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="2acf2-106">Old behavior</span></span>

<span data-ttu-id="2acf2-107">Nelle versioni 3. x di Blazer server e del webassembly blazer, lo spazio vuoto viene rispettato nel codice sorgente di un componente.</span><span class="sxs-lookup"><span data-stu-id="2acf2-107">In 3.x versions of Blazor Server and Blazor WebAssembly, whitespace is honored in a component's source code.</span></span> <span data-ttu-id="2acf2-108">I nodi di testo con solo spazi vuoti vengono visualizzati nel DOM (Document Object Model) del browser anche quando non sono presenti effetti visivi.</span><span class="sxs-lookup"><span data-stu-id="2acf2-108">Whitespace-only text nodes render in the browser's Document Object Model (DOM) even when there's no visual effect.</span></span>

<span data-ttu-id="2acf2-109">Si consideri il seguente codice componente Blazer:</span><span class="sxs-lookup"><span data-stu-id="2acf2-109">Consider the following Blazor component code:</span></span>

```razor
<ul>
    @foreach (var item in Items)
    {
        <li>
            @item.Text
        </li>
    }
</ul>
```

<span data-ttu-id="2acf2-110">Nell'esempio precedente viene eseguito il rendering di due nodi dello spazio vuoto:</span><span class="sxs-lookup"><span data-stu-id="2acf2-110">The preceding example renders two whitespace nodes:</span></span>

* <span data-ttu-id="2acf2-111">All'esterno del `@foreach` blocco di codice.</span><span class="sxs-lookup"><span data-stu-id="2acf2-111">Outside of the `@foreach` code block.</span></span>
* <span data-ttu-id="2acf2-112">Intorno all' `<li>` elemento.</span><span class="sxs-lookup"><span data-stu-id="2acf2-112">Around the `<li>` element.</span></span>
* <span data-ttu-id="2acf2-113">Intorno all' `@item.Text` output.</span><span class="sxs-lookup"><span data-stu-id="2acf2-113">Around the `@item.Text` output.</span></span>

<span data-ttu-id="2acf2-114">Un elenco contenente 100 elementi restituisce i nodi con spazio 402.</span><span class="sxs-lookup"><span data-stu-id="2acf2-114">A list containing 100 items results in 402 whitespace nodes.</span></span> <span data-ttu-id="2acf2-115">Questa è la metà di tutti i nodi di cui è stato eseguito il rendering, anche se nessuno dei nodi spazio ha effetto visivo sull'output sottoposto a rendering.</span><span class="sxs-lookup"><span data-stu-id="2acf2-115">That's over half of all nodes rendered, even though none of the whitespace nodes visually affect the rendered output.</span></span>

<span data-ttu-id="2acf2-116">Quando si esegue il rendering del codice HTML statico per i componenti, gli spazi vuoti all'interno di un tag</span><span class="sxs-lookup"><span data-stu-id="2acf2-116">When rendering static HTML for components, whitespace inside a tag wasn't preserved.</span></span> <span data-ttu-id="2acf2-117">Ad esempio, visualizzare l'origine del componente seguente:</span><span class="sxs-lookup"><span data-stu-id="2acf2-117">For example, view the source of the following component:</span></span>

```razor
<foo        bar="baz"     />
```

<span data-ttu-id="2acf2-118">Lo spazio vuoto non viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="2acf2-118">Whitespace isn't preserved.</span></span> <span data-ttu-id="2acf2-119">L'output di cui è stato eseguito il rendering è:</span><span class="sxs-lookup"><span data-stu-id="2acf2-119">The pre-rendered output is:</span></span>

```razor
<foo bar="baz" />
```

#### <a name="new-behavior"></a><span data-ttu-id="2acf2-120">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="2acf2-120">New behavior</span></span>

<span data-ttu-id="2acf2-121">A meno che la `@preservewhitespace` direttiva non venga usata con value `true` , i nodi dello spazio vuoto vengono rimossi se:</span><span class="sxs-lookup"><span data-stu-id="2acf2-121">Unless the `@preservewhitespace` directive is used with value `true`, whitespace nodes are removed if they:</span></span>

* <span data-ttu-id="2acf2-122">Sono iniziali o finali all'interno di un elemento.</span><span class="sxs-lookup"><span data-stu-id="2acf2-122">Are leading or trailing within an element.</span></span>
* <span data-ttu-id="2acf2-123">Sono iniziali o finali in un `RenderFragment` parametro.</span><span class="sxs-lookup"><span data-stu-id="2acf2-123">Are leading or trailing within a `RenderFragment` parameter.</span></span> <span data-ttu-id="2acf2-124">Ad esempio, il contenuto figlio viene passato a un altro componente.</span><span class="sxs-lookup"><span data-stu-id="2acf2-124">For example, child content being passed to another component.</span></span>
* <span data-ttu-id="2acf2-125">Precede o segue un blocco di codice C#, ad esempio `@if` e `@foreach` .</span><span class="sxs-lookup"><span data-stu-id="2acf2-125">Precede or follow a C# code block such as `@if` and `@foreach`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="2acf2-126">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="2acf2-126">Reason for change</span></span>

<span data-ttu-id="2acf2-127">Uno degli obiettivi di Blazer in ASP.NET Core 5,0 è quello di migliorare le prestazioni del rendering e delle differenze.</span><span class="sxs-lookup"><span data-stu-id="2acf2-127">A goal for Blazor in ASP.NET Core 5.0 is to improve the performance of rendering and diffing.</span></span> <span data-ttu-id="2acf2-128">I nodi dell'albero degli spazi vuoti non significativi hanno consumato fino al 40% del tempo di rendering nei benchmark.</span><span class="sxs-lookup"><span data-stu-id="2acf2-128">Insignificant whitespace tree nodes consumed up to 40 percent of the rendering time in benchmarks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="2acf2-129">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="2acf2-129">Recommended action</span></span>

<span data-ttu-id="2acf2-130">Nella maggior parte dei casi, il layout visivo del componente di cui è stato eseguito il rendering non è interessato.</span><span class="sxs-lookup"><span data-stu-id="2acf2-130">In most cases, the visual layout of the rendered component is unaffected.</span></span> <span data-ttu-id="2acf2-131">Tuttavia, la rimozione degli spazi vuoti potrebbe influire sull'output sottoposto a rendering quando si usa una regola CSS come `white-space: pre` .</span><span class="sxs-lookup"><span data-stu-id="2acf2-131">However, the whitespace removal might affect the rendered output when using a CSS rule like `white-space: pre`.</span></span> <span data-ttu-id="2acf2-132">Per disabilitare questa ottimizzazione delle prestazioni e mantenere lo spazio vuoto, effettuare una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2acf2-132">To disable this performance optimization and preserve the whitespace, take one of the following actions:</span></span>

* <span data-ttu-id="2acf2-133">Aggiungere la `@preservewhitespace true` direttiva all'inizio del file *Razor* per applicare la preferenza a un componente specifico.</span><span class="sxs-lookup"><span data-stu-id="2acf2-133">Add the `@preservewhitespace true` directive at the top of the *.razor* file to apply the preference to a specific component.</span></span>
* <span data-ttu-id="2acf2-134">Aggiungere la `@preservewhitespace true` direttiva all'interno di un file *_Imports. Razor* per applicare la preferenza a un'intera sottodirectory o all'intero progetto.</span><span class="sxs-lookup"><span data-stu-id="2acf2-134">Add the `@preservewhitespace true` directive inside an *_Imports.razor* file to apply the preference to an entire subdirectory or the entire project.</span></span>

<span data-ttu-id="2acf2-135">Nella maggior parte dei casi, non è necessaria alcuna azione, perché le applicazioni in genere continuano a funzionare normalmente (ma più velocemente).</span><span class="sxs-lookup"><span data-stu-id="2acf2-135">In most cases, no action is required, as applications will typically continue to behave normally (but faster).</span></span> <span data-ttu-id="2acf2-136">Se la rimozione degli spazi vuoti causa problemi per un particolare componente, utilizzare `@preservewhitespace true` in tale componente per disabilitare questa ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="2acf2-136">If the whitespace stripping causes any problems for a particular component, use `@preservewhitespace true` in that component to disable this optimization.</span></span>

#### <a name="category"></a><span data-ttu-id="2acf2-137">Categoria</span><span class="sxs-lookup"><span data-stu-id="2acf2-137">Category</span></span>

<span data-ttu-id="2acf2-138">Risultato dell'azione di</span><span class="sxs-lookup"><span data-stu-id="2acf2-138">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="2acf2-139">API interessate</span><span class="sxs-lookup"><span data-stu-id="2acf2-139">Affected APIs</span></span>

<span data-ttu-id="2acf2-140">Nessuno</span><span class="sxs-lookup"><span data-stu-id="2acf2-140">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
