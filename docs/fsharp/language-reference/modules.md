---
title: Moduli
description: Informazioni su come F# un modulo è un raggruppamento di F# codice, ad esempio valori, tipi e valori di funzione, in un F# programma.
ms.date: 04/24/2017
ms.openlocfilehash: fbde0c8b001d88614ba2de49c4aa7bfa098c6945
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425062"
---
# <a name="modules"></a><span data-ttu-id="6fd87-103">Moduli</span><span class="sxs-lookup"><span data-stu-id="6fd87-103">Modules</span></span>

<span data-ttu-id="6fd87-104">Nel contesto della F# lingua, un *modulo* è un raggruppamento di F# codice, ad esempio valori, tipi e valori di funzione, in un F# programma.</span><span class="sxs-lookup"><span data-stu-id="6fd87-104">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="6fd87-105">Il codice di raggruppamento nei moduli consente di tenere insieme il codice correlato e consente di evitare conflitti di nome nel programma.</span><span class="sxs-lookup"><span data-stu-id="6fd87-105">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="6fd87-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fd87-106">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="6fd87-107">Note</span><span class="sxs-lookup"><span data-stu-id="6fd87-107">Remarks</span></span>

<span data-ttu-id="6fd87-108">Un F# modulo è un raggruppamento di costrutti di F# codice, ad esempio tipi, valori, valori di funzione e codice nelle associazioni `do`.</span><span class="sxs-lookup"><span data-stu-id="6fd87-108">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="6fd87-109">Viene implementato come una classe Common Language Runtime (CLR) che dispone solo di membri statici.</span><span class="sxs-lookup"><span data-stu-id="6fd87-109">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="6fd87-110">Esistono due tipi di dichiarazioni di modulo, a seconda che l'intero file sia incluso nel modulo: una dichiarazione di modulo di primo livello e una dichiarazione di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="6fd87-110">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="6fd87-111">Una dichiarazione di modulo di primo livello include l'intero file nel modulo.</span><span class="sxs-lookup"><span data-stu-id="6fd87-111">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="6fd87-112">Una dichiarazione di modulo di primo livello può essere visualizzata solo come prima dichiarazione in un file.</span><span class="sxs-lookup"><span data-stu-id="6fd87-112">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="6fd87-113">Nella sintassi per la dichiarazione di modulo di primo livello, lo *spazio dei nomi Qualified* facoltativo è la sequenza dei nomi di spazio dei nomi annidati che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="6fd87-113">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="6fd87-114">Non è necessario dichiarare in precedenza lo spazio dei nomi qualificato.</span><span class="sxs-lookup"><span data-stu-id="6fd87-114">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="6fd87-115">Non è necessario rientrare nelle dichiarazioni in un modulo di primo livello.</span><span class="sxs-lookup"><span data-stu-id="6fd87-115">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="6fd87-116">È necessario rientrare in tutte le dichiarazioni nei moduli locali.</span><span class="sxs-lookup"><span data-stu-id="6fd87-116">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="6fd87-117">In una dichiarazione di modulo locale, solo le dichiarazioni rientrate sotto tale dichiarazione del modulo fanno parte del modulo.</span><span class="sxs-lookup"><span data-stu-id="6fd87-117">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="6fd87-118">Se un file di codice non inizia con una dichiarazione di modulo di primo livello o con una dichiarazione dello spazio dei nomi, l'intero contenuto del file, inclusi i moduli locali, diventa parte di un modulo di primo livello creato in modo implicito con lo stesso nome del file, senza l'estensione, con la prima lettera convertita in maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="6fd87-118">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="6fd87-119">Si consideri, ad esempio, il file seguente.</span><span class="sxs-lookup"><span data-stu-id="6fd87-119">For example, consider the following file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="6fd87-120">Questo file verrà compilato come se fosse stato scritto in questo modo:</span><span class="sxs-lookup"><span data-stu-id="6fd87-120">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="6fd87-121">Se sono presenti più moduli in un file, è necessario usare una dichiarazione di modulo locale per ogni modulo.</span><span class="sxs-lookup"><span data-stu-id="6fd87-121">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="6fd87-122">Se viene dichiarato uno spazio dei nomi che lo contiene, questi moduli fanno parte dello spazio dei nomi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="6fd87-122">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="6fd87-123">Se uno spazio dei nomi che lo contiene non è dichiarato, i moduli diventano parte del modulo di primo livello creato in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="6fd87-123">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="6fd87-124">Nell'esempio di codice riportato di seguito viene illustrato un file di codice contenente più moduli.</span><span class="sxs-lookup"><span data-stu-id="6fd87-124">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="6fd87-125">Il compilatore crea in modo implicito un modulo di primo livello denominato `Multiplemodules`e `MyModule1` e `MyModule2` sono annidati in tale modulo di primo livello.</span><span class="sxs-lookup"><span data-stu-id="6fd87-125">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="6fd87-126">Se si dispone di più file in un progetto o in una singola compilazione o se si compila una libreria, è necessario includere una dichiarazione dello spazio dei nomi o una dichiarazione di modulo nella parte superiore del file.</span><span class="sxs-lookup"><span data-stu-id="6fd87-126">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="6fd87-127">Il F# compilatore determina il nome del modulo in modo implicito solo quando è presente un solo file in un progetto o in una riga di comando di compilazione e si crea un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6fd87-127">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="6fd87-128">Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="6fd87-128">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="6fd87-129">Per altre informazioni, vedere [Controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="6fd87-129">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="6fd87-130">L'impostazione predefinita è public.</span><span class="sxs-lookup"><span data-stu-id="6fd87-130">The default is public.</span></span>

