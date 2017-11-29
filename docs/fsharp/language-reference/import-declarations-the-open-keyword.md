---
title: 'Dichiarazioni di importazione: parola chiave open (F#)'
description: "Informazioni sulle dichiarazioni di importazione di F # e come vengono specificati di un modulo o spazio dei nomi i cui elementi è possibile fare riferimento senza utilizzare un nome completo."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1e98e48c-52e9-4314-8954-85d5583125f0
ms.openlocfilehash: a6d79bed3dd202657d06956edf9499a9b21a5f03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="import-declarations-the-open-keyword"></a><span data-ttu-id="cc1ad-104">Dichiarazioni di importazione: Il `open` (parola chiave)</span><span class="sxs-lookup"><span data-stu-id="cc1ad-104">Import Declarations: The `open` Keyword</span></span>

> [!NOTE]
<span data-ttu-id="cc1ad-105">I collegamenti di riferimento all'API in questo articolo portano a MSDN.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-105">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="cc1ad-106">Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-106">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="cc1ad-107">Un *una dichiarazione di importazione* Specifica spazio dei nomi i cui elementi è possibile fare riferimento senza utilizzare un nome completo o un modulo.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-107">An *import declaration* specifies a module or namespace whose elements you can reference without using a fully qualified name.</span></span>


## <a name="syntax"></a><span data-ttu-id="cc1ad-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc1ad-108">Syntax</span></span>

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a><span data-ttu-id="cc1ad-109">Note</span><span class="sxs-lookup"><span data-stu-id="cc1ad-109">Remarks</span></span>
<span data-ttu-id="cc1ad-110">Riferimento al codice utilizzando il percorso completo di spazio dei nomi o modulo ogni volta possibile creare codice difficile da leggere, scrivere e mantenere.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-110">Referencing code by using the fully qualified namespace or module path every time can create code that is hard to write, read, and maintain.</span></span> <span data-ttu-id="cc1ad-111">In alternativa, è possibile utilizzare il `open` parola chiave per utilizzati spesso i moduli e gli spazi dei nomi in modo che quando si fa riferimento a un membro di tale modulo o spazio dei nomi, è possibile utilizzare la forma abbreviata del nome anziché il nome completo.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-111">Instead, you can use the `open` keyword for frequently used modules and namespaces so that when you reference a member of that module or namespace, you can use the short form of the name instead of the fully qualified name.</span></span> <span data-ttu-id="cc1ad-112">Questa parola chiave è simile al `using` (parola chiave) in c#, `using namespace` in Visual C++, e `Imports` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-112">This keyword is similar to the `using` keyword in C#, `using namespace` in Visual C++, and `Imports` in Visual Basic.</span></span>

<span data-ttu-id="cc1ad-113">Il modulo o spazio dei nomi fornito deve essere nello stesso progetto o in un progetto di riferimento o un assembly.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-113">The module or namespace provided must be in the same project or in a referenced project or assembly.</span></span> <span data-ttu-id="cc1ad-114">In caso contrario, è possibile aggiungere un riferimento al progetto o utilizzare il `-reference` comando`-`opzione della riga (o la relativa abbreviazione, `-r`).</span><span class="sxs-lookup"><span data-stu-id="cc1ad-114">If it is not, you can add a reference to the project, or use the `-reference` command`-`line option (or its abbreviation, `-r`).</span></span> <span data-ttu-id="cc1ad-115">Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="cc1ad-115">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="cc1ad-116">La dichiarazione di importazione rende i nomi disponibili nel codice che segue la dichiarazione, fino alla fine di inclusione dello spazio dei nomi, modulo o file.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-116">The import declaration makes the names available in the code that follows the declaration, up to the end of the enclosing namespace, module, or file.</span></span>

<span data-ttu-id="cc1ad-117">Quando si utilizzano più dichiarazioni di importazione, verranno visualizzate su righe separate.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-117">When you use multiple import declarations, they should appear on separate lines.</span></span>

<span data-ttu-id="cc1ad-118">Il codice seguente viene illustrato come utilizzare il `open` (parola chiave) per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-118">The following code shows the use of the `open` keyword to simplify code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

<span data-ttu-id="cc1ad-119">Il compilatore F # non genera un errore o un avviso in caso di ambiguità quando si verifica lo stesso nome in più di uno spazio dei nomi o modulo aperto.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-119">The F# compiler does not emit an error or warning when ambiguities occur when the same name occurs in more than one open module or namespace.</span></span> <span data-ttu-id="cc1ad-120">In caso di ambiguità, F # offre preferenza al modulo o spazio dei nomi aperti più di recente.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-120">When ambiguities occur, F# gives preference to the more recently opened module or namespace.</span></span> <span data-ttu-id="cc1ad-121">Ad esempio, nel codice seguente, `empty` significa `Seq.empty`, anche se `empty` si trova in entrambi i `List` e `Seq` moduli.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-121">For example, in the following code, `empty` means `Seq.empty`, even though `empty` is located in both the `List` and `Seq` modules.</span></span>

```fsharp
open List
open Seq
printfn "%A" empty
```

<span data-ttu-id="cc1ad-122">Di conseguenza, prestare attenzione quando si aprono moduli o spazi dei nomi, ad esempio `List` o `Seq` contenenti membri con nomi identici; in alternativa, è consigliabile utilizzare nomi completi.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-122">Therefore, be careful when you open modules or namespaces such as `List` or `Seq` that contain members that have identical names; instead, consider using the qualified names.</span></span> <span data-ttu-id="cc1ad-123">È consigliabile evitare qualsiasi situazione in cui il codice dipende dall'ordine delle dichiarazioni di importazione.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-123">You should avoid any situation in which the code is dependent upon the order of the import declarations.</span></span>


