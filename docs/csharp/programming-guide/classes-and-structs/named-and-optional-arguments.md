---
title: Argomenti denominati e facoltativi - Guida per programmatori C#
description: Gli argomenti denominati in C# specificano gli argomenti per nome, non per la posizione. Gli argomenti facoltativi possono essere omessi.
ms.date: 07/20/2015
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
ms.openlocfilehash: 46b9dc23644e68aea2767f2b990fe7f243a4f357
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864982"
---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="a1415-104">Argomenti denominati e facoltativi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="a1415-104">Named and Optional Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="a1415-105">In C# 4 sono stati introdotti gli argomenti denominati e facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a1415-105">C# 4 introduces named and optional arguments.</span></span> <span data-ttu-id="a1415-106">Gli *argomenti denominati* consentono di specificare un argomento per un particolare parametro associando l'argomento al nome del parametro anziché alla posizione del parametro nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="a1415-106">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="a1415-107">Gli *argomenti facoltativi* consentono di omettere gli argomenti per alcuni parametri.</span><span class="sxs-lookup"><span data-stu-id="a1415-107">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="a1415-108">Entrambe le tecniche possono essere usate con i metodi, gli indicizzatori, i costruttori e i delegati.</span><span class="sxs-lookup"><span data-stu-id="a1415-108">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="a1415-109">Quando si usano gli argomenti denominati e facoltativi, gli argomenti vengono valutati nell'ordine nel quale sono visualizzati nell'elenco di argomenti, non nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="a1415-109">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="a1415-110">I parametri denominati e facoltativi, se usati insieme, consentono di specificare gli argomenti solo per alcuni parametri di un elenco di parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a1415-110">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="a1415-111">Questa funzionalità semplifica considerevolmente le chiamate alle interfacce COM, ad esempio alle API di automazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="a1415-111">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="a1415-112">Argomenti denominati</span><span class="sxs-lookup"><span data-stu-id="a1415-112">Named Arguments</span></span>  
 <span data-ttu-id="a1415-113">Gli argomenti denominati evitano di dover ricordare o cercare l'ordine di parametri negli elenchi di parametri dei metodi chiamati.</span><span class="sxs-lookup"><span data-stu-id="a1415-113">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="a1415-114">Il parametro per ogni argomento può essere specificato dal nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="a1415-114">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="a1415-115">Ad esempio, una funzione che stampa altri dettagli, ad esempio il nome del venditore, il numero dell'ordine e il nome del prodotto, può essere chiamata normalmente inviando gli argomenti relativi alla posizione, nell'ordine definito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="a1415-115">For example, a function that prints order details (such as, seller name, order number & product name) can be called in the standard way by sending arguments by position, in the order defined by the function.</span></span>
  
 `PrintOrderDetails("Gift Shop", 31, "Red Mug");`
  
 <span data-ttu-id="a1415-116">Se non si ricorda l'ordine dei parametri, ma se ne conoscono i nomi, è possibile inviare gli argomenti in qualsiasi ordine.</span><span class="sxs-lookup"><span data-stu-id="a1415-116">If you do not remember the order of the parameters but know their names, you can send the arguments in any order.</span></span>  
  
 `PrintOrderDetails(orderNum: 31, productName: "Red Mug", sellerName: "Gift Shop");`
  
 `PrintOrderDetails(productName: "Red Mug", sellerName: "Gift Shop", orderNum: 31);`
  
 <span data-ttu-id="a1415-117">Gli argomenti denominati migliorano anche la leggibilità del codice identificando che cosa rappresenta ogni argomento.</span><span class="sxs-lookup"><span data-stu-id="a1415-117">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span> <span data-ttu-id="a1415-118">Nel metodo di esempio riportato di seguito `sellerName` non può essere Null o uno spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="a1415-118">In the example method below, the `sellerName` cannot be null or white space.</span></span> <span data-ttu-id="a1415-119">`sellerName` e `productName` sono di tipi stringa, quindi, anziché inviare argomenti in base alla posizione, è opportuno usare argomenti denominati per evitare ambiguità tra i due e semplificare la lettura del codice.</span><span class="sxs-lookup"><span data-stu-id="a1415-119">As both `sellerName` and `productName` are string types, instead of sending arguments by position, it makes sense to use named arguments to disambiguate the two and reduce confusion for anyone reading the code.</span></span>
  
 <span data-ttu-id="a1415-120">Se usati con argomenti posizionali, gli argomenti denominati sono validi se</span><span class="sxs-lookup"><span data-stu-id="a1415-120">Named arguments, when used with positional arguments, are valid as long as</span></span>

- <span data-ttu-id="a1415-121">non sono seguiti da argomenti posizionali, o</span><span class="sxs-lookup"><span data-stu-id="a1415-121">they're not followed by any positional arguments, or</span></span>

 `PrintOrderDetails("Gift Shop", 31, productName: "Red Mug");`