## <a name="referencing-code-in-modules"></a><span data-ttu-id="6fd87-131">Riferimento al codice nei moduli</span><span class="sxs-lookup"><span data-stu-id="6fd87-131">Referencing Code in Modules</span></span>

<span data-ttu-id="6fd87-132">Quando si fa riferimento a funzioni, tipi e valori di un altro modulo, è necessario usare un nome completo o aprire il modulo.</span><span class="sxs-lookup"><span data-stu-id="6fd87-132">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="6fd87-133">Se si usa un nome completo, è necessario specificare gli spazi dei nomi, il modulo e l'identificatore per l'elemento del programma desiderato.</span><span class="sxs-lookup"><span data-stu-id="6fd87-133">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="6fd87-134">Si separa ogni parte del percorso completo con un punto (.), come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6fd87-134">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="6fd87-135">Per semplificare il codice, è possibile aprire il modulo o uno o più spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6fd87-135">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="6fd87-136">Per ulteriori informazioni sull'apertura di spazi dei nomi e moduli, vedere [dichiarazioni di importazione: parola chiave `open`](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="6fd87-136">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="6fd87-137">L'esempio di codice seguente mostra un modulo di primo livello che contiene tutto il codice fino alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="6fd87-137">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="6fd87-138">Per usare questo codice da un altro file nello stesso progetto, è possibile usare nomi completi o aprire il modulo prima di usare le funzioni, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="6fd87-138">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="6fd87-139">Moduli annidati</span><span class="sxs-lookup"><span data-stu-id="6fd87-139">Nested Modules</span></span>

