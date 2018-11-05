---
title: Spazi dei nomi (F#)
description: Informazioni su come uno spazio dei nomi in F# consente di organizzare il codice in aree di funzionalità correlate grazie alla possibilità di associare un nome a un raggruppamento di elementi di programma.
ms.date: 04/24/2017
ms.openlocfilehash: 769a1241f76ac32d3a6a80bd637078493119bb3c
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "44178254"
---
# <a name="namespaces"></a><span data-ttu-id="54d35-103">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="54d35-103">Namespaces</span></span>

<span data-ttu-id="54d35-104">Uno spazio dei nomi consente di organizzare il codice in aree di funzionalità correlate perché consente di collegare un nome a un raggruppamento di elementi di programma.</span><span class="sxs-lookup"><span data-stu-id="54d35-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of program elements.</span></span>

## <a name="syntax"></a><span data-ttu-id="54d35-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54d35-105">Syntax</span></span>

```fsharp
namespace [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="54d35-106">Note</span><span class="sxs-lookup"><span data-stu-id="54d35-106">Remarks</span></span>

<span data-ttu-id="54d35-107">Se si desidera inserire il codice in uno spazio dei nomi, la prima dichiarazione nel file deve dichiarare lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-107">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="54d35-108">Il contenuto dell'intero file diventa quindi parte dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-108">The contents of the entire file then become part of the namespace.</span></span>

<span data-ttu-id="54d35-109">Gli spazi dei nomi non può contenere direttamente i valori e le funzioni.</span><span class="sxs-lookup"><span data-stu-id="54d35-109">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="54d35-110">Al contrario, i valori e le funzioni devono essere inclusi nei moduli e i moduli sono inclusi negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-110">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="54d35-111">Gli spazi dei nomi può contenere tipi di moduli.</span><span class="sxs-lookup"><span data-stu-id="54d35-111">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="54d35-112">Gli spazi dei nomi possono essere dichiarate in modo esplicito con la parola chiave dello spazio dei nomi o in modo implicito quando si dichiara un modulo.</span><span class="sxs-lookup"><span data-stu-id="54d35-112">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="54d35-113">Per dichiarare uno spazio dei nomi in modo esplicito, usare la parola chiave dello spazio dei nomi seguita dal nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-113">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="54d35-114">Nell'esempio seguente viene illustrato un file di codice che dichiara uno spazio dei nomi widget con un tipo e un modulo incluso nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-114">The following example shows a code file that declares a namespace Widgets with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="54d35-115">Se l'intero contenuto del file è in uno dei moduli, è anche possibile dichiarare gli spazi dei nomi in modo implicito usando la `module` (parola chiave) e fornendo il nuovo nome dello spazio dei nomi nel nome completo del modulo.</span><span class="sxs-lookup"><span data-stu-id="54d35-115">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="54d35-116">L'esempio seguente illustra un file di codice che dichiara uno spazio dei nomi `Widgets` e un modulo `WidgetsModule`, che contiene una funzione.</span><span class="sxs-lookup"><span data-stu-id="54d35-116">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="54d35-117">Il codice seguente è equivalente al codice precedente, ma il modulo è una dichiarazione di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="54d35-117">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="54d35-118">In tal caso, lo spazio dei nomi deve essere visualizzato nella riga a sé stante.</span><span class="sxs-lookup"><span data-stu-id="54d35-118">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="54d35-119">Se nello stesso file in uno o più spazi dei nomi è necessaria più di un modulo, è necessario usare le dichiarazioni di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="54d35-119">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="54d35-120">Quando si usano le dichiarazioni di modulo locale, è possibile usare lo spazio dei nomi qualificato nelle dichiarazioni di modulo.</span><span class="sxs-lookup"><span data-stu-id="54d35-120">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="54d35-121">Il codice seguente illustra un file con una dichiarazione dello spazio dei nomi e due dichiarazioni di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="54d35-121">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="54d35-122">In questo caso, i moduli sono contenuti direttamente nello spazio dei nomi; non è disponibile alcun modulo creato in modo implicito con lo stesso nome del file.</span><span class="sxs-lookup"><span data-stu-id="54d35-122">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="54d35-123">Qualsiasi altro codice nel file, ad esempio un `do` binding, è nello spazio dei nomi, ma non in moduli interni, pertanto è necessario qualificare i membri di modulo `widgetFunction` usando il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="54d35-123">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="54d35-124">L'output di questo esempio è come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="54d35-124">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="54d35-125">Per altre informazioni, vedere [moduli](modules.md).</span><span class="sxs-lookup"><span data-stu-id="54d35-125">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="54d35-126">Spazi dei nomi annidati</span><span class="sxs-lookup"><span data-stu-id="54d35-126">Nested Namespaces</span></span>

<span data-ttu-id="54d35-127">Quando si crea uno spazio dei nomi annidato, è necessario specificarla.</span><span class="sxs-lookup"><span data-stu-id="54d35-127">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="54d35-128">In caso contrario, si crea un nuovo spazio dei nomi di primo livello.</span><span class="sxs-lookup"><span data-stu-id="54d35-128">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="54d35-129">Rientro viene ignorato nelle dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-129">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="54d35-130">Nell'esempio seguente viene illustrato come dichiarare uno spazio dei nomi annidato.</span><span class="sxs-lookup"><span data-stu-id="54d35-130">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="54d35-131">Spazi dei nomi nel file e assembly</span><span class="sxs-lookup"><span data-stu-id="54d35-131">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="54d35-132">Gli spazi dei nomi possono estendersi su più file in una compilazione o di singolo progetto.</span><span class="sxs-lookup"><span data-stu-id="54d35-132">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="54d35-133">Il termine *frammento dello spazio dei nomi* descrive la parte di uno spazio dei nomi che è incluso in un unico file.</span><span class="sxs-lookup"><span data-stu-id="54d35-133">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="54d35-134">Gli spazi dei nomi può anche estendersi su più assembly.</span><span class="sxs-lookup"><span data-stu-id="54d35-134">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="54d35-135">Ad esempio, il `System` dello spazio dei nomi include l'intero .NET Framework, si estende su molti assembly che contiene molti spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="54d35-135">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="54d35-136">Global Namespace</span><span class="sxs-lookup"><span data-stu-id="54d35-136">Global Namespace</span></span>

<span data-ttu-id="54d35-137">Lo spazio dei nomi predefiniti `global` per inserire nomi nello spazio dei nomi di livello superiore di .NET.</span><span class="sxs-lookup"><span data-stu-id="54d35-137">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="54d35-138">È possibile inoltre utilizzare globali fanno riferimento a spazio dei nomi principale di .NET, ad esempio, per risolvere i conflitti di nome con altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-138">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="54d35-139">Spazi dei nomi ricorsiva</span><span class="sxs-lookup"><span data-stu-id="54d35-139">Recursive namespaces</span></span>

<span data-ttu-id="54d35-140">F# 4.1 introduce la nozione di spazi dei nomi che consentono di tutto il codice indipendente si escludono a vicenda sono ricorsivi.</span><span class="sxs-lookup"><span data-stu-id="54d35-140">F# 4.1 introduces the notion of namespaces which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="54d35-141">Questa operazione viene eseguita tramite `namespace rec`.</span><span class="sxs-lookup"><span data-stu-id="54d35-141">This is done via `namespace rec`.</span></span>  <span data-ttu-id="54d35-142">Uso di `namespace rec` possibile tentare di risolvere alcune aree problematiche in cui non riesca a scrivere il codice si escludono a vicenda referenziali tra i tipi e i moduli.</span><span class="sxs-lookup"><span data-stu-id="54d35-142">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="54d35-143">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="54d35-143">The following is an example of this:</span></span>

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

<span data-ttu-id="54d35-144">Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` entrambe fanno riferimento reciproco.</span><span class="sxs-lookup"><span data-stu-id="54d35-144">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="54d35-145">Inoltre, il modulo `BananaHelpers` e la classe `Banana` riferimento anche a altro.</span><span class="sxs-lookup"><span data-stu-id="54d35-145">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="54d35-146">Ciò non sarebbe possibile esprimere in F# se sono stati rimossi i `rec` parola chiave dal `MutualReferences` dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="54d35-146">This would not be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="54d35-147">Questa funzionalità è disponibile anche per primo livello [moduli](modules.md) in F# 4.1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="54d35-147">This feature is also available for top-level [Modules](modules.md) in F# 4.1 or higher.</span></span>

## <a name="see-also"></a><span data-ttu-id="54d35-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54d35-148">See also</span></span>

- [<span data-ttu-id="54d35-149">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="54d35-149">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="54d35-150">Moduli</span><span class="sxs-lookup"><span data-stu-id="54d35-150">Modules</span></span>](modules.md)
- [<span data-ttu-id="54d35-151">1009-F# RFC FS - Consenti moduli e tipi referenziali si escludono a vicenda su ambiti più ampi all'interno dei file</span><span class="sxs-lookup"><span data-stu-id="54d35-151">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
