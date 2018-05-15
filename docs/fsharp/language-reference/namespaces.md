---
title: Spazi dei nomi (F#)
description: 'Informazioni su come uno spazio dei nomi in F # consente di organizzare il codice in aree di funzionalità correlate, consentendo di collegare un nome a un raggruppamento di elementi del programma.'
ms.date: 04/24/2017
ms.openlocfilehash: 151079864f18fff79dac108889b68b3acf1566a1
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2018
---
# <a name="namespaces"></a><span data-ttu-id="e8d57-103">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="e8d57-103">Namespaces</span></span>

<span data-ttu-id="e8d57-104">Uno spazio dei nomi consente di organizzare il codice in aree di funzionalità correlate perché consente di collegare un nome a un raggruppamento di elementi di programma.</span><span class="sxs-lookup"><span data-stu-id="e8d57-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>


## <a name="syntax"></a><span data-ttu-id="e8d57-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8d57-105">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="e8d57-106">Note</span><span class="sxs-lookup"><span data-stu-id="e8d57-106">Remarks</span></span>
<span data-ttu-id="e8d57-107">Se si desidera inserire il codice in uno spazio dei nomi, la prima dichiarazione nel file deve dichiarare lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-107">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="e8d57-108">Il contenuto dell'intero file diventa quindi parte dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-108">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="e8d57-109">Spazi dei nomi non può contenere direttamente le funzioni e valori.</span><span class="sxs-lookup"><span data-stu-id="e8d57-109">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="e8d57-110">Invece, funzioni e i valori devono essere inclusi nei moduli e sono inclusi negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-110">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="e8d57-111">Spazi dei nomi può contenere tipi di moduli.</span><span class="sxs-lookup"><span data-stu-id="e8d57-111">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="e8d57-112">Spazi dei nomi possono essere dichiarate in modo esplicito con la parola chiave dello spazio dei nomi o in modo implicito quando si dichiara un modulo.</span><span class="sxs-lookup"><span data-stu-id="e8d57-112">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="e8d57-113">Per dichiarare uno spazio dei nomi in modo esplicito, utilizzare la parola chiave dello spazio dei nomi seguita dal nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-113">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="e8d57-114">Nell'esempio seguente viene illustrato un file di codice che dichiara uno spazio dei nomi widget con un tipo e un modulo incluso nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-114">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="e8d57-115">Se l'intero contenuto del file in un modulo, è inoltre possibile dichiarare spazi dei nomi in modo implicito tramite il `module` (parola chiave) e fornendo il nuovo nome dello spazio dei nomi nel nome del modulo completo.</span><span class="sxs-lookup"><span data-stu-id="e8d57-115">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="e8d57-116">Nell'esempio seguente viene illustrato un file di codice che dichiara uno spazio dei nomi `Widgets` e un modulo `WidgetsModule`, che contiene una funzione.</span><span class="sxs-lookup"><span data-stu-id="e8d57-116">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="e8d57-117">Il codice seguente equivale a quello precedente, ma il modulo è una dichiarazione di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="e8d57-117">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="e8d57-118">In tal caso, lo spazio dei nomi deve essere presente nella propria riga.</span><span class="sxs-lookup"><span data-stu-id="e8d57-118">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="e8d57-119">Se nello stesso file in uno o più spazi, è necessaria più di un modulo, è necessario utilizzare le dichiarazioni di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="e8d57-119">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="e8d57-120">Quando si utilizzano dichiarazioni di modulo locali, è possibile utilizzare lo spazio dei nomi completo nelle dichiarazioni di modulo.</span><span class="sxs-lookup"><span data-stu-id="e8d57-120">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="e8d57-121">Il codice seguente viene illustrato un file con una dichiarazione dello spazio dei nomi e due dichiarazioni di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="e8d57-121">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="e8d57-122">In questo caso, i moduli sono contenuti direttamente nello spazio dei nomi; non vi è alcun modulo creato in modo implicito con lo stesso nome del file.</span><span class="sxs-lookup"><span data-stu-id="e8d57-122">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="e8d57-123">Qualsiasi altro codice nel file, ad esempio un `do` l'associazione, è nello spazio dei nomi ma non nei moduli interni, pertanto è necessario qualificare il membro modulo `widgetFunction` utilizzando il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="e8d57-123">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="e8d57-124">L'output di questo esempio è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="e8d57-124">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="e8d57-125">Per ulteriori informazioni, vedere [moduli](modules.md).</span><span class="sxs-lookup"><span data-stu-id="e8d57-125">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="e8d57-126">Spazi dei nomi annidati</span><span class="sxs-lookup"><span data-stu-id="e8d57-126">Nested Namespaces</span></span>
<span data-ttu-id="e8d57-127">Quando si crea uno spazio dei nomi annidato, è necessario specificarla.</span><span class="sxs-lookup"><span data-stu-id="e8d57-127">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="e8d57-128">In caso contrario, si crea un nuovo spazio dei nomi di primo livello.</span><span class="sxs-lookup"><span data-stu-id="e8d57-128">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="e8d57-129">Rientro viene ignorato nelle dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-129">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="e8d57-130">Nell'esempio seguente viene illustrato come dichiarare uno spazio dei nomi annidato.</span><span class="sxs-lookup"><span data-stu-id="e8d57-130">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="e8d57-131">Spazi dei nomi di file e assembly</span><span class="sxs-lookup"><span data-stu-id="e8d57-131">Namespaces in Files and Assemblies</span></span>
<span data-ttu-id="e8d57-132">Spazi dei nomi può estendersi su più file in un singolo progetto o di una compilazione.</span><span class="sxs-lookup"><span data-stu-id="e8d57-132">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="e8d57-133">Il termine *frammento dello spazio dei nomi* descrive la parte di uno spazio dei nomi che è incluso in un file.</span><span class="sxs-lookup"><span data-stu-id="e8d57-133">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="e8d57-134">Spazi dei nomi può occupare più assembly.</span><span class="sxs-lookup"><span data-stu-id="e8d57-134">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="e8d57-135">Ad esempio, il `System` spazio dei nomi include l'intero .NET Framework, si estende su molti assembly che contiene molti spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="e8d57-135">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>


## <a name="global-namespace"></a><span data-ttu-id="e8d57-136">Namespace globale</span><span class="sxs-lookup"><span data-stu-id="e8d57-136">Global Namespace</span></span>
<span data-ttu-id="e8d57-137">Lo spazio dei nomi predefiniti `global` per inserire i nomi dello spazio dei nomi principali di .NET.</span><span class="sxs-lookup"><span data-stu-id="e8d57-137">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="e8d57-138">È possibile inoltre utilizzare globale per fare riferimento il primo livello dello spazio dei nomi .NET, ad esempio, per risolvere i conflitti di nome con altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-138">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="e8d57-139">Spazi dei nomi ricorsiva</span><span class="sxs-lookup"><span data-stu-id="e8d57-139">Recursive namespaces</span></span>

<span data-ttu-id="e8d57-140">F # 4.1 introduce la nozione di spazi dei nomi che consentono di tutto il codice indipendente reciprocamente sono ricorsivi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="e8d57-141">Questa operazione viene eseguita tramite `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="e8d57-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="e8d57-142">Utilizzo di `namespace rec` possibile tentare di risolvere alcune difficoltà in non è in grado di scrivere codice reciprocamente referenziale tra i tipi e i moduli.</span><span class="sxs-lookup"><span data-stu-id="e8d57-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="e8d57-143">Di seguito è riportato un esempio di questo oggetto:</span><span class="sxs-lookup"><span data-stu-id="e8d57-143">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

<span data-ttu-id="e8d57-144">Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` fanno riferimento a altro.</span><span class="sxs-lookup"><span data-stu-id="e8d57-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="e8d57-145">Inoltre, il modulo `BananaHelpers` e la classe `Banana` anche fare riferimento a altro.</span><span class="sxs-lookup"><span data-stu-id="e8d57-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="e8d57-146">Ciò non sarebbe possibile esprimere in F #, se è stato rimosso il `rec` (parola chiave) dal `MutualReferences` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e8d57-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="e8d57-147">Questa funzionalità è anche disponibile per primo livello [moduli](modules.md) in F # 4.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="e8d57-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8d57-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8d57-148">See Also</span></span>
[<span data-ttu-id="e8d57-149">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="e8d57-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="e8d57-150">Moduli</span><span class="sxs-lookup"><span data-stu-id="e8d57-150">Modules</span></span>](modules.md)

[<span data-ttu-id="e8d57-151">1009-F # RFC Fi - Consenti moduli e tipi reciprocamente referenziali su maggiori ambiti all'interno dei file</span><span class="sxs-lookup"><span data-stu-id="e8d57-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
