---
title: Argomenti denominati e facoltativi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namedParameter_CSharpKeyword
- cs_namedParameter
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], named
- named arguments [C#]
- arguments [C#], named
- optional arguments [C#]
- arguments [C#], optional
- parameters [C#], optional
- named and optional arguments [C#]
ms.assetid: 839c960c-c2dc-4d05-af4d-ca5428e54008
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 0dc2fcee3903b80816c98bab47e2b9a2e5ef78b0
ms.openlocfilehash: a7f05e3e0b19bf6457989f8db2b46741cf6b28c1
ms.contentlocale: it-it
ms.lasthandoff: 08/28/2017

---
# <a name="named-and-optional-arguments-c-programming-guide"></a><span data-ttu-id="155f3-102">Argomenti denominati e facoltativi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="155f3-102">Named and Optional Arguments (C# Programming Guide)</span></span>
<span data-ttu-id="155f3-103">In [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] sono stati introdotti gli argomenti denominati e facoltativi.</span><span class="sxs-lookup"><span data-stu-id="155f3-103">[!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] introduces named and optional arguments.</span></span> <span data-ttu-id="155f3-104">Gli *argomenti denominati* consentono di specificare un argomento per un particolare parametro associando l'argomento al nome del parametro anziché alla posizione del parametro nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="155f3-104">*Named arguments* enable you to specify an argument for a particular parameter by associating the argument with the parameter's name rather than with the parameter's position in the parameter list.</span></span> <span data-ttu-id="155f3-105">Gli *argomenti facoltativi* consentono di omettere gli argomenti per alcuni parametri.</span><span class="sxs-lookup"><span data-stu-id="155f3-105">*Optional arguments* enable you to omit arguments for some parameters.</span></span> <span data-ttu-id="155f3-106">Entrambe le tecniche possono essere usate con i metodi, gli indicizzatori, i costruttori e i delegati.</span><span class="sxs-lookup"><span data-stu-id="155f3-106">Both techniques can be used with methods, indexers, constructors, and delegates.</span></span>  
  
 <span data-ttu-id="155f3-107">Quando si usano gli argomenti denominati e facoltativi, gli argomenti vengono valutati nell'ordine nel quale sono visualizzati nell'elenco di argomenti, non nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="155f3-107">When you use named and optional arguments, the arguments are evaluated in the order in which they appear in the argument list, not the parameter list.</span></span>  
  
 <span data-ttu-id="155f3-108">I parametri denominati e facoltativi, se usati insieme, consentono di specificare gli argomenti solo per alcuni parametri di un elenco di parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="155f3-108">Named and optional parameters, when used together, enable you to supply arguments for only a few parameters from a list of optional parameters.</span></span> <span data-ttu-id="155f3-109">Questa funzionalità semplifica considerevolmente le chiamate alle interfacce COM, ad esempio alle API di automazione di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="155f3-109">This capability greatly facilitates calls to COM interfaces such as the Microsoft Office Automation APIs.</span></span>  
  
## <a name="named-arguments"></a><span data-ttu-id="155f3-110">Argomenti denominati</span><span class="sxs-lookup"><span data-stu-id="155f3-110">Named Arguments</span></span>  
 <span data-ttu-id="155f3-111">Gli argomenti denominati evitano di dover ricordare o cercare l'ordine di parametri negli elenchi di parametri dei metodi chiamati.</span><span class="sxs-lookup"><span data-stu-id="155f3-111">Named arguments free you from the need to remember or to look up the order of parameters in the parameter lists of called methods.</span></span> <span data-ttu-id="155f3-112">Il parametro per ogni argomento può essere specificato dal nome del parametro.</span><span class="sxs-lookup"><span data-stu-id="155f3-112">The parameter for each argument can be specified by parameter name.</span></span> <span data-ttu-id="155f3-113">Ad esempio, una funzione che calcola l'indice di massa corporea (BMI, Body Mass Index) può essere chiamata normalmente inviando gli argomenti relativi a peso e altezza in base alla posizione, nell'ordine definito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="155f3-113">For example, a function that calculates body mass index (BMI) can be called in the standard way by sending arguments for weight and height by position, in the order defined by the function.</span></span>  
  
 `CalculateBMI(123, 64);`  
  
 <span data-ttu-id="155f3-114">Se non si ricorda l'ordine dei parametri ma se ne conoscono i nomi, è possibile inviare gli argomenti in qualsiasi ordine, ovvero prima il peso o prima l'altezza.</span><span class="sxs-lookup"><span data-stu-id="155f3-114">If you do not remember the order of the parameters but you do know their names, you can send the arguments in either order, weight first or height first.</span></span>  
  
 `CalculateBMI(weight: 123, height: 64);`  
  
 `CalculateBMI(height: 64, weight: 123);`  
  
 <span data-ttu-id="155f3-115">Gli argomenti denominati migliorano anche la leggibilità del codice identificando che cosa rappresenta ogni argomento.</span><span class="sxs-lookup"><span data-stu-id="155f3-115">Named arguments also improve the readability of your code by identifying what each argument represents.</span></span>  
  
 <span data-ttu-id="155f3-116">Un argomento denominato può seguire gli argomenti posizionali, come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="155f3-116">A named argument can follow positional arguments, as shown here.</span></span>  
  
 `CalculateBMI(123, height: 64);`  
  
 <span data-ttu-id="155f3-117">Un argomento posizionale non può, tuttavia, seguire un argomento denominato.</span><span class="sxs-lookup"><span data-stu-id="155f3-117">However, a positional argument cannot follow a named argument.</span></span> <span data-ttu-id="155f3-118">L'istruzione seguente causa un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="155f3-118">The following statement causes a compiler error.</span></span>  
  
 `//CalculateBMI(weight: 123, 64);`  
  
## <a name="example"></a><span data-ttu-id="155f3-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="155f3-119">Example</span></span>  
 <span data-ttu-id="155f3-120">Il codice seguente implementa gli esempi di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="155f3-120">The following code implements the examples from this section.</span></span>  
  
 <span data-ttu-id="155f3-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="155f3-121">[!code-cs[csProgGuideNamedAndOptional#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_1.cs)]</span></span>  
  
## <a name="optional-arguments"></a><span data-ttu-id="155f3-122">Argomenti facoltativi</span><span class="sxs-lookup"><span data-stu-id="155f3-122">Optional Arguments</span></span>  
 <span data-ttu-id="155f3-123">La definizione di un metodo, un costruttore, un indicizzatore o un delegato può specificare che i parametri sono obbligatori o facoltativi.</span><span class="sxs-lookup"><span data-stu-id="155f3-123">The definition of a method, constructor, indexer, or delegate can specify that its parameters are required or that they are optional.</span></span> <span data-ttu-id="155f3-124">Tutte le chiamate devono specificare gli argomenti per tutti i parametri obbligatori, ma possono omettere gli argomenti per i parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="155f3-124">Any call must provide arguments for all required parameters, but can omit arguments for optional parameters.</span></span>  
  
 <span data-ttu-id="155f3-125">Ogni parametro facoltativo ha un valore predefinito incluso nella definizione.</span><span class="sxs-lookup"><span data-stu-id="155f3-125">Each optional parameter has a default value as part of its definition.</span></span> <span data-ttu-id="155f3-126">Se per il parametro non viene inviato alcun argomento, viene usato il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="155f3-126">If no argument is sent for that parameter, the default value is used.</span></span> <span data-ttu-id="155f3-127">Il valore predefinito deve essere uno dei tipi di espressioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="155f3-127">A default value must be one of the following types of expressions:</span></span>  
  
-   <span data-ttu-id="155f3-128">un'espressione costante;</span><span class="sxs-lookup"><span data-stu-id="155f3-128">a constant expression;</span></span>  
  
-   <span data-ttu-id="155f3-129">un'espressione del form `new ValType()`, dove `ValType` è un tipo di valore, ad esempio [enum](../../../csharp/language-reference/keywords/enum.md) o [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span><span class="sxs-lookup"><span data-stu-id="155f3-129">an expression of the form `new ValType()`, where `ValType` is a value type, such as an [enum](../../../csharp/language-reference/keywords/enum.md) or a [struct](../../../csharp/programming-guide/classes-and-structs/structs.md);</span></span>  
  
-   <span data-ttu-id="155f3-130">un'espressione del form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md), dove `ValType` è un tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="155f3-130">an expression of the form [default(ValType)](../../../csharp/programming-guide/statements-expressions-operators/default-value-expressions.md),  where `ValType` is a value type.</span></span>  
  
 <span data-ttu-id="155f3-131">I parametri facoltativi sono definiti alla fine dell'elenco di parametri, dopo eventuali parametri obbligatori.</span><span class="sxs-lookup"><span data-stu-id="155f3-131">Optional parameters are defined at the end of the parameter list, after any required parameters.</span></span> <span data-ttu-id="155f3-132">Se il chiamante specifica un argomento per un parametro di una successione di parametri facoltativi, deve specificare gli argomenti per tutti i parametri facoltativi precedenti.</span><span class="sxs-lookup"><span data-stu-id="155f3-132">If the caller provides an argument for any one of a succession of optional parameters, it must provide arguments for all preceding optional parameters.</span></span> <span data-ttu-id="155f3-133">I gap delimitati da virgole nell'elenco di argomenti non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="155f3-133">Comma-separated gaps in the argument list are not supported.</span></span> <span data-ttu-id="155f3-134">Nel codice seguente, ad esempio, il metodo di istanza `ExampleMethod` viene definito con un parametro obbligatorio e due parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="155f3-134">For example, in the following code, instance method `ExampleMethod` is defined with one required and two optional parameters.</span></span>  
  
 <span data-ttu-id="155f3-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="155f3-135">[!code-cs[csProgGuideNamedAndOptional#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_2.cs)]</span></span>  
  
 <span data-ttu-id="155f3-136">La chiamata seguente a `ExampleMethod` genera un errore del compilatore, poiché viene specificato un argomento per il terzo parametro ma non per il secondo.</span><span class="sxs-lookup"><span data-stu-id="155f3-136">The following call to `ExampleMethod` causes a compiler error, because an argument is provided for the third parameter but not for the second.</span></span>  
  
 `//anExample.ExampleMethod(3, ,4);`  
  
 <span data-ttu-id="155f3-137">Se, tuttavia, si conosce il nome del terzo parametro, è possibile usare un argomento denominato per eseguire l'attività.</span><span class="sxs-lookup"><span data-stu-id="155f3-137">However, if you know the name of the third parameter, you can use a named argument to accomplish the task.</span></span>  
  
 `anExample.ExampleMethod(3, optionalint: 4);`  
  
 <span data-ttu-id="155f3-138">IntelliSense usa le parentesi per indicare parametri facoltativi, come mostrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="155f3-138">IntelliSense uses brackets to indicate optional parameters, as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="155f3-139">![Informazioni rapide di IntelliSense per il metodo ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span><span class="sxs-lookup"><span data-stu-id="155f3-139">![IntelliSense Quick Info for method ExampleMethod.](../../../csharp/programming-guide/classes-and-structs/media/optional_parameters.png "Optional_Parameters")</span></span>  
<span data-ttu-id="155f3-140">Parametri facoltativi in ExampleMethod</span><span class="sxs-lookup"><span data-stu-id="155f3-140">Optional parameters in ExampleMethod</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="155f3-141">È possibile anche dichiarare parametri facoltativi usando la classe .NET <xref:System.Runtime.InteropServices.OptionalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="155f3-141">You can also declare optional parameters by using the .NET <xref:System.Runtime.InteropServices.OptionalAttribute> class.</span></span> <span data-ttu-id="155f3-142">I parametri `OptionalAttribute` non richiedono un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="155f3-142">`OptionalAttribute` parameters do not require a default value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="155f3-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="155f3-143">Example</span></span>  
 <span data-ttu-id="155f3-144">Nell'esempio seguente il costruttore per `ExampleClass` ha un solo parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="155f3-144">In the following example, the constructor for `ExampleClass` has one parameter, which is optional.</span></span> <span data-ttu-id="155f3-145">Il metodo di istanza `ExampleMethod` ha un solo parametro obbligatorio, `required`, e due parametri facoltativi, `optionalstr` e `optionalint`.</span><span class="sxs-lookup"><span data-stu-id="155f3-145">Instance method `ExampleMethod` has one required parameter, `required`, and two optional parameters, `optionalstr` and `optionalint`.</span></span> <span data-ttu-id="155f3-146">Il codice in `Main` illustra i diversi modi in cui è possibile richiamare il costruttore e il metodo.</span><span class="sxs-lookup"><span data-stu-id="155f3-146">The code in `Main` shows the different ways in which the constructor and method can be invoked.</span></span>  
  
 <span data-ttu-id="155f3-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="155f3-147">[!code-cs[csProgGuideNamedAndOptional#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_3.cs)]</span></span>  
  
## <a name="com-interfaces"></a><span data-ttu-id="155f3-148">Interfacce COM</span><span class="sxs-lookup"><span data-stu-id="155f3-148">COM Interfaces</span></span>  
 <span data-ttu-id="155f3-149">Gli argomenti denominati e facoltativi, insieme al supporto per gli oggetti dinamici e ad altri miglioramenti, aumentano considerevolmente l'interoperabilità con le API COM, quali le API di automazione di Office.</span><span class="sxs-lookup"><span data-stu-id="155f3-149">Named and optional arguments, along with support for dynamic objects and other enhancements, greatly improve interoperability with COM APIs, such as Office Automation APIs.</span></span>  
  
 <span data-ttu-id="155f3-150">Ad esempio, il metodo [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) nell'interfaccia [Range](http://go.microsoft.com/fwlink/?LinkId=148196) di Microsoft Office Excel ha sette parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="155f3-150">For example, the [AutoFormat](http://go.microsoft.com/fwlink/?LinkId=148201) method in the Microsoft Office Excel [Range](http://go.microsoft.com/fwlink/?LinkId=148196) interface has seven parameters, all of which are optional.</span></span> <span data-ttu-id="155f3-151">Questi parametri sono illustrati nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="155f3-151">These parameters are shown in the following illustration.</span></span>  
  
 <span data-ttu-id="155f3-152">![Informazioni rapide di IntelliSense per il metodo AutoFormat.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span><span class="sxs-lookup"><span data-stu-id="155f3-152">![IntelliSense Quick Info for the AutoFormat method.](../../../csharp/programming-guide/classes-and-structs/media/autoformat_parameters.png "AutoFormat_Parameters")</span></span>  
<span data-ttu-id="155f3-153">Parametri di AutoFormat</span><span class="sxs-lookup"><span data-stu-id="155f3-153">AutoFormat parameters</span></span>  
  
 <span data-ttu-id="155f3-154">In C# 3.0 e versioni precedenti è necessario un argomento per ogni parametro, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="155f3-154">In C# 3.0 and earlier versions, an argument is required for each parameter, as shown in the following example.</span></span>  
  
 <span data-ttu-id="155f3-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="155f3-155">[!code-cs[csProgGuideNamedAndOptional#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_4.cs)]</span></span>  
  
 <span data-ttu-id="155f3-156">È tuttavia possibile semplificare in modo sostanziale la chiamata a `AutoFormat` mediante argomenti denominati e facoltativi, introdotti in C# 4.0.</span><span class="sxs-lookup"><span data-stu-id="155f3-156">However, you can greatly simplify the call to `AutoFormat` by using named and optional arguments, introduced in C# 4.0.</span></span> <span data-ttu-id="155f3-157">Gli argomenti denominati e facoltativi consentono di omettere l'argomento per un parametro facoltativo se non si vuole modificare il valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="155f3-157">Named and optional arguments enable you to omit the argument for an optional parameter if you do not want to change the parameter's default value.</span></span> <span data-ttu-id="155f3-158">Nella chiamata seguente viene specificato un valore per uno solo dei sette parametri.</span><span class="sxs-lookup"><span data-stu-id="155f3-158">In the following call, a value is specified for only one of the seven parameters.</span></span>  
  
 <span data-ttu-id="155f3-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="155f3-159">[!code-cs[csProgGuideNamedAndOptional#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/named-and-optional-arguments_5.cs)]</span></span>  
  
 <span data-ttu-id="155f3-160">Per altre informazioni ed esempi, vedere [Procedura: Usare argomenti denominati e facoltativi nella programmazione di Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) e [Procedura: Accedere agli oggetti di interoperabilità di Office usando le funzionalità di Visual C#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span><span class="sxs-lookup"><span data-stu-id="155f3-160">For more information and examples, see [How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) and [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
## <a name="overload-resolution"></a><span data-ttu-id="155f3-161">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="155f3-161">Overload Resolution</span></span>  
 <span data-ttu-id="155f3-162">L'uso di argomenti denominati e facoltativi influisce sulla risoluzione dell'overload nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="155f3-162">Use of named and optional arguments affects overload resolution in the following ways:</span></span>  
  
-   <span data-ttu-id="155f3-163">Un metodo, un indicizzatore o un costruttore è un candidato per l'esecuzione se ogni parametro è facoltativo o corrisponde, per nome o per posizione, a un solo argomento nell'istruzione chiamante e tale argomento può essere convertito nel tipo del parametro.</span><span class="sxs-lookup"><span data-stu-id="155f3-163">A method, indexer, or constructor is a candidate for execution if each of its parameters either is optional or corresponds, by name or by position, to a single argument in the calling statement, and that argument can be converted to the type of the parameter.</span></span>  
  
-   <span data-ttu-id="155f3-164">Se è disponibile più di un candidato, agli argomenti specificati in modo esplicito vengono applicate le regole di risoluzione dell'overload per le conversioni preferite.</span><span class="sxs-lookup"><span data-stu-id="155f3-164">If more than one candidate is found, overload resolution rules for preferred conversions are applied to the arguments that are explicitly specified.</span></span> <span data-ttu-id="155f3-165">Gli argomenti omessi per i parametri facoltativi vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="155f3-165">Omitted arguments for optional parameters are ignored.</span></span>  
  
-   <span data-ttu-id="155f3-166">Se due candidati sono giudicati ugualmente validi, la preferenza va a un candidato che non ha parametri facoltativi per i quali sono stati omessi gli argomenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="155f3-166">If two candidates are judged to be equally good, preference goes to a candidate that does not have optional parameters for which arguments were omitted in the call.</span></span> <span data-ttu-id="155f3-167">Si tratta di una conseguenza di una preferenza generale nella risoluzione dell'overload per i candidati che hanno un numero di parametri inferiore.</span><span class="sxs-lookup"><span data-stu-id="155f3-167">This is a consequence of a general preference in overload resolution for candidates that have fewer parameters.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="155f3-168">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="155f3-168">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="155f3-169">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="155f3-169">See Also</span></span>  
 <span data-ttu-id="155f3-170">[Procedura: Usare argomenti denominati e facoltativi nella programmazione di Office](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="155f3-170">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="155f3-171">[Uso del tipo dinamico](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="155f3-171">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="155f3-172">[Uso dei costruttori](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span><span class="sxs-lookup"><span data-stu-id="155f3-172">[Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) </span></span>  
 [<span data-ttu-id="155f3-173">Uso degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="155f3-173">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)

