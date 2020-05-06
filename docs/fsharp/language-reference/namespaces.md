---
title: Spazi dei nomi
description: 'Informazioni su come uno spazio dei nomi F # consente di organizzare il codice in aree di funzionalità correlate consentendo di alleghiare un nome a un raggruppamento di elementi di programma.'
ms.date: 12/08/2018
ms.openlocfilehash: bf71843349434a1ea91c58dbc0477373dbb0c449
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796132"
---
# <a name="namespaces"></a><span data-ttu-id="5c13c-103">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="5c13c-103">Namespaces</span></span>

<span data-ttu-id="5c13c-104">Uno spazio dei nomi consente di organizzare il codice in aree della funzionalità correlata consentendo di alleghiare un nome a un raggruppamento di elementi di programma F #.</span><span class="sxs-lookup"><span data-stu-id="5c13c-104">A namespace lets you organize code into areas of related functionality by enabling you to attach a name to a grouping of F# program elements.</span></span> <span data-ttu-id="5c13c-105">Gli spazi dei nomi sono in genere elementi di primo livello nei file F #.</span><span class="sxs-lookup"><span data-stu-id="5c13c-105">Namespaces are typically top-level elements in F# files.</span></span>

## <a name="syntax"></a><span data-ttu-id="5c13c-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c13c-106">Syntax</span></span>

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a><span data-ttu-id="5c13c-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5c13c-107">Remarks</span></span>

<span data-ttu-id="5c13c-108">Se si desidera inserire il codice in uno spazio dei nomi, la prima dichiarazione nel file deve dichiarare lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-108">If you want to put code in a namespace, the first declaration in the file must declare the namespace.</span></span> <span data-ttu-id="5c13c-109">Il contenuto dell'intero file diventa quindi parte dello spazio dei nomi, purché nel file non esistano altre dichiarazioni di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-109">The contents of the entire file then become part of the namespace, provided no other namespaces declaration exists further in the file.</span></span> <span data-ttu-id="5c13c-110">In tal caso, tutto il codice fino alla successiva dichiarazione dello spazio dei nomi viene considerato all'interno del primo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-110">If that is the case, then all code up until the next namespace declaration is considered to be within the first namespace.</span></span>

<span data-ttu-id="5c13c-111">Gli spazi dei nomi non possono contenere direttamente valori e funzioni.</span><span class="sxs-lookup"><span data-stu-id="5c13c-111">Namespaces cannot directly contain values and functions.</span></span> <span data-ttu-id="5c13c-112">Al contrario, i valori e le funzioni devono essere inclusi nei moduli e i moduli sono inclusi negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-112">Instead, values and functions must be included in modules, and modules are included in namespaces.</span></span> <span data-ttu-id="5c13c-113">Gli spazi dei nomi possono contenere tipi, moduli.</span><span class="sxs-lookup"><span data-stu-id="5c13c-113">Namespaces can contain types, modules.</span></span>

<span data-ttu-id="5c13c-114">I commenti in formato documentazione XML possono essere dichiarati sopra uno spazio dei nomi, ma sono ignorati.</span><span class="sxs-lookup"><span data-stu-id="5c13c-114">XML doc comments can be declared above a namespace, but they're ignored.</span></span> <span data-ttu-id="5c13c-115">Le direttive del compilatore possono anche essere dichiarate sopra uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-115">Compiler directives can also be declared above a namespace.</span></span>

<span data-ttu-id="5c13c-116">Gli spazi dei nomi possono essere dichiarati in modo esplicito con la parola chiave namespace o in modo implicito quando si dichiara un modulo.</span><span class="sxs-lookup"><span data-stu-id="5c13c-116">Namespaces can be declared explicitly with the namespace keyword, or implicitly when declaring a module.</span></span> <span data-ttu-id="5c13c-117">Per dichiarare uno spazio dei nomi in modo esplicito, usare la parola chiave namespace seguita dal nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-117">To declare a namespace explicitly, use the namespace keyword followed by the namespace name.</span></span> <span data-ttu-id="5c13c-118">Nell'esempio seguente viene illustrato un file di codice che dichiara uno `Widgets` spazio dei nomi con un tipo e un modulo inclusi nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-118">The following example shows a code file that declares a namespace `Widgets` with a type and a module included in that namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