<span data-ttu-id="6fd87-140">I moduli possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="6fd87-140">Modules can be nested.</span></span> <span data-ttu-id="6fd87-141">Per indicare che si tratta di moduli interni e non nuovi moduli, è necessario rientrare nei moduli interni per quanto riguarda le dichiarazioni del modulo esterno.</span><span class="sxs-lookup"><span data-stu-id="6fd87-141">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="6fd87-142">Confrontare, ad esempio, i due esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="6fd87-142">For example, compare the following two examples.</span></span> <span data-ttu-id="6fd87-143">Module `Z` è un modulo interno nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6fd87-143">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="6fd87-144">Il modulo `Z` tuttavia è un elemento di pari livello per il modulo `Y` nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6fd87-144">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="6fd87-145">Module `Z` è anche un modulo di pari livello nel codice seguente, perché non è rientrato per quanto riguarda le altre dichiarazioni nell'`Y`del modulo.</span><span class="sxs-lookup"><span data-stu-id="6fd87-145">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="6fd87-146">Infine, se il modulo esterno non ha dichiarazioni e viene seguito immediatamente da un'altra dichiarazione di modulo, si presuppone che la nuova dichiarazione del modulo sia un modulo interno, ma il compilatore avvisa l'utente se la definizione del secondo modulo non è rientrata oltre prima.</span><span class="sxs-lookup"><span data-stu-id="6fd87-146">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="6fd87-147">Per eliminare l'avviso, rientrare nel modulo interno.</span><span class="sxs-lookup"><span data-stu-id="6fd87-147">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="6fd87-148">Se si vuole che tutto il codice in un file si trovi in un unico modulo esterno e si desideri che i moduli interni non richiedano il segno di uguale e le dichiarazioni, incluse le dichiarazioni dei moduli interni, che andranno nel modulo esterno non devono essere rientrate.</span><span class="sxs-lookup"><span data-stu-id="6fd87-148">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="6fd87-149">È necessario rientrare le dichiarazioni all'interno delle dichiarazioni dei moduli interni.</span><span class="sxs-lookup"><span data-stu-id="6fd87-149">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="6fd87-150">Il codice seguente illustra questo caso.</span><span class="sxs-lookup"><span data-stu-id="6fd87-150">The following code shows this case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="recursive-modules"></a><span data-ttu-id="6fd87-151">Moduli ricorsivi</span><span class="sxs-lookup"><span data-stu-id="6fd87-151">Recursive modules</span></span>

<span data-ttu-id="6fd87-152">F#4,1 introduce la nozione di moduli che consentono a tutto il codice contenuto di essere ricorsivo a vicenda.</span><span class="sxs-lookup"><span data-stu-id="6fd87-152">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="6fd87-153">Questa operazione viene eseguita tramite `module rec`.</span><span class="sxs-lookup"><span data-stu-id="6fd87-153">This is done via `module rec`.</span></span>  <span data-ttu-id="6fd87-154">L'uso di `module rec` può alleviare alcune problematiche nella mancata possibilità di scrivere codice reciprocamente referenziale tra tipi e moduli.</span><span class="sxs-lookup"><span data-stu-id="6fd87-154">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="6fd87-155">Di seguito è riportato un esempio:</span><span class="sxs-lookup"><span data-stu-id="6fd87-155">The following is an example of this:</span></span>

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

<span data-ttu-id="6fd87-156">Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` entrambi fanno riferimento l'uno all'altro.</span><span class="sxs-lookup"><span data-stu-id="6fd87-156">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="6fd87-157">Inoltre, il modulo `BananaHelpers` e la classe `Banana` fanno riferimento l'uno all'altro.</span><span class="sxs-lookup"><span data-stu-id="6fd87-157">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="6fd87-158">Questa operazione non può essere espressa in F# se è stata rimossa la parola chiave `rec` dal modulo di `RecursiveModule`.</span><span class="sxs-lookup"><span data-stu-id="6fd87-158">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="6fd87-159">Questa funzionalità è inoltre possibile negli [spazi dei nomi](namespaces.md) con F# 4,1.</span><span class="sxs-lookup"><span data-stu-id="6fd87-159">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fd87-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fd87-160">See also</span></span>

- [<span data-ttu-id="6fd87-161">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="6fd87-161">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6fd87-162">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="6fd87-162">Namespaces</span></span>](namespaces.md)
- [<span data-ttu-id="6fd87-163">F#RFC FS-1009-Consenti i tipi e i moduli referenziali reciprocamente su ambiti più ampi nei file</span><span class="sxs-lookup"><span data-stu-id="6fd87-163">F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files</span></span>](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