- <span data-ttu-id="a1415-122">_iniziando con C# 7.2_, vengono usati nella posizione corretta.</span><span class="sxs-lookup"><span data-stu-id="a1415-122">_starting with C# 7.2_, they're used in the correct position.</span></span> <span data-ttu-id="a1415-123">Nell'esempio seguente il parametro `orderNum` è nella posizione corretta, ma non è denominato in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="a1415-123">In the example below, the parameter `orderNum` is in the correct position but isn't explicitly named.</span></span>

 `PrintOrderDetails(sellerName: "Gift Shop", 31, productName: "Red Mug");`
  
 <span data-ttu-id="a1415-124">Gli argomenti posizionali che seguono gli argomenti denominati non ordinati non sono validi.</span><span class="sxs-lookup"><span data-stu-id="a1415-124">Positional arguments that follow any out-of-order named arguments are invalid.</span></span>

 ```csharp
 // This generates CS1738: Named argument specifications must appear after all fixed arguments have been specified.
 PrintOrderDetails(productName: "Red Mug", 31, "Gift Shop");
 ```
  
## <a name="example"></a><span data-ttu-id="a1415-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1415-125">Example</span></span>  
 <span data-ttu-id="a1415-126">Il codice seguente implementa gli esempi di questa e altre sezioni.</span><span class="sxs-lookup"><span data-stu-id="a1415-126">The following code implements the examples from this section along with some additional ones.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/program.cs#1)]  
  
## <a name="optional-arguments"></a><span data-ttu-id="a1415-127">Argomenti facoltativi</span><span class="sxs-lookup"><span data-stu-id="a1415-127">Optional Arguments</span></span>  
 <span data-ttu-id="a1415-128">La definizione di un metodo, un costruttore, un indicizzatore o un delegato può specificare che i parametri sono obbligatori o facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a1415-128">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="a1415-129">Tutte le chiamate devono specificare gli argomenti per tutti i parametri obbligatori, ma possono omettere gli argomenti per i parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a1415-129">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="a1415-130">Ogni parametro facoltativo ha un valore predefinito incluso nella definizione.</span><span class="sxs-lookup"><span data-stu-id="a1415-130">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="a1415-131">Se per il parametro non viene inviato alcun argomento, viene usato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a1415-131">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="a1415-132">Il valore predefinito deve essere uno dei tipi di espressioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1415-132">A default value must be one of the following types of expressions:</span></span>  
  
- <span data-ttu-id="a1415-133">un'espressione costante;</span><span class="sxs-lookup"><span data-stu-id="a1415-133">a constant expression;</span></span>  
  
- <span data-ttu-id="a1415-134">un'espressione del form `new ValType()`, dove `ValType` è un tipo di valore, ad esempio [enum](../../language-reference/builtin-types/enum.md) o [struct](../../language-reference/builtin-types/struct.md);</span><span class="sxs-lookup"><span data-stu-id="a1415-134">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../language-reference/builtin-types/enum.md) or a [struct](../../language-reference/builtin-types/struct.md);</span></span>  
  
- <span data-ttu-id="a1415-135">un'espressione del form [default(ValType)](../../language-reference/operators/default.md), dove `ValType` è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="a1415-135">an expression of the form [default(ValType)](../../language-reference/operators/default.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="a1415-136">I parametri facoltativi sono definiti alla fine dell'elenco di parametri, dopo eventuali parametri obbligatori.</span><span class="sxs-lookup"><span data-stu-id="a1415-136">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="a1415-137">Se il chiamante specifica un argomento per un parametro di una successione di parametri facoltativi, deve specificare gli argomenti per tutti i parametri facoltativi precedenti.</span><span class="sxs-lookup"><span data-stu-id="a1415-137">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="a1415-138">I gap delimitati da virgole nell'elenco di argomenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="a1415-138">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="a1415-139">Nel codice seguente, ad esempio, il metodo di istanza `ExampleMethod` viene definito con un parametro obbligatorio e due parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a1415-139">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#15)]  
  
 <span data-ttu-id="a1415-140">La chiamata seguente a `ExampleMethod` genera un errore del compilatore, poiché viene specificato un argomento per il terzo parametro ma non per il secondo.</span><span class="sxs-lookup"><span data-stu-id="a1415-140">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="a1415-141">Se, tuttavia, si conosce il nome del terzo parametro, è possibile usare un argomento denominato per eseguire l'attività.</span><span class="sxs-lookup"><span data-stu-id="a1415-141">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="a1415-142">IntelliSense usa le parentesi per indicare parametri facoltativi, come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="a1415-142">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration:</span></span>  
  
 ![Screenshot con le informazioni rapide di IntelliSense per il metodo ExampleMethod.](./media/named-and-optional-arguments/optional-examplemethod-parameters.png)  
  
> [!NOTE]
> <span data-ttu-id="a1415-144">È possibile anche dichiarare parametri facoltativi usando la classe .NET <xref:System.Runtime.InteropServices.OptionalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a1415-144">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="a1415-145">I parametri `OptionalAttribute` non richiedono un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="a1415-145">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1415-146">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1415-146">Example</span></span>  
 <span data-ttu-id="a1415-147">Nell'esempio seguente il costruttore per `ExampleClass` ha un solo parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="a1415-147">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="a1415-148">Il metodo di istanza `ExampleMethod` ha un solo parametro obbligatorio, `required`, e due parametri facoltativi, `optionalstr` e `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="a1415-148">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="a1415-149">Il codice in `Main` illustra i diversi modi in cui è possibile richiamare il costruttore e il metodo.</span><span class="sxs-lookup"><span data-stu-id="a1415-149">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/optional.cs#2)]  
  
