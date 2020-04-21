---
title: Uso degli spazi dei nomi - Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: b4326be8c9e299a96477096ec21864ec69037abe
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738236"
---
# <a name="using-namespaces-c-programming-guide"></a><span data-ttu-id="43c86-102">Uso degli spazi dei nomi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="43c86-102">Using namespaces (C# Programming Guide)</span></span>

<span data-ttu-id="43c86-103">Gli spazi dei nomi vengono usati frequentemente nei programmi C# in due modi.</span><span class="sxs-lookup"><span data-stu-id="43c86-103">Namespaces are heavily used within C# programs in two ways.</span></span> <span data-ttu-id="43c86-104">In primo luogo, le classi di .NET Framework usano gli spazi dei nomi per organizzare numerose classi.</span><span class="sxs-lookup"><span data-stu-id="43c86-104">Firstly, the .NET Framework classes use namespaces to organize its many classes.</span></span> <span data-ttu-id="43c86-105">In secondo luogo, dichiarando i propri spazi dei nomi è possibile controllare l'ambito dei nomi di classi e metodi nei progetti di programmazione più grandi.</span><span class="sxs-lookup"><span data-stu-id="43c86-105">Secondly, declaring your own namespaces can help control the scope of class and method names in larger programming projects.</span></span>  
  