<span data-ttu-id="5c13c-119">Se l'intero contenuto del file si trova in un modulo, è anche possibile dichiarare gli spazi dei nomi in modo implicito usando la `module` parola chiave e specificando il nuovo nome dello spazio dei nomi nel nome completo del modulo.</span><span class="sxs-lookup"><span data-stu-id="5c13c-119">If the entire contents of the file are in one module, you can also declare namespaces implicitly by using the `module` keyword and providing the new namespace name in the fully qualified module name.</span></span> <span data-ttu-id="5c13c-120">Nell'esempio seguente viene illustrato un file di codice che dichiara uno `Widgets` spazio dei nomi `WidgetsModule`e un modulo che contiene una funzione.</span><span class="sxs-lookup"><span data-stu-id="5c13c-120">The following example shows a code file that declares a namespace `Widgets` and a module `WidgetsModule`, which contains a function.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

<span data-ttu-id="5c13c-121">Il codice seguente è equivalente a quello precedente, ma il modulo è una dichiarazione di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="5c13c-121">The following code is equivalent to the preceding code, but the module is a local module declaration.</span></span> <span data-ttu-id="5c13c-122">In tal caso, lo spazio dei nomi deve essere visualizzato su una riga a parte.</span><span class="sxs-lookup"><span data-stu-id="5c13c-122">In that case, the namespace must appear on its own line.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/namespaces/snippet6402.fs)]

<span data-ttu-id="5c13c-123">Se è necessario più di un modulo nello stesso file in uno o più spazi dei nomi, è necessario usare le dichiarazioni di modulo locali.</span><span class="sxs-lookup"><span data-stu-id="5c13c-123">If more than one module is required in the same file in one or more namespaces, you must use local module declarations.</span></span> <span data-ttu-id="5c13c-124">Quando si usano le dichiarazioni di modulo locali, non è possibile usare lo spazio dei nomi Qualified nelle dichiarazioni del modulo.</span><span class="sxs-lookup"><span data-stu-id="5c13c-124">When you use local module declarations, you cannot use the qualified namespace in the module declarations.</span></span> <span data-ttu-id="5c13c-125">Il codice seguente illustra un file con una dichiarazione dello spazio dei nomi e due dichiarazioni di modulo locali.</span><span class="sxs-lookup"><span data-stu-id="5c13c-125">The following code shows a file that has a namespace declaration and two local module declarations.</span></span> <span data-ttu-id="5c13c-126">In questo caso, i moduli sono contenuti direttamente nello spazio dei nomi; non esiste alcun modulo creato in modo implicito con lo stesso nome del file.</span><span class="sxs-lookup"><span data-stu-id="5c13c-126">In this case, the modules are contained directly in the namespace; there is no implicitly created module that has the same name as the file.</span></span> <span data-ttu-id="5c13c-127">Qualsiasi altro codice nel file, ad esempio un' `do` associazione, si trova nello spazio dei nomi ma non nei moduli interni, quindi è necessario qualificare il membro `widgetFunction` del modulo usando il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="5c13c-127">Any other code in the file, such as a `do` binding, is in the namespace but not in the inner modules, so you need to qualify the module member `widgetFunction` by using the module name.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

<span data-ttu-id="5c13c-128">L'output di questo esempio è il seguente.</span><span class="sxs-lookup"><span data-stu-id="5c13c-128">The output of this example is as follows.</span></span>

```fsharp
Module1 10 20
Module2 5 6
```

<span data-ttu-id="5c13c-129">Per ulteriori informazioni, vedere [moduli](modules.md).</span><span class="sxs-lookup"><span data-stu-id="5c13c-129">For more information, see [Modules](modules.md).</span></span>

## <a name="nested-namespaces"></a><span data-ttu-id="5c13c-130">Spazi dei nomi annidati</span><span class="sxs-lookup"><span data-stu-id="5c13c-130">Nested Namespaces</span></span>

<span data-ttu-id="5c13c-131">Quando si crea uno spazio dei nomi annidato, è necessario qualificarlo completamente.</span><span class="sxs-lookup"><span data-stu-id="5c13c-131">When you create a nested namespace, you must fully qualify it.</span></span> <span data-ttu-id="5c13c-132">In caso contrario, viene creato un nuovo spazio dei nomi di primo livello.</span><span class="sxs-lookup"><span data-stu-id="5c13c-132">Otherwise, you create a new top-level namespace.</span></span> <span data-ttu-id="5c13c-133">Il rientro viene ignorato nelle dichiarazioni dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-133">Indentation is ignored in namespace declarations.</span></span>

<span data-ttu-id="5c13c-134">Nell'esempio seguente viene illustrato come dichiarare uno spazio dei nomi annidato.</span><span class="sxs-lookup"><span data-stu-id="5c13c-134">The following example shows how to declare a nested namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a><span data-ttu-id="5c13c-135">Spazi dei nomi in file e assembly</span><span class="sxs-lookup"><span data-stu-id="5c13c-135">Namespaces in Files and Assemblies</span></span>

