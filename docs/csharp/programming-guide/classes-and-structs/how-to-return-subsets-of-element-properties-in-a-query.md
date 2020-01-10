---
title: Come restituire subset di proprietà degli elementi in una guida per la C# programmazione di query
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 27a2626fc46307a7195040adf746d8d8757d2f82
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714863"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="7d61c-102">Come restituire subset di proprietà degli elementi in una query (C# guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="7d61c-102">How to return subsets of element properties in a query (C# Programming Guide)</span></span>
<span data-ttu-id="7d61c-103">Usare un tipo anonimo in un'espressione di query quando si verificano entrambe le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7d61c-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
- <span data-ttu-id="7d61c-104">Si vogliono restituire solo alcune delle proprietà di ogni elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="7d61c-104">You want to return only some of the properties of each source element.</span></span>  
  
- <span data-ttu-id="7d61c-105">Non è necessario archiviare la query all'esterno dell'ambito del metodo in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="7d61c-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="7d61c-106">Se si vuole restituire solo una proprietà o un campo da ogni elemento di origine, è sufficiente usare l'operatore punto nella clausola `select`.</span><span class="sxs-lookup"><span data-stu-id="7d61c-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="7d61c-107">Per restituire, ad esempio, solo l'`ID` di ogni `student`, scrivere la clausola `select` come segue:</span><span class="sxs-lookup"><span data-stu-id="7d61c-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="7d61c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d61c-108">Example</span></span>  
 <span data-ttu-id="7d61c-109">Nell'esempio seguente viene illustrato come usare un tipo anonimo per restituire solo un sottoinsieme delle proprietà di ogni elemento di origine che corrisponde alla condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="7d61c-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 <span data-ttu-id="7d61c-110">Si noti che se per le proprietà non è specificato alcun nome, il tipo anonimo usa i nomi dell'elemento di origine.</span><span class="sxs-lookup"><span data-stu-id="7d61c-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="7d61c-111">Per assegnare nuovi nomi alle proprietà nel tipo anonimo, scrivere l'istruzione `select` come segue:</span><span class="sxs-lookup"><span data-stu-id="7d61c-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="7d61c-112">Se si tenta questa operazione nell'esempio precedente, è necessario modificare anche l'istruzione `Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="7d61c-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d61c-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="7d61c-113">Compiling the Code</span></span>  
  
<span data-ttu-id="7d61c-114">Per eseguire questo codice, copiare e incollare la classe in un'applicazione console C# con una direttiva `using` per System.Linq.</span><span class="sxs-lookup"><span data-stu-id="7d61c-114">To run this code, copy and paste the class into a C# console application  with a `using` directive for System.Linq.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d61c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d61c-115">See also</span></span>

- [<span data-ttu-id="7d61c-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7d61c-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7d61c-117">Tipi anonimi</span><span class="sxs-lookup"><span data-stu-id="7d61c-117">Anonymous Types</span></span>](./anonymous-types.md)
- [<span data-ttu-id="7d61c-118">LINQ in C#</span><span class="sxs-lookup"><span data-stu-id="7d61c-118">LINQ in C#</span></span>](../../linq/index.md)