## <a name="com-interfaces"></a><span data-ttu-id="a1415-150">Interfacce COM</span><span class="sxs-lookup"><span data-stu-id="a1415-150">COM Interfaces</span></span>  
 <span data-ttu-id="a1415-151">Gli argomenti denominati e facoltativi, insieme al supporto per gli oggetti dinamici e ad altri miglioramenti, aumentano considerevolmente l'interoperabilità con le API COM, quali le API di automazione di Office.</span><span class="sxs-lookup"><span data-stu-id="a1415-151">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="a1415-152">Ad esempio, il metodo <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> nell'interfaccia <xref:Microsoft.Office.Interop.Excel.Range> di Microsoft Office Excel ha sette parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="a1415-152">For example, the <xref:Microsoft.Office.Interop.Excel.Range.AutoFormat%2A> method in the Microsoft Office Excel <xref:Microsoft.Office.Interop.Excel.Range> interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="a1415-153">Questi parametri sono illustrati nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="a1415-153">These parameters are shown in the following illustration:</span></span>  
  
 ![Screenshot con le informazioni rapide di IntelliSense per il metodo AutoFormat.](./media/named-and-optional-arguments/autoformat-method-parameters.png)  
  
 <span data-ttu-id="a1415-155">In C# 3.0 e versioni precedenti è necessario un argomento per ogni parametro, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a1415-155">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#3)]  
  
 <span data-ttu-id="a1415-156">È tuttavia possibile semplificare in modo sostanziale la chiamata a `AutoFormat` mediante argomenti denominati e facoltativi, introdotti in C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="a1415-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="a1415-157">Gli argomenti denominati e facoltativi consentono di omettere l'argomento per un parametro facoltativo se non si vuole modificare il valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="a1415-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="a1415-158">Nella chiamata seguente viene specificato un valore per uno solo dei sette parametri.</span><span class="sxs-lookup"><span data-stu-id="a1415-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/namedandoptcom.cs#13)]  
  
 <span data-ttu-id="a1415-159">Per altre informazioni ed esempi, vedere [come usare gli argomenti denominati e facoltativi nella programmazione di Office](./how-to-use-named-and-optional-arguments-in-office-programming.md) e [come accedere agli oggetti di interoperabilità di Office usando le funzionalità di C#](../interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="a1415-159">For more information and examples, see [How to use named and optional arguments in Office programming](./how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to access Office interop objects by using C# features](../interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="a1415-160">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="a1415-160">Overload Resolution</span></span>  
 <span data-ttu-id="a1415-161">L'uso di argomenti denominati e facoltativi influisce sulla risoluzione dell'overload nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1415-161">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
- <span data-ttu-id="a1415-162">Un metodo, un indicizzatore o un costruttore è un candidato per l'esecuzione se ogni parametro è facoltativo o corrisponde, per nome o per posizione, a un solo argomento nell'istruzione chiamante e tale argomento può essere convertito nel tipo del parametro.</span><span class="sxs-lookup"><span data-stu-id="a1415-162">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
- <span data-ttu-id="a1415-163">Se è disponibile più di un candidato, agli argomenti specificati in modo esplicito vengono applicate le regole di risoluzione dell'overload per le conversioni preferite.</span><span class="sxs-lookup"><span data-stu-id="a1415-163">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="a1415-164">Gli argomenti omessi per i parametri facoltativi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="a1415-164">Omitted arguments for optional parameters are ignored.</span></span>  
  
- <span data-ttu-id="a1415-165">Se due candidati sono giudicati ugualmente validi, la preferenza va a un candidato che non ha parametri facoltativi per i quali sono stati omessi gli argomenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="a1415-165">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="a1415-166">Si tratta di una conseguenza di una preferenza generale nella risoluzione dell'overload per i candidati che hanno un numero di parametri inferiore.</span><span class="sxs-lookup"><span data-stu-id="a1415-166">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a1415-167">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="a1415-167">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a1415-168">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a1415-168">See also</span></span>

- [<span data-ttu-id="a1415-169">Come usare argomenti denominati e facoltativi nella programmazione di Office</span><span class="sxs-lookup"><span data-stu-id="a1415-169">How to use named and optional arguments in Office programming</span></span>](./how-to-use-named-and-optional-arguments-in-office-programming.md)
- [<span data-ttu-id="a1415-170">Utilizzo del tipo dinamico</span><span class="sxs-lookup"><span data-stu-id="a1415-170">Using Type dynamic</span></span>](../types/using-type-dynamic.md)
- [<span data-ttu-id="a1415-171">Utilizzo di costruttori</span><span class="sxs-lookup"><span data-stu-id="a1415-171">Using Constructors</span></span>](./using-constructors.md)
- [<span data-ttu-id="a1415-172">Utilizzo degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="a1415-172">Using Indexers</span></span>](../indexers/using-indexers.md)