<span data-ttu-id="5c13c-136">Gli spazi dei nomi possono estendersi su più file in un singolo progetto o compilazione.</span><span class="sxs-lookup"><span data-stu-id="5c13c-136">Namespaces can span multiple files in a single project or compilation.</span></span> <span data-ttu-id="5c13c-137">Il termine *frammento spazio dei nomi* descrive la parte di uno spazio dei nomi incluso in un file.</span><span class="sxs-lookup"><span data-stu-id="5c13c-137">The term *namespace fragment* describes the part of a namespace that is included in one file.</span></span> <span data-ttu-id="5c13c-138">Gli spazi dei nomi possono anche estendersi su più assembly.</span><span class="sxs-lookup"><span data-stu-id="5c13c-138">Namespaces can also span multiple assemblies.</span></span> <span data-ttu-id="5c13c-139">Ad esempio, lo `System` spazio dei nomi include l'intero .NET Framework, che si estende su molti assembly e contiene molti spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="5c13c-139">For example, the `System` namespace includes the whole .NET Framework, which spans many assemblies and contains many nested namespaces.</span></span>

## <a name="global-namespace"></a><span data-ttu-id="5c13c-140">Spazio dei nomi globale</span><span class="sxs-lookup"><span data-stu-id="5c13c-140">Global Namespace</span></span>

<span data-ttu-id="5c13c-141">Usare lo spazio dei `global` nomi predefinito per inserire i nomi nello spazio dei nomi di primo livello .NET.</span><span class="sxs-lookup"><span data-stu-id="5c13c-141">You use the predefined namespace `global` to put names in the .NET top-level namespace.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

<span data-ttu-id="5c13c-142">È anche possibile usare Global per fare riferimento allo spazio dei nomi .NET di primo livello, ad esempio per risolvere i conflitti di nomi con altri spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-142">You can also use global to reference the top-level .NET namespace, for example, to resolve name conflicts with other namespaces.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a><span data-ttu-id="5c13c-143">Spazi dei nomi ricorsivi</span><span class="sxs-lookup"><span data-stu-id="5c13c-143">Recursive namespaces</span></span>

<span data-ttu-id="5c13c-144">Gli spazi dei nomi possono anche essere dichiarati come ricorsivi per consentire a tutto il codice contenuto di essere ricorsivo a vicenda.</span><span class="sxs-lookup"><span data-stu-id="5c13c-144">Namespaces can also be declared as recursive to allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="5c13c-145">Questa operazione viene eseguita `namespace rec`tramite.</span><span class="sxs-lookup"><span data-stu-id="5c13c-145">This is done via `namespace rec`.</span></span> <span data-ttu-id="5c13c-146">L'uso `namespace rec` di può alleviare alcune problematiche nella mancata possibilità di scrivere codice reciprocamente referenziale tra tipi e moduli.</span><span class="sxs-lookup"><span data-stu-id="5c13c-146">Use of `namespace rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span> <span data-ttu-id="5c13c-147">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="5c13c-147">The following is an example of this:</span></span>

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

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

<span data-ttu-id="5c13c-148">Si noti che l' `DontSqueezeTheBananaException` eccezione e la `Banana` classe fanno riferimento l'una all'altra.</span><span class="sxs-lookup"><span data-stu-id="5c13c-148">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="5c13c-149">Inoltre, il modulo `BananaHelpers` e la classe `Banana` fanno riferimento l'uno all'altro.</span><span class="sxs-lookup"><span data-stu-id="5c13c-149">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span> <span data-ttu-id="5c13c-150">Non sarebbe possibile esprimere in F # se la `rec` parola chiave è stata rimossa dallo `MutualReferences` spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5c13c-150">This wouldn't be possible to express in F# if you removed the `rec` keyword from the `MutualReferences` namespace.</span></span>

<span data-ttu-id="5c13c-151">Questa funzionalità è disponibile anche per i [moduli](modules.md)di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="5c13c-151">This feature is also available for top-level [Modules](modules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c13c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c13c-152">See also</span></span>

- [<span data-ttu-id="5c13c-153">Riferimenti per il linguaggio F #</span><span class="sxs-lookup"><span data-stu-id="5c13c-153">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="5c13c-154">Moduli</span><span class="sxs-lookup"><span data-stu-id="5c13c-154">Modules</span></span>](modules.md)
- [<span data-ttu-id="5c13c-155">F # RFC FS-1009-Consenti i tipi e i moduli referenziali reciprocamente su ambiti più ampi nei file</span><span class="sxs-lookup"><span data-stu-id="5c13c-155">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
