---
title: 'Dichiarazioni di importazione: parola chiave open (F#)'
description: Informazioni sulle dichiarazioni di importazione di F# e come vengono specificati un modulo o dello spazio dei nomi cui elementi è possibile fare riferimento senza usare un nome completo.
ms.date: 05/16/2016
ms.openlocfilehash: 8cae4b4f5418689bfb0933b7db4ec23a313d5ed8
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "46586623"
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="a266d-103">Dichiarazioni di importazione: Il `open` (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="a266d-103">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
<span data-ttu-id="a266d-104">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="a266d-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="a266d-105">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="a266d-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="a266d-106">Un' *dichiarazione di importazione* specifica un modulo o i cui elementi è possibile fare riferimento senza usare un nome completo dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a266d-106">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>

## <a name="syntax"></a><span data-ttu-id="a266d-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a266d-107">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="a266d-108">Note</span><span class="sxs-lookup"><span data-stu-id="a266d-108">Remarks</span></span>

<span data-ttu-id="a266d-109">Riferimento al codice utilizzando il percorso completo dello spazio dei nomi o modulo ogni volta possibile creare codice difficile da leggere, scrivere e mantenere.</span><span class="sxs-lookup"><span data-stu-id="a266d-109">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="a266d-110">In alternativa, è possibile usare il `open` parola chiave per utilizzati spesso moduli e spazi dei nomi in modo che quando si fa riferimento a un membro di tale modulo o dello spazio dei nomi, è possibile usare la versione abbreviata del nome anziché il nome completo.</span><span class="sxs-lookup"><span data-stu-id="a266d-110">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="a266d-111">Questa parola chiave è simile al `using` parola chiave nel linguaggio c# `using namespace` in Visual C++ e `Imports` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a266d-111">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="a266d-112">Il modulo o dello spazio dei nomi fornito deve essere nello stesso progetto o in un progetto di riferimento o un assembly.</span><span class="sxs-lookup"><span data-stu-id="a266d-112">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="a266d-113">In caso contrario, è possibile aggiungere un riferimento al progetto o usare il `-reference` comandi`-`opzione della riga (o la relativa abbreviazione `-r`).</span><span class="sxs-lookup"><span data-stu-id="a266d-113">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="a266d-114">Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="a266d-114">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="a266d-115">La dichiarazione di importazione sono disponibili i nomi nel codice che segue la dichiarazione, fino alla fine dell'inclusione dello spazio dei nomi, modulo o file.</span><span class="sxs-lookup"><span data-stu-id="a266d-115">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="a266d-116">Quando si usano più dichiarazioni di importazione, verranno visualizzate in righe separate.</span><span class="sxs-lookup"><span data-stu-id="a266d-116">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="a266d-117">Il codice seguente viene illustrato come utilizzare il `open` (parola chiave) per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="a266d-117">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="a266d-118">Il compilatore F# non genera un errore o un avviso quando le ambiguità si verificano quando si verifica lo stesso nome in più di un modulo aperto o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a266d-118">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="a266d-119">Quando si verificano ambiguità, F# accorda priorità a più file aperti di recente modulo o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a266d-119">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="a266d-120">Ad esempio, nel codice seguente, `empty` significa `Seq.empty`, anche se `empty` si trova in entrambi i `List` e `Seq` moduli.</span><span class="sxs-lookup"><span data-stu-id="a266d-120">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="a266d-121">Pertanto, prestare attenzione quando si apre, ad esempio i moduli o spazi dei nomi `List` o `Seq` che contengono membri che hanno nomi identici; in alternativa, è consigliabile usare i nomi completi.</span><span class="sxs-lookup"><span data-stu-id="a266d-121">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="a266d-122">È consigliabile evitare qualsiasi situazione in cui il codice è dipende dall'ordine delle dichiarazioni di importazione.</span><span class="sxs-lookup"><span data-stu-id="a266d-122">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>

## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="a266d-123">Spazi dei nomi che sono aperte per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="a266d-123">Namespaces That Are Open by Default</span></span>

<span data-ttu-id="a266d-124">Alcuni spazi dei nomi vengono utilizzati con una frequenza nel codice F# che sono aperti in modo implicito senza la necessità di una dichiarazione di importazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="a266d-124">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="a266d-125">La tabella seguente mostra gli spazi dei nomi che sono aperte per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a266d-125">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="a266d-126">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="a266d-126">Namespace</span></span>|<span data-ttu-id="a266d-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a266d-127">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="a266d-128">Contiene le definizioni dei tipo F# di base per i tipi predefiniti, ad esempio `int` e `float`.</span><span class="sxs-lookup"><span data-stu-id="a266d-128">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="a266d-129">Contiene operazioni aritmetiche di base, ad esempio `+` e `*`.</span><span class="sxs-lookup"><span data-stu-id="a266d-129">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="a266d-130">Contiene le classi di raccolte non modificabili, ad esempio `List` e `Array`.</span><span class="sxs-lookup"><span data-stu-id="a266d-130">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="a266d-131">Contiene tipi per i costrutti di controllo, ad esempio la valutazione lazy e flussi di lavoro asincroni.</span><span class="sxs-lookup"><span data-stu-id="a266d-131">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="a266d-132">Contiene funzioni per i/o formattati, ad esempio il `printf` (funzione).</span><span class="sxs-lookup"><span data-stu-id="a266d-132">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="a266d-133">AutoOpen (attributo)</span><span class="sxs-lookup"><span data-stu-id="a266d-133">AutoOpen Attribute</span></span>

<span data-ttu-id="a266d-134">È possibile applicare il `AutoOpen` attributo a un assembly, se si vuole aprire automaticamente un modulo o dello spazio dei nomi quando viene fatto riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="a266d-134">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="a266d-135">È inoltre possibile applicare il `AutoOpen` attributo a un modulo a modulo si apre automaticamente quando viene aperto il modulo padre o dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a266d-135">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="a266d-136">Per altre informazioni, vedere [classe Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="a266d-136">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>

## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="a266d-137">RequireQualifiedAccess (attributo)</span><span class="sxs-lookup"><span data-stu-id="a266d-137">RequireQualifiedAccess Attribute</span></span>

<span data-ttu-id="a266d-138">Alcuni moduli, record o i tipi di unione possono specificare il `RequireQualifiedAccess` attributo.</span><span class="sxs-lookup"><span data-stu-id="a266d-138">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="a266d-139">Quando si fa riferimento a elementi di tali moduli, record o unioni, è necessario utilizzare un nome completo indipendentemente dal fatto che è includere una dichiarazione di importazione.</span><span class="sxs-lookup"><span data-stu-id="a266d-139">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="a266d-140">Se si usa questo attributo in modo strategico su tipi che definiscono in genere utilizzati nomi, consente di evitare conflitti di nome e codice più resiliente a modifiche nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="a266d-140">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="a266d-141">Per altre informazioni, vedere [classe Core. RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="a266d-141">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>

## <a name="see-also"></a><span data-ttu-id="a266d-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a266d-142">See also</span></span>

- [<span data-ttu-id="a266d-143">C# riferimenti al linguaggio</span><span class="sxs-lookup"><span data-stu-id="a266d-143"># Language Reference</span></span>](index.md)
- [<span data-ttu-id="a266d-144">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="a266d-144">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="a266d-145">Moduli</span><span class="sxs-lookup"><span data-stu-id="a266d-145">Modules</span></span>](modules.md)
