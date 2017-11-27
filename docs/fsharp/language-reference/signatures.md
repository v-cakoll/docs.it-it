---
title: Firme (F#)
description: 'Informazioni su come utilizzare un file di firma F # per contenere le informazioni sulle firme pubbliche di un set di F # elementi di programma, ad esempio moduli, tipi e spazi dei nomi.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 76c84a62-b2f6-44ec-8238-e687e2f7d18e
ms.openlocfilehash: d0f71c6472852268303a2d3af2e4b0a3c256704e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="signatures"></a><span data-ttu-id="d0d68-104">Firme</span><span class="sxs-lookup"><span data-stu-id="d0d68-104">Signatures</span></span>

<span data-ttu-id="d0d68-105">Un file della firma contiene informazioni sulle firme pubbliche di un set di elementi del programma F#, ad esempio i tipi, gli spazi dei nomi e i moduli.</span><span class="sxs-lookup"><span data-stu-id="d0d68-105">A signature file contains information about the public signatures of a set of F# program elements, such as types, namespaces, and modules.</span></span> <span data-ttu-id="d0d68-106">Può essere usato per specificare l'accessibilità di questi elementi del programma.</span><span class="sxs-lookup"><span data-stu-id="d0d68-106">It can be used to specify the accessibility of these program elements.</span></span>


## <a name="remarks"></a><span data-ttu-id="d0d68-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d0d68-107">Remarks</span></span>
<span data-ttu-id="d0d68-108">Per ogni file di codice F# è disponibile un *file della firma*, ossia un file con lo stesso nome del file di codice, ma con l'estensione fsi invece che fs.</span><span class="sxs-lookup"><span data-stu-id="d0d68-108">For each F# code file, you can have a *signature file*, which is a file that has the same name as the code file but with the extension .fsi instead of .fs.</span></span> <span data-ttu-id="d0d68-109">I file della firma possono essere aggiunti anche alla riga di comando di compilazione se si usa direttamente la riga di comando.</span><span class="sxs-lookup"><span data-stu-id="d0d68-109">Signature files can also be added to the compilation command-line if you are using the command line directly.</span></span> <span data-ttu-id="d0d68-110">Per distinguere tra file di codice e file della firma, a volte i file di codice vengono chiamati *file di implementazione*.</span><span class="sxs-lookup"><span data-stu-id="d0d68-110">To distinguish between code files and signature files, code files are sometimes referred to as *implementation files*.</span></span> <span data-ttu-id="d0d68-111">In un progetto il file della firma deve precedere il file di codice associato.</span><span class="sxs-lookup"><span data-stu-id="d0d68-111">In a project, the signature file should precede the associated code file.</span></span>

<span data-ttu-id="d0d68-112">Un file della firma descrive gli spazi dei nomi, i moduli, i tipi e i membri nel file di implementazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d0d68-112">A signature file describes the namespaces, modules, types, and members in the corresponding implementation file.</span></span> <span data-ttu-id="d0d68-113">Le informazioni in un file della firma vengono usate per specificare le parti di codice nel file di implementazione corrispondente a cui è possibile accedere dal codice esterno al file di implementazione e le parti interne al file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-113">You use the information in a signature file to specify what parts of the code in the corresponding implementation file can be accessed from code outside the implementation file, and what parts are internal to the implementation file.</span></span> <span data-ttu-id="d0d68-114">Gli spazi dei nomi, i moduli e i tipi inclusi nel file della firma devono essere un subset degli spazi dei nomi, dei moduli e dei tipi inclusi nel file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-114">The namespaces, modules, and types that are included in the signature file must be a subset of the namespaces, modules, and types that are included in the implementation file.</span></span> <span data-ttu-id="d0d68-115">Con le eccezioni descritte più avanti in questo argomento, gli elementi del linguaggio non elencati nel file della firma vengono considerati privati per il file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-115">With some exceptions noted later in this topic, those language elements that are not listed in the signature file are considered private to the implementation file.</span></span> <span data-ttu-id="d0d68-116">Se non vengono trovati file della firma nel progetto o nella riga di comando, viene usata l'opzione di accessibilità predefinita.</span><span class="sxs-lookup"><span data-stu-id="d0d68-116">If no signature file is found in the project or command line, the default accessibility is used.</span></span>

<span data-ttu-id="d0d68-117">Per ulteriori informazioni sull'accessibilità predefinita, vedere [controllo di accesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="d0d68-117">For more information about the default accessibility, see [Access Control](access-control.md).</span></span>

<span data-ttu-id="d0d68-118">In un file della firma non ripetere la definizione dei tipi e le implementazioni di ogni metodo o funzione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-118">In a signature file, you do not repeat the definition of the types and the implementations of each method or function.</span></span> <span data-ttu-id="d0d68-119">Usare invece la firma per ogni metodo e funzione, che consente di specificare in modo completo le funzionalità implementate da un modulo o da un frammento dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d0d68-119">Instead, you use the signature for each method and function, which acts as a complete specification of the functionality that is implemented by a module or namespace fragment.</span></span> <span data-ttu-id="d0d68-120">La sintassi per una firma di tipo è uguale a quella usata nelle dichiarazioni del metodo astratto nelle interfacce e nelle classi astratte e viene anche mostrata da IntelliSense e dall'interprete F# fsi.exe quando visualizza correttamente l'input compilato.</span><span class="sxs-lookup"><span data-stu-id="d0d68-120">The syntax for a type signature is the same as that used in abstract method declarations in interfaces and abstract classes, and is also shown by IntelliSense and by the F# interpreter fsi.exe when it displays correctly compiled input.</span></span>

<span data-ttu-id="d0d68-121">Se le informazioni nella firma di tipo non sono sufficienti a indicare se il tipo è sealed o un tipo di interfaccia, è necessario aggiungere un attributo che indichi la natura del tipo al compilatore.</span><span class="sxs-lookup"><span data-stu-id="d0d68-121">If there is not enough information in the type signature to indicate whether a type is sealed, or whether it is an interface type, you must add an attribute that indicates the nature of the type to the compiler.</span></span> <span data-ttu-id="d0d68-122">Gli attributi usati per questo scopo vengono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="d0d68-122">Attributes that you use for this purpose are described in the following table.</span></span>



|<span data-ttu-id="d0d68-123">Attributo</span><span class="sxs-lookup"><span data-stu-id="d0d68-123">Attribute</span></span>|<span data-ttu-id="d0d68-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d0d68-124">Description</span></span>|
|---------|-----------|
|`[<Sealed>]`|<span data-ttu-id="d0d68-125">Per un tipo senza membri astratti o che non deve essere esteso.</span><span class="sxs-lookup"><span data-stu-id="d0d68-125">For a type that has no abstract members, or that should not be extended.</span></span>|
|`[<Interface>]`|<span data-ttu-id="d0d68-126">Per un tipo che corrisponde a un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d0d68-126">For a type that is an interface.</span></span>|
<span data-ttu-id="d0d68-127">Il compilatore genera un errore se gli attributi non sono coerenti tra la firma e la dichiarazione nel file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-127">The compiler produces an error if the attributes are not consistent between the signature and the declaration in the implementation file.</span></span>

<span data-ttu-id="d0d68-128">Usare la parola chiave `val` per creare una firma per un valore o un valore di funzione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-128">Use the keyword `val` to create a signature for a value or function value.</span></span> <span data-ttu-id="d0d68-129">La parola chiave `type` introduce una firma di tipo.</span><span class="sxs-lookup"><span data-stu-id="d0d68-129">The keyword `type` introduces a type signature.</span></span>

<span data-ttu-id="d0d68-130">È possibile generare un file della firma usando l'opzione `--sig` del compilatore.</span><span class="sxs-lookup"><span data-stu-id="d0d68-130">You can generate a signature file by using the `--sig` compiler option.</span></span> <span data-ttu-id="d0d68-131">In generale, i file FSI non vengono scritti manualmente.</span><span class="sxs-lookup"><span data-stu-id="d0d68-131">Generally, you do not write .fsi files manually.</span></span> <span data-ttu-id="d0d68-132">I file FSI vengono invece generati usando il compilatore, aggiunti al progetto, se disponibile, e modificati rimuovendo i metodi e le funzioni che non si vogliono rendere accessibili.</span><span class="sxs-lookup"><span data-stu-id="d0d68-132">Instead, you generate .fsi files by using the compiler, add them to your project, if you have one, and edit them by removing methods and functions that you do not want to be accessible.</span></span>

<span data-ttu-id="d0d68-133">Esistono diverse regole per le firme di tipo:</span><span class="sxs-lookup"><span data-stu-id="d0d68-133">There are several rules for type signatures:</span></span>


- <span data-ttu-id="d0d68-134">Le abbreviazioni del tipo in un file di implementazione non devono corrispondere a un tipo senza abbreviazione in un file della firma.</span><span class="sxs-lookup"><span data-stu-id="d0d68-134">Type abbreviations in an implementation file must not match a type without an abbreviation in a signature file.</span></span>


- <span data-ttu-id="d0d68-135">I record e le unioni discriminate devono esporre tutti i campi oppure nessuno e i costruttori e l'ordine nella firma devono corrispondere all'ordine nel file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-135">Records and discriminated unions must expose either all or none of their fields and constructors, and the order in the signature must match the order in the implementation file.</span></span> <span data-ttu-id="d0d68-136">Le classi possono visualizzare alcuni, tutti o nessun campo e metodo nella firma.</span><span class="sxs-lookup"><span data-stu-id="d0d68-136">Classes can reveal some, all, or none of their fields and methods in the signature.</span></span>


- <span data-ttu-id="d0d68-137">Le classi e le strutture con costruttori devono esporre le dichiarazioni delle relative classi base (dichiarazione `inherits` ).</span><span class="sxs-lookup"><span data-stu-id="d0d68-137">Classes and structures that have constructors must expose the declarations of their base classes (the `inherits` declaration).</span></span> <span data-ttu-id="d0d68-138">Inoltre, le classi e le strutture con costruttori devono esporre tutti i metodi astratti e le dichiarazioni di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d0d68-138">Also, classes and structures that have constructors must expose all of their abstract methods and interface declarations.</span></span>


- <span data-ttu-id="d0d68-139">I tipi di interfaccia devono visualizzare tutti i relativi metodi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="d0d68-139">Interface types must reveal all their methods and interfaces.</span></span>


<span data-ttu-id="d0d68-140">Le regole per le firme di valore sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="d0d68-140">The rules for value signatures are as follows:</span></span>


- <span data-ttu-id="d0d68-141">I modificatori per l'accessibilità (`public`, `internal`e così via) e i modificatori `inline` e `mutable` nella firma devono corrispondere a quelli nell'implementazione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-141">Modifiers for accessibility (`public`, `internal`, and so on) and the `inline` and `mutable` modifiers in the signature must match those in the implementation.</span></span>


- <span data-ttu-id="d0d68-142">Il numero di parametri di tipo generico (dedotti implicitamente o dichiarati esplicitamente) deve corrispondere e il tipo e i vincoli di tipo nei parametri di tipo generico devono corrispondere.</span><span class="sxs-lookup"><span data-stu-id="d0d68-142">The number of generic type parameters (either implicitly inferred or explicitly declared) must match, and the types and type constraints in generic type parameters must match.</span></span>


- <span data-ttu-id="d0d68-143">Se viene usato l'attributo `Literal` , deve essere visualizzato sia nella firma che nell'implementazione e è necessario usare lo stesso valore letterale per entrambe.</span><span class="sxs-lookup"><span data-stu-id="d0d68-143">If the `Literal` attribute is used, it must appear in both the signature and the implementation, and the same literal value must be used for both.</span></span>


- <span data-ttu-id="d0d68-144">Il modello dei parametri (anche noto come *grado*) delle firme e delle implementazioni deve essere coerente.</span><span class="sxs-lookup"><span data-stu-id="d0d68-144">The pattern of parameters (also known as the *arity*) of signatures and implementations must be consistent.</span></span>


<span data-ttu-id="d0d68-145">L'esempio di codice seguente mostra un esempio di file della firma che contiene lo spazio dei nomi, il modulo, il valore di funzione e le firme di tipo, oltre agli attributi appropriati.</span><span class="sxs-lookup"><span data-stu-id="d0d68-145">The following code example shows an example of a signature file that has namespace, module, function value, and type signatures together with the appropriate attributes.</span></span> <span data-ttu-id="d0d68-146">Mostra anche il file di implementazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="d0d68-146">It also shows the corresponding implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9002.fs)]

<span data-ttu-id="d0d68-147">Il codice seguente mostra il file di implementazione.</span><span class="sxs-lookup"><span data-stu-id="d0d68-147">The following code shows the implementation file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9001.fs)]
    
## <a name="see-also"></a><span data-ttu-id="d0d68-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0d68-148">See Also</span></span>
[<span data-ttu-id="d0d68-149">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="d0d68-149">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d0d68-150">Controllo di accesso</span><span class="sxs-lookup"><span data-stu-id="d0d68-150">Access Control</span></span>](access-control.md)

[<span data-ttu-id="d0d68-151">Opzioni del compilatore</span><span class="sxs-lookup"><span data-stu-id="d0d68-151">Compiler Options</span></span>](compiler-options.md)
