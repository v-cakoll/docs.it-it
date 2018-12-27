---
title: Moduli
description: Informazioni su come un F# modulo è un raggruppamento di F# codice, ad esempio i valori, tipi e valori di funzioni, in un F# programma.
ms.date: 04/24/2017
ms.openlocfilehash: 9e5bef4ffe3301a69bbe32483625652d988f8a35
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611113"
---
# <a name="modules"></a><span data-ttu-id="62886-103">Moduli</span><span class="sxs-lookup"><span data-stu-id="62886-103">Modules</span></span>

<span data-ttu-id="62886-104">Nel contesto del F# linguaggio, un *module* è un raggruppamento di F# codice, ad esempio i valori, tipi e valori di funzioni, in un F# programma.</span><span class="sxs-lookup"><span data-stu-id="62886-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="62886-105">Il codice di raggruppamento nei moduli consente di tenere insieme il codice correlato e consente di evitare conflitti di nome nel programma.</span><span class="sxs-lookup"><span data-stu-id="62886-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="62886-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62886-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="62886-107">Note</span><span class="sxs-lookup"><span data-stu-id="62886-107">Remarks</span></span>

<span data-ttu-id="62886-108">Un F# modulo è un raggruppamento di F# costruisce codice, ad esempio i tipi, i valori, valori di funzione e codice nel `do` associazioni.</span><span class="sxs-lookup"><span data-stu-id="62886-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="62886-109">Viene implementato come una classe common language runtime (CLR) che includa solo membri statici.</span><span class="sxs-lookup"><span data-stu-id="62886-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="62886-110">Esistono due tipi di dichiarazioni di modulo, a seconda del fatto che l'intero file è incluso nel modulo: una dichiarazione di modulo di primo livello e una dichiarazione di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="62886-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="62886-111">Una dichiarazione di modulo di livello principale include l'intero file nel modulo.</span><span class="sxs-lookup"><span data-stu-id="62886-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="62886-112">Una dichiarazione di modulo di primo livello può apparire solo come la prima dichiarazione in un file.</span><span class="sxs-lookup"><span data-stu-id="62886-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="62886-113">La sintassi per la dichiarazione di modulo di primo livello, l'opzione facoltativa *qualificato-spazio dei nomi* è la sequenza di nomi di spazio dei nomi annidato che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="62886-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="62886-114">Lo spazio dei nomi qualificato non deve essere dichiarato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="62886-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="62886-115">Non è necessario impostare un rientro delle dichiarazioni in un modulo di primo livello.</span><span class="sxs-lookup"><span data-stu-id="62886-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="62886-116">È necessario impostare un rientro a tutte le dichiarazioni nei moduli locale.</span><span class="sxs-lookup"><span data-stu-id="62886-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="62886-117">In una dichiarazione di modulo locale, solo le dichiarazioni vengono rientrate sotto tale dichiarazione di modulo fanno parte del modulo.</span><span class="sxs-lookup"><span data-stu-id="62886-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="62886-118">Se un file di codice non inizia con una dichiarazione di modulo di primo livello o una dichiarazione dello spazio dei nomi, l'intero contenuto del file, inclusi tutti i moduli locali, diventa parte di un modulo di primo livello creato in modo implicito con lo stesso nome del file, senza l'estensione, con la prima lettera convertita in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="62886-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="62886-119">Ad esempio, si consideri il seguente file.</span><span class="sxs-lookup"><span data-stu-id="62886-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="62886-120">Questo file potrebbe essere compilato come se fosse scritto in questo modo:</span><span class="sxs-lookup"><span data-stu-id="62886-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="62886-121">Se si dispone di più moduli in un file, è necessario usare una dichiarazione di modulo locale per ogni modulo.</span><span class="sxs-lookup"><span data-stu-id="62886-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="62886-122">Se viene dichiarato uno spazio dei nomi che lo contiene, questi moduli sono parte dello spazio dei nomi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="62886-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="62886-123">Se non viene dichiarato uno spazio dei nomi che lo contiene, i moduli diventano parte del modulo di primo livello creato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="62886-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="62886-124">Esempio di codice seguente illustra un file di codice che contiene più moduli.</span><span class="sxs-lookup"><span data-stu-id="62886-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="62886-125">Il compilatore crea in modo implicito un modulo di primo livello denominato `Multiplemodules`, e `MyModule1` e `MyModule2` sono annidate in ogni modulo di primo livello.</span><span class="sxs-lookup"><span data-stu-id="62886-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="62886-126">Se si hanno più file in un progetto o in un'unica compilazione o se si sta creando una libreria, è necessario includere una dichiarazione di modulo nella parte superiore del file o una dichiarazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="62886-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="62886-127">Il F# compilatore determina solo un nome di modulo in modo implicito quando è presente un solo file in una riga di comando di compilazione o di progetto e si sta creando un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="62886-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="62886-128">Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="62886-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="62886-129">Per altre informazioni, vedere [Controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="62886-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="62886-130">L'impostazione predefinita è public.</span><span class="sxs-lookup"><span data-stu-id="62886-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="62886-131">Riferimenti al codice nei moduli</span><span class="sxs-lookup"><span data-stu-id="62886-131">Referencing Code in Modules</span></span>