## <a name="accessing-namespaces"></a><span data-ttu-id="43c86-106">Accesso agli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="43c86-106">Accessing namespaces</span></span>

 <span data-ttu-id="43c86-107">La maggior parte delle applicazioni C# iniziano con una sezione di direttive `using`.</span><span class="sxs-lookup"><span data-stu-id="43c86-107">Most C# applications begin with a section of `using` directives.</span></span> <span data-ttu-id="43c86-108">In questa sezione sono elencati gli spazi dei nomi usati di frequente dall'applicazione, evitando al programmatore di specificare un nome completo ogni volta che viene usato un metodo contenuto negli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="43c86-108">This section lists the namespaces that the application will be using frequently, and saves the programmer from specifying a fully qualified name every time that a method that is contained within is used.</span></span>  
  
 <span data-ttu-id="43c86-109">Ad esempio, includendo la riga:</span><span class="sxs-lookup"><span data-stu-id="43c86-109">For example, by including the line:</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 <span data-ttu-id="43c86-110">All'inizio di un programma, il programmatore può usare il codice:</span><span class="sxs-lookup"><span data-stu-id="43c86-110">At the start of a program, the programmer can use the code:</span></span>  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 <span data-ttu-id="43c86-111">Anziché:</span><span class="sxs-lookup"><span data-stu-id="43c86-111">Instead of:</span></span>  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a><span data-ttu-id="43c86-112">Alias dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="43c86-112">Namespace aliases</span></span>

 <span data-ttu-id="43c86-113">È inoltre possibile utilizzare la [ `using` direttiva](../../language-reference/keywords/using-directive.md) per creare un alias per uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="43c86-113">You can also use the [`using` directive](../../language-reference/keywords/using-directive.md) to create an alias for a namespace.</span></span> <span data-ttu-id="43c86-114">Usare il [qualificatore di alias dello spazio dei nomi `::`](../../language-reference/operators/namespace-alias-qualifier.md) per accedere ai membri dello spazio dei nomi con alias.</span><span class="sxs-lookup"><span data-stu-id="43c86-114">Use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to access the members of the aliased namespace.</span></span> <span data-ttu-id="43c86-115">Nell'esempio seguente viene illustrato come creare e usare un alias dello spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="43c86-115">The following example shows how to create and use a namespace alias:</span></span>
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a><span data-ttu-id="43c86-116">Uso degli spazi dei nomi per controllare l'ambito</span><span class="sxs-lookup"><span data-stu-id="43c86-116">Using namespaces to control scope</span></span>

 <span data-ttu-id="43c86-117">La parola chiave `namespace` viene usata per dichiarare un ambito.</span><span class="sxs-lookup"><span data-stu-id="43c86-117">The `namespace` keyword is used to declare a scope.</span></span> <span data-ttu-id="43c86-118">La possibilità di creare ambiti all'interno del progetto consente di organizzare il codice e di creare tipi univoci globali.</span><span class="sxs-lookup"><span data-stu-id="43c86-118">The ability to create scopes within your project helps organize code and lets you create globally-unique types.</span></span> <span data-ttu-id="43c86-119">Nell'esempio seguente, una classe denominata `SampleClass` è definita in due spazi dei nomi, uno annidato all'interno dell'altro.</span><span class="sxs-lookup"><span data-stu-id="43c86-119">In the following example, a class titled `SampleClass` is defined in two namespaces, one nested inside the other.</span></span> <span data-ttu-id="43c86-120">Il [ `.` token](../../language-reference/operators/member-access-operators.md#member-access-expression-) viene utilizzato per distinguere il metodo chiamato.</span><span class="sxs-lookup"><span data-stu-id="43c86-120">The [`.` token](../../language-reference/operators/member-access-operators.md#member-access-expression-) is used to differentiate which method gets called.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a><span data-ttu-id="43c86-121">Nomi completi</span><span class="sxs-lookup"><span data-stu-id="43c86-121">Fully qualified names</span></span>

 <span data-ttu-id="43c86-122">Spazi dei nomi e tipi hanno nomi univoci, descritti da nomi completi che indicano una gerarchia logica.</span><span class="sxs-lookup"><span data-stu-id="43c86-122">Namespaces and types have unique titles described by fully qualified names that indicate a logical hierarchy.</span></span> <span data-ttu-id="43c86-123">Ad esempio, l'istruzione `A.B` implica che `A` è il nome dello spazio dei nomi o del tipo e `B` è annidato al suo interno.</span><span class="sxs-lookup"><span data-stu-id="43c86-123">For example, the statement `A.B` implies that `A` is the name of the namespace or type, and `B` is nested inside it.</span></span>  
  
 <span data-ttu-id="43c86-124">Nell'esempio seguente sono presenti classi e spazi dei nomi annidati.</span><span class="sxs-lookup"><span data-stu-id="43c86-124">In the following example, there are nested classes and namespaces.</span></span> <span data-ttu-id="43c86-125">Il nome completo è indicato come commento dopo ogni entità.</span><span class="sxs-lookup"><span data-stu-id="43c86-125">The fully qualified name is indicated as a comment following each entity.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 <span data-ttu-id="43c86-126">Nel segmento di codice precedente:</span><span class="sxs-lookup"><span data-stu-id="43c86-126">In the previous code segment:</span></span>  
  
- <span data-ttu-id="43c86-127">Lo spazio dei nomi `N1` è un membro dello spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="43c86-127">The namespace `N1` is a member of the global namespace.</span></span> <span data-ttu-id="43c86-128">Il relativo nome completo è `N1`.</span><span class="sxs-lookup"><span data-stu-id="43c86-128">Its fully qualified name is `N1`.</span></span>  
  
- <span data-ttu-id="43c86-129">Lo spazio dei nomi `N2` è un membro di `N1`.</span><span class="sxs-lookup"><span data-stu-id="43c86-129">The namespace `N2` is a member of `N1`.</span></span> <span data-ttu-id="43c86-130">Il relativo nome completo è `N1.N2`.</span><span class="sxs-lookup"><span data-stu-id="43c86-130">Its fully qualified name is `N1.N2`.</span></span>  
  
- <span data-ttu-id="43c86-131">La classe `C1` è un membro di `N1`.</span><span class="sxs-lookup"><span data-stu-id="43c86-131">The class `C1` is a member of `N1`.</span></span> <span data-ttu-id="43c86-132">Il relativo nome completo è `N1.C1`.</span><span class="sxs-lookup"><span data-stu-id="43c86-132">Its fully qualified name is `N1.C1`.</span></span>  
  
- <span data-ttu-id="43c86-133">Il nome della classe `C2` viene usato due volte in questo codice.</span><span class="sxs-lookup"><span data-stu-id="43c86-133">The class name `C2` is used two times in this code.</span></span> <span data-ttu-id="43c86-134">Tuttavia, i nomi completi sono univoci.</span><span class="sxs-lookup"><span data-stu-id="43c86-134">However, the fully qualified names are unique.</span></span> <span data-ttu-id="43c86-135">La prima istanza di `C2` è dichiarata all'interno di `C1`, pertanto il relativo nome completo è: `N1.C1.C2`.</span><span class="sxs-lookup"><span data-stu-id="43c86-135">The first instance of `C2` is declared inside `C1`; therefore, its fully qualified name is: `N1.C1.C2`.</span></span> <span data-ttu-id="43c86-136">La seconda istanza di `C2` è dichiarata all'interno di uno spazio dei nomi `N2`, pertanto il relativo nome completo è `N1.N2.C2`.</span><span class="sxs-lookup"><span data-stu-id="43c86-136">The second instance of `C2` is declared inside a namespace `N2`; therefore, its fully qualified name is `N1.N2.C2`.</span></span>  
  
 <span data-ttu-id="43c86-137">Usando il segmento di codice precedente, è possibile aggiungere un nuovo membro della classe, `C3`, allo spazio dei nomi `N1.N2` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="43c86-137">Using the previous code segment, you can add a new class member, `C3`, to the namespace `N1.N2` as follows:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 <span data-ttu-id="43c86-138">In generale, usare il [qualificatore di alias dello spazio dei nomi `::`](../../language-reference/operators/namespace-alias-qualifier.md) per fare riferimento a un alias dello spazio dei nomi oppure `global::` per fare riferimento allo spazio dei nomi globale e `.` per qualificare i tipi o i membri.</span><span class="sxs-lookup"><span data-stu-id="43c86-138">In general, use the [namespace alias qualifier `::`](../../language-reference/operators/namespace-alias-qualifier.md) to reference a namespace alias or `global::` to reference the global namespace and `.` to qualify types or members.</span></span>  
  
 <span data-ttu-id="43c86-139">È un errore usare `::` con un alias che fa riferimento a un tipo, anziché a uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="43c86-139">It is an error to use `::` with an alias that references a type instead of a namespace.</span></span> <span data-ttu-id="43c86-140">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="43c86-140">For example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 <span data-ttu-id="43c86-141">Tenere presente che la parola `global` non è un alias predefinito, pertanto `global.X` non ha alcun significato speciale.</span><span class="sxs-lookup"><span data-stu-id="43c86-141">Remember that the word `global` is not a predefined alias; therefore, `global.X` does not have any special meaning.</span></span> <span data-ttu-id="43c86-142">Acquisisce un significato speciale solo quando viene usata con `::`.</span><span class="sxs-lookup"><span data-stu-id="43c86-142">It acquires a special meaning only when it is used with `::`.</span></span>  
  
 <span data-ttu-id="43c86-143">Se si definisce un alias denominato global, viene generato l'avviso del compilatore CS0440, perché `global::` fa sempre riferimento allo spazio dei nomi globale e non a un alias.</span><span class="sxs-lookup"><span data-stu-id="43c86-143">Compiler warning CS0440 is generated if you define an alias named global because `global::` always references the global namespace and not an alias.</span></span> <span data-ttu-id="43c86-144">Ad esempio, la riga seguente genera l'avviso:</span><span class="sxs-lookup"><span data-stu-id="43c86-144">For example, the following line generates the warning:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 <span data-ttu-id="43c86-145">L'uso di `::` con gli alias è consigliabile e garantisce la protezione contro l'introduzione imprevista di tipi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="43c86-145">Using `::` with aliases is a good idea and protects against the unexpected introduction of additional types.</span></span> <span data-ttu-id="43c86-146">Si prenda, ad esempio, in considerazione quanto segue:</span><span class="sxs-lookup"><span data-stu-id="43c86-146">For example, consider this example:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 <span data-ttu-id="43c86-147">Questo metodo funziona, ma se un tipo denominato `Alias` dovesse essere introdotto successivamente, `Alias.` sarebbe associato a tale tipo.</span><span class="sxs-lookup"><span data-stu-id="43c86-147">This works, but if a type named `Alias` were to subsequently be introduced, `Alias.` would bind to that type instead.</span></span> <span data-ttu-id="43c86-148">L'uso di `Alias::Exception` assicura che `Alias` sia trattato come un alias di spazio dei nomi e non venga erroneamente considerato un tipo.</span><span class="sxs-lookup"><span data-stu-id="43c86-148">Using `Alias::Exception` ensures that `Alias` is treated as a namespace alias and not mistaken for a type.</span></span>  

## <a name="see-also"></a><span data-ttu-id="43c86-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43c86-149">See also</span></span>

- [<span data-ttu-id="43c86-150">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="43c86-150">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="43c86-151">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="43c86-151">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="43c86-152">Espressione di accesso ai membri</span><span class="sxs-lookup"><span data-stu-id="43c86-152">Member access expression</span></span>](../../language-reference/operators/member-access-operators.md#member-access-expression-)
- [<span data-ttu-id="43c86-153">:: (operatore)</span><span class="sxs-lookup"><span data-stu-id="43c86-153">:: operator</span></span>](../../language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="43c86-154">extern alias</span><span class="sxs-lookup"><span data-stu-id="43c86-154">extern alias</span></span>](../../language-reference/keywords/extern-alias.md)
