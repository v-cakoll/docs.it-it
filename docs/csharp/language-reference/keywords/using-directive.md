---
title: Direttiva using (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 1ed7ac49cde6792cddff898e8b9930a83598e02c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45594750"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="b88dc-102">Direttiva using (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b88dc-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="b88dc-103">La direttiva `using` ha tre usi:</span><span class="sxs-lookup"><span data-stu-id="b88dc-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="b88dc-104">Consentire l'uso di tipi in uno spazio dei nomi in modo da non dover qualificare l'uso di un tipo in tale spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="b88dc-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="b88dc-105">Consentire l'accesso ai membri statici e ai tipi nidificati di un tipo senza dover qualificare l'accesso con il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="b88dc-105">To allow you to access static members and nested types of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="b88dc-106">Per altre informazioni, vedere la [direttiva using static](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="b88dc-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="b88dc-107">Creare un alias per uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="b88dc-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="b88dc-108">Si tratta di una *direttiva alias using*.</span><span class="sxs-lookup"><span data-stu-id="b88dc-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="b88dc-109">La parola chiave `using` viene usata anche per creare *istruzioni using*, che garantiscono che gli oggetti <xref:System.IDisposable>, ad esempio file e tipi di carattere, vengano gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="b88dc-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="b88dc-110">Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b88dc-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="b88dc-111">Tipo using static</span><span class="sxs-lookup"><span data-stu-id="b88dc-111">Using Static Type</span></span>  
 <span data-ttu-id="b88dc-112">È possibile accedere ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo:</span><span class="sxs-lookup"><span data-stu-id="b88dc-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="b88dc-113">Note</span><span class="sxs-lookup"><span data-stu-id="b88dc-113">Remarks</span></span>  
 <span data-ttu-id="b88dc-114">L'ambito di una direttiva `using` è limitato al file in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="b88dc-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>
 
 <span data-ttu-id="b88dc-115">La direttiva `using` può essere visualizzata:</span><span class="sxs-lookup"><span data-stu-id="b88dc-115">The `using` directive can appear:</span></span>
- <span data-ttu-id="b88dc-116">All'inizio del file del codice sorgente, prima di eventuali definizioni di spazio dei nomi o tipo.</span><span class="sxs-lookup"><span data-stu-id="b88dc-116">At the beginning of a source code file, before any namespace or type definitions.</span></span>
- <span data-ttu-id="b88dc-117">In qualsiasi spazio dei nomi, ma prima di un spazio dei nomi o di tipi dichiarati nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b88dc-117">In any namespace, but before any namespace or types declared in this namespace.</span></span>

<span data-ttu-id="b88dc-118">In caso contrario, viene generato l'errore del compilatore [CS1529](../../misc/cs1529.md).</span><span class="sxs-lookup"><span data-stu-id="b88dc-118">Otherwise, compiler error [CS1529](../../misc/cs1529.md) is generated.</span></span>
  
 <span data-ttu-id="b88dc-119">Creare una direttiva alias `using` per semplificare la qualifica di un identificatore in uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="b88dc-119">Create a `using` alias directive to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="b88dc-120">In una direttiva `using` è necessario usare lo spazio dei nomi o il tipo completo indipendentemente dalle direttive `using` che la precedono.</span><span class="sxs-lookup"><span data-stu-id="b88dc-120">In any `using` directive, the fully-qualified namespace or type must be used regardless of the `using` directives that come before it.</span></span> <span data-ttu-id="b88dc-121">Non è possibile usare alcun alias `using` nella dichiarazione di una direttiva `using`.</span><span class="sxs-lookup"><span data-stu-id="b88dc-121">No `using` alias can be used in the declaration of a `using` directive.</span></span> <span data-ttu-id="b88dc-122">Ad esempio, il codice seguente genera un errore del compilatore:</span><span class="sxs-lookup"><span data-stu-id="b88dc-122">For example, the following generates a compiler error:</span></span>
 ```csharp
 using s = System.Text;
 using s.RegularExpressions; 
 ```
  
 <span data-ttu-id="b88dc-123">Creare una direttiva `using` per usare i tipi in uno spazio dei nomi senza dover specificare tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b88dc-123">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="b88dc-124">Una direttiva `using` non offre accesso ad alcuno spazio dei nomi annidato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="b88dc-124">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="b88dc-125">Gli spazi dei nomi sono disponibili in due categorie: definiti dall'utente e definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="b88dc-125">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="b88dc-126">Gli spazi dei nomi definiti dall'utente vengono definiti nel codice.</span><span class="sxs-lookup"><span data-stu-id="b88dc-126">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="b88dc-127">Per un elenco di spazi dei nomi definiti dal sistema, vedere [Browser API .NET](https://docs.microsoft.com/en-us/dotnet/api/).</span><span class="sxs-lookup"><span data-stu-id="b88dc-127">For a list of the system-defined namespaces, see [.NET API Browser](https://docs.microsoft.com/en-us/dotnet/api/).</span></span>  
  
 <span data-ttu-id="b88dc-128">Per esempi relativi ai metodi di riferimento in altri assembly, vedere [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md) (Creazione e uso degli assembly usando la riga di comando).</span><span class="sxs-lookup"><span data-stu-id="b88dc-128">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="b88dc-129">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="b88dc-129">Example 1</span></span>  
  
 <span data-ttu-id="b88dc-130">Nell'esempio seguente viene illustrato come definire e usare un alias `using` per uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="b88dc-130">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="b88dc-131">Una direttiva alias using non può contenere un tipo generico aperto nella parte destra.</span><span class="sxs-lookup"><span data-stu-id="b88dc-131">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="b88dc-132">Ad esempio, non è possibile creare un alias using per List\<T>, ma è possibile crearne uno per List\<int>.</span><span class="sxs-lookup"><span data-stu-id="b88dc-132">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="b88dc-133">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="b88dc-133">Example 2</span></span>  
  
 <span data-ttu-id="b88dc-134">Nell'esempio seguente viene illustrato come definire una direttiva `using` e un alias `using` per una classe:</span><span class="sxs-lookup"><span data-stu-id="b88dc-134">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b88dc-135">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b88dc-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b88dc-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b88dc-136">See Also</span></span>

- [<span data-ttu-id="b88dc-137">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b88dc-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b88dc-138">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b88dc-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b88dc-139">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="b88dc-139">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
- [<span data-ttu-id="b88dc-140">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b88dc-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="b88dc-141">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="b88dc-141">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="b88dc-142">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="b88dc-142">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
- [<span data-ttu-id="b88dc-143">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="b88dc-143">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