<span data-ttu-id="62886-132">Quando si fa riferimento a funzioni, tipi e valori da un altro modulo, è necessario usare un nome completo o aprire il modulo.</span><span class="sxs-lookup"><span data-stu-id="62886-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="62886-133">Se si usa un nome completo, è necessario specificare gli spazi dei nomi, il modulo e l'identificatore per l'elemento del programma desiderato.</span><span class="sxs-lookup"><span data-stu-id="62886-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="62886-134">È separare ogni parte del percorso completo con un punto (.), come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="62886-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="62886-135">È possibile aprire il modulo o uno o più degli spazi dei nomi per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="62886-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="62886-136">Per altre informazioni sull'apertura degli spazi dei nomi e i moduli, vedere [dichiarazioni di importazione: Il `open` parola chiave](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="62886-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="62886-137">Esempio di codice seguente mostra un modulo di primo livello che contiene tutto il codice fino alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="62886-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="62886-138">Per usare questo codice da un altro file nello stesso progetto, è possibile utilizzare nomi completi o si apre il modulo prima di usare le funzioni, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="62886-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="62886-139">Moduli annidati</span><span class="sxs-lookup"><span data-stu-id="62886-139">Nested Modules</span></span>

<span data-ttu-id="62886-140">I moduli possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="62886-140">Modules can be nested.</span></span> <span data-ttu-id="62886-141">Moduli interni devono essere applicato un rientro per quanto riguarda le dichiarazioni di modulo esterno per indicare che sono moduli interni, non nuovi moduli.</span><span class="sxs-lookup"><span data-stu-id="62886-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="62886-142">Ad esempio, confrontare i due esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="62886-142">For example, compare the following two examples.</span></span> <span data-ttu-id="62886-143">Modulo `Z` è un modulo interno nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="62886-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="62886-144">Ma modulo `Z` è di pari livello al modulo `Y` nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="62886-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="62886-145">Modulo `Z` è anche un modulo di pari livello nel codice seguente, in quanto non viene applicato un rientro per quanto riguarda le altre dichiarazioni di modulo `Y`.</span><span class="sxs-lookup"><span data-stu-id="62886-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="62886-146">Infine, se il modulo esterno non dispone di alcun dichiarazioni ed è seguito immediatamente da un'altra dichiarazione di modulo, la nuova dichiarazione di modulo viene considerato come un modulo interno, ma il compilatore avverte l'utente se la seconda definizione del modulo non verrà rientrata rispetto a farther il primo.</span><span class="sxs-lookup"><span data-stu-id="62886-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="62886-147">Per eliminare l'avviso, impostare un rientro del modulo interno.</span><span class="sxs-lookup"><span data-stu-id="62886-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="62886-148">Se si vuole che tutto il codice in un file in un singolo modulo esterno e si vuole moduli interni, il modulo esterno non richiede il segno di uguale e le dichiarazioni, incluse le dichiarazioni di modulo interno, che entreranno nel modulo esterno non sono necessario impostare un rientro.</span><span class="sxs-lookup"><span data-stu-id="62886-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="62886-149">Le dichiarazioni all'interno delle dichiarazioni di modulo interno deve essere rientrata.</span><span class="sxs-lookup"><span data-stu-id="62886-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="62886-150">Il codice seguente viene illustrato in questo caso.</span><span class="sxs-lookup"><span data-stu-id="62886-150">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="62886-151">Moduli ricorsiva</span><span class="sxs-lookup"><span data-stu-id="62886-151">Recursive modules</span></span>

<span data-ttu-id="62886-152">F#4.1 introduce la nozione di moduli che consentono di tutto il codice indipendente si escludono a vicenda sono ricorsivi.</span><span class="sxs-lookup"><span data-stu-id="62886-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="62886-153">Questa operazione viene eseguita tramite `module rec`.</span><span class="sxs-lookup"><span data-stu-id="62886-153">This is done via `module rec`.</span></span>  <span data-ttu-id="62886-154">Uso di `module rec` possibile tentare di risolvere alcune aree problematiche in cui non riesca a scrivere il codice si escludono a vicenda referenziali tra i tipi e i moduli.</span><span class="sxs-lookup"><span data-stu-id="62886-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="62886-155">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="62886-155">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
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

<span data-ttu-id="62886-156">Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` entrambe fanno riferimento reciproco.</span><span class="sxs-lookup"><span data-stu-id="62886-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="62886-157">Inoltre, il modulo `BananaHelpers` e la classe `Banana` riferimento anche a altro.</span><span class="sxs-lookup"><span data-stu-id="62886-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="62886-158">Ciò non sarebbe possibile esprimere F# se è stato rimosso il `rec` parola chiave dal `RecursiveModule` modulo.</span><span class="sxs-lookup"><span data-stu-id="62886-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="62886-159">Questa funzionalità è anche possibile nelle [spazi dei nomi](namespaces.md) con F# 4.1.</span><span class="sxs-lookup"><span data-stu-id="62886-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="62886-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62886-160">See also</span></span>

- [<span data-ttu-id="62886-161">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="62886-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="62886-162">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="62886-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="62886-163">F#RFC FS-1009 - Consenti moduli e tipi referenziali si escludono a vicenda su ambiti più ampi all'interno dei file</span><span class="sxs-lookup"><span data-stu-id="62886-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)