## <a name="namespaces-that-are-open-by-default"></a><span data-ttu-id="cc1ad-124">Spazi dei nomi aperta per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="cc1ad-124">Namespaces That Are Open by Default</span></span>
<span data-ttu-id="cc1ad-125">Alcuni spazi dei nomi vengono utilizzati frequentemente nel codice F # che sono aperti in modo implicito senza necessità di una dichiarazione di importazione esplicita.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-125">Some namespaces are so frequently used in F# code that they are opened implicitly without the need of an explicit import declaration.</span></span> <span data-ttu-id="cc1ad-126">La tabella seguente illustra gli spazi dei nomi che sono aperti per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-126">The following table shows the namespaces that are open by default.</span></span>

|<span data-ttu-id="cc1ad-127">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="cc1ad-127">Namespace</span></span>|<span data-ttu-id="cc1ad-128">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc1ad-128">Description</span></span>|
|---------|-----------|
|`Microsoft.FSharp.Core`|<span data-ttu-id="cc1ad-129">Contiene le definizioni dei tipo F # di base per i tipi predefiniti, ad esempio `int` e `float`.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-129">Contains basic F# type definitions for built-in types such as `int` and `float`.</span></span>|
|`Microsoft.FSharp.Core.Operators`|<span data-ttu-id="cc1ad-130">Contiene operazioni aritmetiche di base, ad esempio `+` e `*`.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-130">Contains basic arithmetic operations such as `+` and `*`.</span></span>|
|`Microsoft.FSharp.Collections`|<span data-ttu-id="cc1ad-131">Contiene le classi di raccolta non modificabile, ad esempio `List` e `Array`.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-131">Contains immutable collection classes such as `List` and `Array`.</span></span>|
|`Microsoft.FSharp.Control`|<span data-ttu-id="cc1ad-132">Contiene tipi per i costrutti di controllo, ad esempio la valutazione lazy e flussi di lavoro asincroni.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-132">Contains types for control constructs such as lazy evaluation and asynchronous workflows.</span></span>|
|`Microsoft.FSharp.Text`|<span data-ttu-id="cc1ad-133">Contiene le funzioni per i/o formattato, ad esempio il `printf` (funzione).</span><span class="sxs-lookup"><span data-stu-id="cc1ad-133">Contains functions for formatted IO, such as the `printf` function.</span></span>|

## <a name="autoopen-attribute"></a><span data-ttu-id="cc1ad-134">AutoOpen (attributo)</span><span class="sxs-lookup"><span data-stu-id="cc1ad-134">AutoOpen Attribute</span></span>
<span data-ttu-id="cc1ad-135">È possibile applicare il `AutoOpen` attributo a un assembly, se si desidera aprire automaticamente un modulo o spazio dei nomi quando viene fatto riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-135">You can apply the `AutoOpen` attribute to an assembly if you want to automatically open a namespace or module when the assembly is referenced.</span></span> <span data-ttu-id="cc1ad-136">È inoltre possibile applicare il `AutoOpen` attributo a un modulo per aprire automaticamente tale modulo quando viene aperto il modulo padre o spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-136">You can also apply the `AutoOpen` attribute to a module to automatically open that module when the parent module or namespace is opened.</span></span> <span data-ttu-id="cc1ad-137">Per ulteriori informazioni, vedere [classe Core. AutoOpenAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span><span class="sxs-lookup"><span data-stu-id="cc1ad-137">For more information, see [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).</span></span>


## <a name="requirequalifiedaccess-attribute"></a><span data-ttu-id="cc1ad-138">RequireQualifiedAccess (attributo)</span><span class="sxs-lookup"><span data-stu-id="cc1ad-138">RequireQualifiedAccess Attribute</span></span>
<span data-ttu-id="cc1ad-139">Alcuni moduli, record o i tipi di unione possono specificare il `RequireQualifiedAccess` attributo.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-139">Some modules, records, or union types may specify the `RequireQualifiedAccess` attribute.</span></span> <span data-ttu-id="cc1ad-140">Quando si fa riferimento a elementi di tali moduli, record o unioni, è necessario utilizzare un nome completo indipendentemente dal fatto se si include una dichiarazione di importazione.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-140">When you reference elements of those modules, records, or unions, you must use a qualified name regardless of whether you include an import declaration.</span></span> <span data-ttu-id="cc1ad-141">Se si usa questo attributo in modo strategico in tipi che definiscono in genere utilizzati nomi, consente di evitare conflitti di nome e codice molto più adattabile a modifiche nelle librerie.</span><span class="sxs-lookup"><span data-stu-id="cc1ad-141">If you use this attribute strategically on types that define commonly used names, you help avoid name collisions and thereby make code more resilient to changes in libraries.</span></span> <span data-ttu-id="cc1ad-142">Per ulteriori informazioni, vedere [classe Core. RequireQualifiedAccessAttribute](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span><span class="sxs-lookup"><span data-stu-id="cc1ad-142">For more information, see [Core.RequireQualifiedAccessAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).</span></span>


## <a name="see-also"></a><span data-ttu-id="cc1ad-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc1ad-143">See Also</span></span>
[<span data-ttu-id="cc1ad-144">C# riferimenti al linguaggio</span><span class="sxs-lookup"><span data-stu-id="cc1ad-144"># Language Reference</span></span>](index.md)

[<span data-ttu-id="cc1ad-145">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="cc1ad-145">Namespaces</span></span>](namespaces.md)

[<span data-ttu-id="cc1ad-146">Moduli</span><span class="sxs-lookup"><span data-stu-id="cc1ad-146">Modules</span></span>](modules.md)

