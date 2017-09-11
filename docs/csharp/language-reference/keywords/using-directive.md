---
title: Direttiva using (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1129efd8a1c4058a9648eab61f98cdcef7e9f2f7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="using-directive-c-reference"></a><span data-ttu-id="3acdd-102">Direttiva using (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3acdd-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="3acdd-103">La direttiva `using` ha tre usi:</span><span class="sxs-lookup"><span data-stu-id="3acdd-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="3acdd-104">Consentire l'uso di tipi in uno spazio dei nomi in modo da non dover qualificare l'uso di un tipo in tale spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="3acdd-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="3acdd-105">Consentire l'accesso ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="3acdd-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="3acdd-106">Per altre informazioni, vedere la [direttiva using static](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="3acdd-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="3acdd-107">Creare un alias per uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="3acdd-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="3acdd-108">Si tratta di una *direttiva alias using*.</span><span class="sxs-lookup"><span data-stu-id="3acdd-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="3acdd-109">La parola chiave `using` viene usata anche per creare *istruzioni using*, che garantiscono che gli oggetti <xref:System.IDisposable>, ad esempio file e tipi di carattere, vengano gestiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="3acdd-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="3acdd-110">Per altre informazioni, vedere [Istruzione using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3acdd-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="3acdd-111">Tipo using static</span><span class="sxs-lookup"><span data-stu-id="3acdd-111">Using Static Type</span></span>  
 <span data-ttu-id="3acdd-112">È possibile accedere ai membri statici di un tipo senza dover qualificare l'accesso con il nome del tipo:</span><span class="sxs-lookup"><span data-stu-id="3acdd-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="3acdd-113">Note</span><span class="sxs-lookup"><span data-stu-id="3acdd-113">Remarks</span></span>  
 <span data-ttu-id="3acdd-114">L'ambito di una direttiva `using` è limitato al file in cui viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3acdd-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="3acdd-115">Creare un alias `using` per semplificare la qualifica di un identificatore in uno spazio dei nomi o un tipo.</span><span class="sxs-lookup"><span data-stu-id="3acdd-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="3acdd-116">La parte destra di una direttiva alias deve essere sempre un tipo completo indipendentemente dalle direttive using che lo precedono.</span><span class="sxs-lookup"><span data-stu-id="3acdd-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="3acdd-117">Creare una direttiva `using` per usare i tipi in uno spazio dei nomi senza dover specificare tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3acdd-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="3acdd-118">Una direttiva `using` non offre accesso ad alcuno spazio dei nomi annidato nello spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="3acdd-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="3acdd-119">Gli spazi dei nomi sono disponibili in due categorie: definiti dall'utente e definiti dal sistema.</span><span class="sxs-lookup"><span data-stu-id="3acdd-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="3acdd-120">Gli spazi dei nomi definiti dall'utente vengono definiti nel codice.</span><span class="sxs-lookup"><span data-stu-id="3acdd-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="3acdd-121">Per un elenco di spazi dei nomi definiti dal sistema, vedere [Libreria di classi di .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195).</span><span class="sxs-lookup"><span data-stu-id="3acdd-121">For a list of the system-defined namespaces, see [.NET Framework Class Library](http://go.microsoft.com/fwlink/?LinkID=227195).</span></span>  
  
 <span data-ttu-id="3acdd-122">Per esempi relativi ai metodi di riferimento in altri assembly, vedere [Creazione e uso di DLL C#](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span><span class="sxs-lookup"><span data-stu-id="3acdd-122">For examples on referencing methods in other assemblies, see [Creating and Using C# DLLs](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="3acdd-123">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="3acdd-123">Example 1</span></span>  
  
 <span data-ttu-id="3acdd-124">Nell'esempio seguente viene illustrato come definire e usare un alias `using` per uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3acdd-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 <span data-ttu-id="3acdd-125">[!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3acdd-125">[!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]</span></span>  
  
 <span data-ttu-id="3acdd-126">Una direttiva alias using non può contenere un tipo generico aperto nella parte destra.</span><span class="sxs-lookup"><span data-stu-id="3acdd-126">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="3acdd-127">Ad esempio, non è possibile creare un alias using per List\<T>, ma è possibile crearne uno per List\<int>.</span><span class="sxs-lookup"><span data-stu-id="3acdd-127">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="3acdd-128">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="3acdd-128">Example 2</span></span>  
  
 <span data-ttu-id="3acdd-129">Nell'esempio seguente viene illustrato come definire una direttiva `using` e un alias `using` per una classe:</span><span class="sxs-lookup"><span data-stu-id="3acdd-129">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 <span data-ttu-id="3acdd-130">[!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3acdd-130">[!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="3acdd-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3acdd-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3acdd-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3acdd-132">See Also</span></span>  
 <span data-ttu-id="3acdd-133">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3acdd-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3acdd-134">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3acdd-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3acdd-135">[Uso degli spazi dei nomi](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="3acdd-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
 <span data-ttu-id="3acdd-136">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="3acdd-136">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="3acdd-137">[Parole chiave per gli spazi dei nomi](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="3acdd-137">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="3acdd-138">[Spazi dei nomi](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="3acdd-138">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 [<span data-ttu-id="3acdd-139">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="3acdd-139">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

