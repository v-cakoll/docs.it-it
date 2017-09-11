---
title: "Procedura: restituire sottoinsiemi di proprietà degli elementi in una query (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
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
ms.openlocfilehash: de6f4f1aeb07d7878d02b4f51e6f42b69d0bdcf5
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="7bfd4-102">Procedura: restituire sottoinsiemi di proprietà degli elementi in una query (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="7bfd4-102">How to: Return Subsets of Element Properties in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="7bfd4-103">Usare un tipo anonimo in un'espressione di query quando si verificano entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7bfd4-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
-   <span data-ttu-id="7bfd4-104">Si vogliono restituire solo alcune delle proprietà di ogni elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="7bfd4-104">You want to return only some of the properties of each source element.</span></span>  
  
-   <span data-ttu-id="7bfd4-105">Non è necessario archiviare la query all'esterno dell'ambito del metodo in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="7bfd4-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="7bfd4-106">Se si vuole restituire solo una proprietà o un campo da ogni elemento di origine, è sufficiente usare l'operatore punto nella clausola `select`.</span><span class="sxs-lookup"><span data-stu-id="7bfd4-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="7bfd4-107">Per restituire, ad esempio, solo l'`ID` di ogni `student`, scrivere la clausola `select` come segue:</span><span class="sxs-lookup"><span data-stu-id="7bfd4-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="7bfd4-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bfd4-108">Example</span></span>  
 <span data-ttu-id="7bfd4-109">Nell'esempio seguente viene illustrato come usare un tipo anonimo per restituire solo un sottoinsieme delle proprietà di ogni elemento di origine che corrisponde alla condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="7bfd4-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 <span data-ttu-id="7bfd4-110">[!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7bfd4-110">[!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]</span></span>  
  
 <span data-ttu-id="7bfd4-111">Si noti che se per le proprietà non è specificato alcun nome, il tipo anonimo usa i nomi dell'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="7bfd4-111">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="7bfd4-112">Per assegnare nuovi nomi alle proprietà nel tipo anonimo, scrivere l'istruzione `select` come segue:</span><span class="sxs-lookup"><span data-stu-id="7bfd4-112">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="7bfd4-113">Se si tenta questa operazione nell'esempio precedente, è necessario modificare anche l'istruzione `Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="7bfd4-113">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7bfd4-114">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7bfd4-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="7bfd4-115">Per eseguire questo codice, copiare e incollare la classe in un progetto di applicazione console di Visual C# creato in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7bfd4-115">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="7bfd4-116">Per impostazione predefinita, questo progetto usa la versione 3.5 di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] e contiene un riferimento a System.Core.dll e una direttiva `using` per System.Linq.</span><span class="sxs-lookup"><span data-stu-id="7bfd4-116">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it will have a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="7bfd4-117">Se uno o più di questi requisiti non sono presenti nel progetto, è possibile aggiungerli manualmente.</span><span class="sxs-lookup"><span data-stu-id="7bfd4-117">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="7bfd4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bfd4-118">See Also</span></span>  
 <span data-ttu-id="7bfd4-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7bfd4-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7bfd4-120">[Tipi anonimi](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="7bfd4-120">[Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) </span></span>  
 [<span data-ttu-id="7bfd4-121">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="7bfd4-121">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)

