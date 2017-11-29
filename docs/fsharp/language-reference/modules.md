---
title: Moduli (F#)
description: "Informazioni su come un modulo F # è un raggruppamento di codice F #, ad esempio i valori e tipi di valori di funzione, in un programma F #."
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 46de2d18-da51-40fa-a262-92edecada79d
ms.openlocfilehash: 89401c1f889be6c5585a302e3a7ac62478573b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="modules"></a><span data-ttu-id="7c399-104">Moduli</span><span class="sxs-lookup"><span data-stu-id="7c399-104">Modules</span></span>

<span data-ttu-id="7c399-105">Nel contesto del linguaggio F #, un *modulo* è un raggruppamento di codice F #, ad esempio i valori e tipi di valori di funzione, in un programma F #.</span><span class="sxs-lookup"><span data-stu-id="7c399-105">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="7c399-106">Il codice di raggruppamento nei moduli consente di tenere insieme il codice correlato e consente di evitare conflitti di nome nel programma.</span><span class="sxs-lookup"><span data-stu-id="7c399-106">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c399-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c399-107">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="7c399-108">Note</span><span class="sxs-lookup"><span data-stu-id="7c399-108">Remarks</span></span>
<span data-ttu-id="7c399-109">Un modulo F # è un raggruppamento di costrutti di codice F #, ad esempio tipi, i valori, valori di funzione e codice `do` associazioni.</span><span class="sxs-lookup"><span data-stu-id="7c399-109">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="7c399-110">È implementato come una classe di common language runtime (CLR) che include solo i membri statici.</span><span class="sxs-lookup"><span data-stu-id="7c399-110">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="7c399-111">Esistono due tipi di dichiarazioni di modulo, a seconda se l'intero file è incluso nel modulo: una dichiarazione di modulo di primo livello e una dichiarazione di modulo locale.</span><span class="sxs-lookup"><span data-stu-id="7c399-111">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="7c399-112">Una dichiarazione di modulo di primo livello include l'intero file nel modulo.</span><span class="sxs-lookup"><span data-stu-id="7c399-112">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="7c399-113">Una dichiarazione di modulo di primo livello può apparire solo come prima dichiarazione in un file.</span><span class="sxs-lookup"><span data-stu-id="7c399-113">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="7c399-114">Nella sintassi per la dichiarazione di modulo di primo livello, facoltativo *nomi qualificati* è la sequenza di nomi annidati che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="7c399-114">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="7c399-115">Lo spazio dei nomi completo non deve essere dichiarato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7c399-115">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="7c399-116">Non si dispone per il rientro delle dichiarazioni in un modulo di primo livello.</span><span class="sxs-lookup"><span data-stu-id="7c399-116">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="7c399-117">È necessario impostare un rientro tutte le dichiarazioni nei moduli locali.</span><span class="sxs-lookup"><span data-stu-id="7c399-117">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="7c399-118">In una dichiarazione di modulo locale, solo le dichiarazioni sono rientrate sotto tale dichiarazione di modulo fanno parte del modulo.</span><span class="sxs-lookup"><span data-stu-id="7c399-118">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="7c399-119">Se un file di codice non inizia con una dichiarazione di modulo di primo livello o una dichiarazione dello spazio dei nomi, l'intero contenuto del file, compresi eventuali moduli locali, diventa parte di un modulo di primo livello creata in modo implicito con lo stesso nome del file, senza l'estensione, con la prima lettera convertita in caratteri maiuscoli.</span><span class="sxs-lookup"><span data-stu-id="7c399-119">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="7c399-120">Ad esempio, si consideri il seguente file.</span><span class="sxs-lookup"><span data-stu-id="7c399-120">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="7c399-121">Questo file verrà compilato come se fosse scritto in questo modo:</span><span class="sxs-lookup"><span data-stu-id="7c399-121">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="7c399-122">Se si dispone di più moduli in un file, è necessario utilizzare una dichiarazione di modulo locale per ogni modulo.</span><span class="sxs-lookup"><span data-stu-id="7c399-122">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="7c399-123">Se viene dichiarato uno spazio dei nomi che lo contiene, questi moduli fanno parte dello spazio dei nomi che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="7c399-123">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="7c399-124">Se non è dichiarato uno spazio dei nomi che lo contiene, i moduli diventano parte del modulo di primo livello creata in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="7c399-124">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="7c399-125">Esempio di codice seguente viene illustrato un file di codice che contiene più moduli.</span><span class="sxs-lookup"><span data-stu-id="7c399-125">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="7c399-126">Il compilatore crea in modo implicito un modulo di primo livello denominato `Multiplemodules`, e `MyModule1` e `MyModule2` sono annidate in tale modulo di primo livello.</span><span class="sxs-lookup"><span data-stu-id="7c399-126">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="7c399-127">Se si dispone di più file in un progetto o in un'unica compilazione o se si compila una libreria, è necessario includere una dichiarazione dello spazio dei nomi o modulo nella parte superiore del file.</span><span class="sxs-lookup"><span data-stu-id="7c399-127">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="7c399-128">Il compilatore F # determina solo un nome di modulo in modo implicito quando è presente un solo file in una riga di comando di compilazione o di progetto e si sta creando un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7c399-128">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="7c399-129">Il *modificatore di accessibilità* può essere uno dei seguenti: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="7c399-129">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="7c399-130">Per altre informazioni, vedere [Controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="7c399-130">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="7c399-131">L'impostazione predefinita è public.</span><span class="sxs-lookup"><span data-stu-id="7c399-131">The default is public.</span></span>


## <a name="referencing-code-in-modules"></a><span data-ttu-id="7c399-132">Riferimenti al codice nei moduli</span><span class="sxs-lookup"><span data-stu-id="7c399-132">Referencing Code in Modules</span></span>
<span data-ttu-id="7c399-133">Quando si fa riferimento a funzioni, tipi e valori da un altro modulo, è necessario utilizzare un nome completo o aprire il modulo.</span><span class="sxs-lookup"><span data-stu-id="7c399-133">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="7c399-134">Se si utilizza un nome completo, è necessario specificare gli spazi dei nomi, il modulo e l'identificatore per l'elemento del programma desiderato.</span><span class="sxs-lookup"><span data-stu-id="7c399-134">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="7c399-135">Separare ogni parte del percorso completo con un punto (.), come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7c399-135">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="7c399-136">È possibile aprire il modulo o uno o più degli spazi dei nomi per semplificare il codice.</span><span class="sxs-lookup"><span data-stu-id="7c399-136">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="7c399-137">Per ulteriori informazioni sull'apertura di spazi dei nomi e i moduli, vedere [dichiarazioni di importazione: il `open` parola chiave](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="7c399-137">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="7c399-138">Esempio di codice seguente viene illustrato un modulo di primo livello che contiene tutto il codice fino alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="7c399-138">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="7c399-139">Per utilizzare questo codice da un altro file nello stesso progetto, è possibile utilizzare nomi completi o si apre il modulo prima di utilizzare le funzioni, come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7c399-139">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="7c399-140">Moduli annidati</span><span class="sxs-lookup"><span data-stu-id="7c399-140">Nested Modules</span></span>
<span data-ttu-id="7c399-141">I moduli possono essere annidati.</span><span class="sxs-lookup"><span data-stu-id="7c399-141">Modules can be nested.</span></span> <span data-ttu-id="7c399-142">Moduli interni devono essere rientrati fino alle dichiarazioni di modulo esterno per indicare che sono moduli interni, non nuovi moduli.</span><span class="sxs-lookup"><span data-stu-id="7c399-142">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="7c399-143">Ad esempio, confrontare i due esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="7c399-143">For example, compare the following two examples.</span></span> <span data-ttu-id="7c399-144">Modulo `Z` è un modulo interno nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7c399-144">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="7c399-145">Ma modulo `Z` è di pari livello al modulo `Y` nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7c399-145">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="7c399-146">Modulo `Z` è inoltre un modulo di elemento di pari livello nel codice seguente, in quanto il rientro non concerne le altre dichiarazioni nel modulo `Y`.</span><span class="sxs-lookup"><span data-stu-id="7c399-146">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="7c399-147">Infine, se il modulo esterno non include dichiarazioni ed è seguito immediatamente da un'altra dichiarazione di modulo, si presuppone che la nuova dichiarazione di modulo è un modulo interno, ma il compilatore visualizzerà un avviso se la seconda definizione di modulo non viene rientrata farther più di primo.</span><span class="sxs-lookup"><span data-stu-id="7c399-147">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="7c399-148">Per eliminare l'avviso, impostare un rientro il modulo interno.</span><span class="sxs-lookup"><span data-stu-id="7c399-148">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="7c399-149">Se si desidera che tutto il codice in un file in un singolo modulo esterno e si desidera moduli interni, il modulo esterno non richiede il segno di uguale e le dichiarazioni, incluse tutte le dichiarazioni di modulo interno, che entreranno nel modulo esterno non è necessario impostare un rientro.</span><span class="sxs-lookup"><span data-stu-id="7c399-149">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="7c399-150">Le dichiarazioni all'interno delle dichiarazioni di moduli interni deve essere rientrato.</span><span class="sxs-lookup"><span data-stu-id="7c399-150">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="7c399-151">Il codice seguente è illustrata questa situazione.</span><span class="sxs-lookup"><span data-stu-id="7c399-151">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="module-rec-allowing-mutual-recursive-code-at-the-module-level"></a><span data-ttu-id="7c399-152">Modulo `rec`: consente al codice ricorsiva reciproca a livello di modulo</span><span class="sxs-lookup"><span data-stu-id="7c399-152">Module `rec`: allowing mutual recursive code at the module level</span></span>

<span data-ttu-id="7c399-153">F # 4.1 introduce la nozione di moduli che consentono di tutto il codice indipendente reciprocamente sono ricorsivi.</span><span class="sxs-lookup"><span data-stu-id="7c399-153">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="7c399-154">Questa operazione viene eseguita tramite `module rec`.</span><span class="sxs-lookup"><span data-stu-id="7c399-154">This is done via `module rec`.</span></span>  <span data-ttu-id="7c399-155">Utilizzo di `module rec` possibile tentare di risolvere alcune difficoltà in non è in grado di scrivere codice reciprocamente referenziale tra i tipi e i moduli.</span><span class="sxs-lookup"><span data-stu-id="7c399-155">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="7c399-156">Di seguito è riportato un esempio di questo oggetto:</span><span class="sxs-lookup"><span data-stu-id="7c399-156">The following is an example of this:</span></span>

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

    module private BananaHelpers =
        let peel (b : Banana) =
            let flip banana =
                match banana.Orientation with
                | Up -> 
                    banana.Orientation <- Down
                    banana
                | Down -> banana

            let peelSides banana =
                for side in banana.Sides do
                    if side = Unpeeled then
                        side <- Peeled

            match b.Orientation with
            | Up ->   b |> flip |> peelSides
            | Down -> b |> peelSides
```

<span data-ttu-id="7c399-157">Si noti che l'eccezione `DontSqueezeTheBananaException` e la classe `Banana` fanno riferimento a altro.</span><span class="sxs-lookup"><span data-stu-id="7c399-157">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="7c399-158">Inoltre, il modulo `BananaHelpers` e la classe `Banana` anche fare riferimento a altro.</span><span class="sxs-lookup"><span data-stu-id="7c399-158">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="7c399-159">Ciò non sarebbe possibile esprimere in F #, se è stato rimosso il `rec` (parola chiave) dal `RecursiveModule` modulo.</span><span class="sxs-lookup"><span data-stu-id="7c399-159">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="7c399-160">Questa funzionalità è anche possibile in [gli spazi dei nomi](namespaces.md) con F # 4.1.</span><span class="sxs-lookup"><span data-stu-id="7c399-160">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c399-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c399-161">See Also</span></span>

<span data-ttu-id="7c399-162">[Riferimenti al linguaggio F #](index.md)
[gli spazi dei nomi](namespaces.md)
[F # RFC FS-1009 - Consenti moduli e tipi reciprocamente referenziali su maggiori ambiti all'interno dei file](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span><span class="sxs-lookup"><span data-stu-id="7c399-162">[F# Language Reference](index.md)
[Namespaces](namespaces.md)
[F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span></span>
