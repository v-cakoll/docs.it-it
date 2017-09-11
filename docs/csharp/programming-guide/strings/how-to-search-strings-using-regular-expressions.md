---
title: 'Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="d0ef9-102">Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="d0ef9-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="d0ef9-103">La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> può essere usata per eseguire la ricerca di stringhe.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> class can be used to search strings.</span></span> <span data-ttu-id="d0ef9-104">Queste ricerche possono avere livelli di complessità molto diversi, da molto semplici a casi in cui vengono usate espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="d0ef9-105">Di seguito sono riportati due esempi di ricerca di stringhe tramite la classe <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="d0ef9-106">Per altre informazioni, vedere [Espressioni regolari di .NET Framework](https://msdn.microsoft.com/library/hs600312).</span><span class="sxs-lookup"><span data-stu-id="d0ef9-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0ef9-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0ef9-107">Example</span></span>  
 <span data-ttu-id="d0ef9-108">Il codice seguente è un'applicazione console che esegue una semplice ricerca di stringhe in una matrice, senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="d0ef9-109">Il metodo statico <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> esegue la ricerca in base alla stringa da cercare e a una stringa contenente i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="d0ef9-110">In questo caso viene usato un terzo argomento per indicare che la distinzione tra lettere maiuscole e minuscole deve essere ignorata.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="d0ef9-111">Per altre informazioni, vedere <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="d0ef9-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d0ef9-112">[!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0ef9-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0ef9-113">Example</span></span>  
 <span data-ttu-id="d0ef9-114">Il codice seguente rappresenta un'applicazione console che usa le espressioni regolari per convalidare il formato di ogni stringa in una matrice.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-114">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="d0ef9-115">Per la convalida è necessario che ogni stringa abbia il formato di un numero di telefono costituito da tre gruppi di cifre separate da trattini, di cui i primi due gruppi contengono tre cifre e il terzo ne contiene quattro.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-115">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="d0ef9-116">A tale scopo viene usata l'espressione regolare `^\\d{3}-\\d{3}-\\d{4}$`.</span><span class="sxs-lookup"><span data-stu-id="d0ef9-116">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="d0ef9-117">Per altre informazioni, vedere [Linguaggio di espressioni regolari - Riferimento rapido](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span><span class="sxs-lookup"><span data-stu-id="d0ef9-117">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 <span data-ttu-id="d0ef9-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d0ef9-118">[!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ef9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0ef9-119">See Also</span></span>  
 <span data-ttu-id="d0ef9-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d0ef9-120"><xref:System.Text.RegularExpressions.Regex?displayProperty=fullName></span></span>   
 <span data-ttu-id="d0ef9-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0ef9-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d0ef9-122">[Stringhe](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0ef9-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="d0ef9-123">[Espressioni regolari di .NET Framework](https://msdn.microsoft.com/library/hs600312) </span><span class="sxs-lookup"><span data-stu-id="d0ef9-123">[.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312) </span></span>  
 [<span data-ttu-id="d0ef9-124">Linguaggio di espressioni regolari - Riferimento rapido</span><span class="sxs-lookup"><span data-stu-id="d0ef9-124">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

