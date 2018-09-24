---
title: Utilizzo degli spazi dei nomi (Guida per programmatori C#)
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 81876d1818a6e82764e4aea0ae2b6f9e091f0ba3
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706278"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="c69af-102">Utilizzo degli spazi dei nomi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c69af-102">Using Namespaces (C# Programming Guide)</span></span>
<span data-ttu-id="c69af-103">Gli spazi dei nomi vengono usati frequentemente nei programmi C# in due modi.</span><span class="sxs-lookup"><span data-stu-id="c69af-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="c69af-104">In primo luogo, le classi di .NET Framework usano gli spazi dei nomi per organizzare numerose classi.</span><span class="sxs-lookup"><span data-stu-id="c69af-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="c69af-105">In secondo luogo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.</span><span class="sxs-lookup"><span data-stu-id="c69af-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="c69af-106">Accesso agli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="c69af-106">Accessing Namespaces</span></span>  
 <span data-ttu-id="c69af-107">La maggior parte delle applicazioni C# iniziano con una sezione di direttive `using`.</span><span class="sxs-lookup"><span data-stu-id="c69af-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="c69af-108">In questa sezione sono elencati gli spazi dei nomi usati di frequente dall'applicazione, evitando al programmatore di specificare un nome completo ogni volta che viene usato un metodo contenuto negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c69af-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="c69af-109">Ad esempio, includendo la riga:</span><span class="sxs-lookup"><span data-stu-id="c69af-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_1.cs)]  
  
 <span data-ttu-id="c69af-110">All'inizio di un programma, il programmatore può usare il codice:</span><span class="sxs-lookup"><span data-stu-id="c69af-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_2.cs)]  
  
 <span data-ttu-id="c69af-111">Invece di:</span><span class="sxs-lookup"><span data-stu-id="c69af-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/using-namespaces_3.cs)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="c69af-112">Alias degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="c69af-112">Namespace Aliases</span></span>  
 <span data-ttu-id="c69af-113">È anche possibile usare la [direttiva using](../../../csharp/language-reference/keywords/using-directive.md) per creare un alias per uno [spazio dei nomi](../../../csharp/language-reference/keywords/namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c69af-113">The [using Directive](../../../csharp/language-reference/keywords/using-directive.md) can also be used to create an alias for a [namespace](../../../csharp/language-reference/keywords/namespace.md).</span></span> <span data-ttu-id="c69af-114">Se ad esempio si usa uno spazio dei nomi scritto in precedenza che contiene spazi dei nomi annidati, è consigliabile dichiarare un alias per fornire un modo abbreviato per fare riferimento a uno di essi in particolare, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="c69af-114">For example, if you are using a previously written namespace that contains nested namespaces, you might want to declare an alias to provide a shorthand way of referencing one in particular, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#7](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_4.cs)]  
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="c69af-115">Uso degli spazi dei nomi per controllare l'ambito</span><span class="sxs-lookup"><span data-stu-id="c69af-115">Using Namespaces to control scope</span></span>  
 <span data-ttu-id="c69af-116">La parola chiave `namespace` viene usata per dichiarare un ambito.</span><span class="sxs-lookup"><span data-stu-id="c69af-116">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="c69af-117">La possibilità di creare ambiti all'interno del progetto consente di organizzare il codice e di creare tipi univoci globali.</span><span class="sxs-lookup"><span data-stu-id="c69af-117">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="c69af-118">Nell'esempio seguente, una classe denominata `SampleClass` è definita in due spazi dei nomi, uno annidato all'interno dell'altro.</span><span class="sxs-lookup"><span data-stu-id="c69af-118">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="c69af-119">Oggetto [. ](../../../csharp/language-reference/operators/member-access-operator.md) viene usato per identificare il metodo da chiamare.</span><span class="sxs-lookup"><span data-stu-id="c69af-119">The [. Operator](../../../csharp/language-reference/operators/member-access-operator.md) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_5.cs)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="c69af-120">nomi completi</span><span class="sxs-lookup"><span data-stu-id="c69af-120">Fully Qualified Names</span></span>  
 <span data-ttu-id="c69af-121">Spazi dei nomi e tipi hanno nomi univoci, descritti da nomi completi che indicano una gerarchia logica.</span><span class="sxs-lookup"><span data-stu-id="c69af-121">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="c69af-122">Ad esempio, l'istruzione `A.B` implica che `A` è il nome dello spazio dei nomi o del tipo e `B` è annidato al suo interno.</span><span class="sxs-lookup"><span data-stu-id="c69af-122">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="c69af-123">Nell'esempio seguente sono presenti classi e spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="c69af-123">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="c69af-124">Il nome completo è indicato come commento dopo ogni entità.</span><span class="sxs-lookup"><span data-stu-id="c69af-124">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_6.cs)]  
  
 <span data-ttu-id="c69af-125">Nel segmento di codice precedente:</span><span class="sxs-lookup"><span data-stu-id="c69af-125">In the previous code segment:</span></span>  
  
