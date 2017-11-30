---
title: Direttiva using (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 02c50b1e7a54d776985b60570c898e7d0739c44c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="7eea0-102">Direttiva using (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7eea0-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="7eea0-103">La direttiva `using` ha tre usi:</span><span class="sxs-lookup"><span data-stu-id="7eea0-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="7eea0-104">Consentire l'uso di tipi in uno spazio dei nomi in modo da non dover qualificare l'uso di un tipo in tale spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="7eea0-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="7eea0-105">Consentire l'accesso ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="7eea0-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="7eea0-106">Per altre informazioni, vedere la [direttiva using static](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="7eea0-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="7eea0-107">Creare un alias per uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="7eea0-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="7eea0-108">Si tratta di una *direttiva alias using*.</span><span class="sxs-lookup"><span data-stu-id="7eea0-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="7eea0-109">La parola chiave `using` viene usata anche per creare *istruzioni using*, che garantiscono che gli oggetti <xref:System.IDisposable>, ad esempio file e tipi di carattere, vengano gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="7eea0-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="7eea0-110">Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7eea0-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="7eea0-111">Tipo using static</span><span class="sxs-lookup"><span data-stu-id="7eea0-111">Using Static Type</span></span>  
 <span data-ttu-id="7eea0-112">È possibile accedere ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo:</span><span class="sxs-lookup"><span data-stu-id="7eea0-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="7eea0-113">Note</span><span class="sxs-lookup"><span data-stu-id="7eea0-113">Remarks</span></span>  
 <span data-ttu-id="7eea0-114">L'ambito di una direttiva `using` è limitato al file in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="7eea0-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="7eea0-115">Creare un alias `using` per semplificare la qualifica di un identificatore in uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="7eea0-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="7eea0-116">La parte destra di una direttiva alias deve essere sempre un tipo completo indipendentemente dalle direttive using che lo precedono.</span><span class="sxs-lookup"><span data-stu-id="7eea0-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="7eea0-117">Creare una direttiva `using` per usare i tipi in uno spazio dei nomi senza dover specificare tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7eea0-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="7eea0-118">Una direttiva `using` non offre accesso ad alcuno spazio dei nomi annidato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="7eea0-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="7eea0-119">Gli spazi dei nomi sono disponibili in due categorie: definiti dall'utente e definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="7eea0-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="7eea0-120">Gli spazi dei nomi definiti dall'utente vengono definiti nel codice.</span><span class="sxs-lookup"><span data-stu-id="7eea0-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="7eea0-121">Per un elenco degli spazi dei nomi definiti dal sistema, vedere [Cenni preliminari sulla libreria di classe di .NET Framework](../../../standard/class-library-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7eea0-121">For a list of the system-defined namespaces, see [.NET Framework Class Library Overview](../../../standard/class-library-overview.md).</span></span>  
  
 <span data-ttu-id="7eea0-122">Per esempi relativi a metodi di altri assembly di riferimento, vedere [creare e utilizzare assembly dalla riga di comando](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="7eea0-122">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="7eea0-123">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="7eea0-123">Example 1</span></span>  
  
 <span data-ttu-id="7eea0-124">Nell'esempio seguente viene illustrato come definire e usare un alias `using` per uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="7eea0-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="7eea0-125">Una direttiva alias using non può contenere un tipo generico aperto nella parte destra.</span><span class="sxs-lookup"><span data-stu-id="7eea0-125">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="7eea0-126">Ad esempio, non è possibile creare un alias using per List\<T>, ma è possibile crearne uno per List\<int>.</span><span class="sxs-lookup"><span data-stu-id="7eea0-126">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="7eea0-127">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="7eea0-127">Example 2</span></span>  
  
 <span data-ttu-id="7eea0-128">Nell'esempio seguente viene illustrato come definire una direttiva `using` e un alias `using` per una classe:</span><span class="sxs-lookup"><span data-stu-id="7eea0-128">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="7eea0-129">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7eea0-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7eea0-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eea0-130">See Also</span></span>  
 [<span data-ttu-id="7eea0-131">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="7eea0-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7eea0-132">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7eea0-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7eea0-133">Uso degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="7eea0-133">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
 [<span data-ttu-id="7eea0-134">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="7eea0-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7eea0-135">Parole chiave per gli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="7eea0-135">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="7eea0-136">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="7eea0-136">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
 [<span data-ttu-id="7eea0-137">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="7eea0-137">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