-   <span data-ttu-id="c69af-126">Lo spazio dei nomi `N1` è un membro dello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="c69af-126">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="c69af-127">Il relativo nome completo è `N1`.</span><span class="sxs-lookup"><span data-stu-id="c69af-127">Its fully qualified name is `N1`.</span></span>  
  
-   <span data-ttu-id="c69af-128">Lo spazio dei nomi `N2` è un membro di `N1`.</span><span class="sxs-lookup"><span data-stu-id="c69af-128">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="c69af-129">Il relativo nome completo è `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="c69af-129">Its fully qualified name is `N1.N2`.</span></span>  
  
-   <span data-ttu-id="c69af-130">La classe `C1` è un membro di `N1`.</span><span class="sxs-lookup"><span data-stu-id="c69af-130">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="c69af-131">Il relativo nome completo è `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="c69af-131">Its fully qualified name is `N1.C1`.</span></span>  
  
-   <span data-ttu-id="c69af-132">Il nome della classe `C2` viene usato due volte in questo codice.</span><span class="sxs-lookup"><span data-stu-id="c69af-132">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="c69af-133">Tuttavia, i nomi completi sono univoci.</span><span class="sxs-lookup"><span data-stu-id="c69af-133">However, the fully qualified names are unique.</span></span> <span data-ttu-id="c69af-134">La prima istanza di `C2` è dichiarata all'interno di `C1`, pertanto il relativo nome completo è: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="c69af-134">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="c69af-135">La seconda istanza di `C2` è dichiarata all'interno di uno spazio dei nomi `N2`, pertanto il relativo nome completo è `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="c69af-135">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="c69af-136">Usando il segmento di codice precedente, è possibile aggiungere un nuovo membro della classe, `C3`, allo spazio dei nomi `N1.N2` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="c69af-136">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_7.cs)]  
  
 <span data-ttu-id="c69af-137">In generale, usare `::` per fare riferimento a un alias dello spazio dei nomi oppure `global::` per fare riferimento allo spazio dei nomi globale e `.` per qualificare i tipi o i membri.</span><span class="sxs-lookup"><span data-stu-id="c69af-137">In general, use `::` to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="c69af-138">È un errore usare `::` con un alias che fa riferimento a un tipo, anziché a uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c69af-138">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="c69af-139">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c69af-139">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_8.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#12](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_9.cs)]  
  
 <span data-ttu-id="c69af-140">Tenere presente che la parola `global` non è un alias predefinito, pertanto `global.X` non ha alcun significato speciale.</span><span class="sxs-lookup"><span data-stu-id="c69af-140">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="c69af-141">Acquisisce un significato speciale solo quando viene usata con `::`.</span><span class="sxs-lookup"><span data-stu-id="c69af-141">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="c69af-142">Se si definisce un alias denominato global, viene generato l'avviso del compilatore CS0440, perché `global::` fa sempre riferimento allo spazio dei nomi globale e non a un alias.</span><span class="sxs-lookup"><span data-stu-id="c69af-142">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="c69af-143">Ad esempio, la riga seguente genera l'avviso:</span><span class="sxs-lookup"><span data-stu-id="c69af-143">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_10.cs)]  
  
 <span data-ttu-id="c69af-144">L'uso di `::` con gli alias è consigliabile e garantisce la protezione contro l'introduzione imprevista di tipi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c69af-144">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="c69af-145">Si prenda, ad esempio, in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c69af-145">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_11.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#15](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/using-namespaces_12.cs)]  
  
 <span data-ttu-id="c69af-146">Questo metodo funziona, ma se un tipo denominato `Alias` dovesse essere introdotto successivamente, `Alias.` sarebbe associato a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="c69af-146">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="c69af-147">L'uso di `Alias::Exception` assicura che `Alias` sia trattato come un alias di spazio dei nomi e non venga erroneamente considerato un tipo.</span><span class="sxs-lookup"><span data-stu-id="c69af-147">Using `Alias::Exception` insures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  
  
 <span data-ttu-id="c69af-148">Per altre informazioni sull'alias `global`, vedere l'argomento [Procedura: utilizzare l'alias dello spazio dei nomi globale](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span><span class="sxs-lookup"><span data-stu-id="c69af-148">See the topic [How to: Use the Global Namespace Alias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md) for more information regarding the `global` alias.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69af-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c69af-149">See Also</span></span>

- [<span data-ttu-id="c69af-150">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c69af-150">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c69af-151">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="c69af-151">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="c69af-152">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="c69af-152">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="c69af-153">. (operatore)</span><span class="sxs-lookup"><span data-stu-id="c69af-153">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="c69af-154">Operatore ::</span><span class="sxs-lookup"><span data-stu-id="c69af-154">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
- [<span data-ttu-id="c69af-155">extern</span><span class="sxs-lookup"><span data-stu-id="c69af-155">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
