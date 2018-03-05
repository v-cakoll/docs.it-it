---
title: 'Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a><span data-ttu-id="bbe77-102">Procedura: Eseguire la ricerca di stringhe tramite espressioni regolari (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bbe77-102">How to: Search Strings Using Regular Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="bbe77-103">La classe <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> può essere usata per eseguire la ricerca di stringhe.</span><span class="sxs-lookup"><span data-stu-id="bbe77-103">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class can be used to search strings.</span></span> <span data-ttu-id="bbe77-104">Queste ricerche possono avere livelli di complessità molto diversi, da molto semplici a casi in cui vengono usate espressioni regolari.</span><span class="sxs-lookup"><span data-stu-id="bbe77-104">These searches can range in complexity from very simple to making full use of regular expressions.</span></span> <span data-ttu-id="bbe77-105">Di seguito sono riportati due esempi di ricerca di stringhe tramite la classe <xref:System.Text.RegularExpressions.Regex>.</span><span class="sxs-lookup"><span data-stu-id="bbe77-105">The following are two examples of string searching by using the <xref:System.Text.RegularExpressions.Regex> class.</span></span> <span data-ttu-id="bbe77-106">Per altre informazioni, vedere [Espressioni regolari di .NET Framework](https://msdn.microsoft.com/library/hs600312).</span><span class="sxs-lookup"><span data-stu-id="bbe77-106">For more information, see [.NET Framework Regular Expressions](https://msdn.microsoft.com/library/hs600312).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbe77-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbe77-107">Example</span></span>  
 <span data-ttu-id="bbe77-108">Il codice seguente è un'applicazione console che esegue una semplice ricerca di stringhe in una matrice, senza distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="bbe77-108">The following code is a console application that performs a simple case-insensitive search of the strings in an array.</span></span> <span data-ttu-id="bbe77-109">Il metodo statico <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> esegue la ricerca in base alla stringa da cercare e a una stringa contenente i criteri di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bbe77-109">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> performs the search given the string to search and a string that contains the search pattern.</span></span> <span data-ttu-id="bbe77-110">In questo caso viene usato un terzo argomento per indicare che la distinzione tra lettere maiuscole e minuscole deve essere ignorata.</span><span class="sxs-lookup"><span data-stu-id="bbe77-110">In this case, a third argument is used to indicate that case should be ignored.</span></span> <span data-ttu-id="bbe77-111">Per altre informazioni, vedere <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bbe77-111">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="bbe77-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbe77-112">Example</span></span>  
 <span data-ttu-id="bbe77-113">Il codice seguente rappresenta un'applicazione console che usa le espressioni regolari per convalidare il formato di ogni stringa in una matrice.</span><span class="sxs-lookup"><span data-stu-id="bbe77-113">The following code is a console application that uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="bbe77-114">Per la convalida è necessario che ogni stringa abbia il formato di un numero di telefono costituito da tre gruppi di cifre separate da trattini, di cui i primi due gruppi contengono tre cifre e il terzo ne contiene quattro.</span><span class="sxs-lookup"><span data-stu-id="bbe77-114">The validation requires that each string take the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="bbe77-115">A tale scopo viene usata l'espressione regolare `^\\d{3}-\\d{3}-\\d{4}$`.</span><span class="sxs-lookup"><span data-stu-id="bbe77-115">This is done by using the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="bbe77-116">Per altre informazioni, vedere [Linguaggio di espressioni regolari - Riferimento rapido](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span><span class="sxs-lookup"><span data-stu-id="bbe77-116">For more information, see [Regular Expression Language - Quick Reference](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).</span></span>  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="bbe77-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbe77-117">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [<span data-ttu-id="bbe77-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bbe77-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bbe77-119">Stringhe</span><span class="sxs-lookup"><span data-stu-id="bbe77-119">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="bbe77-120">Espressioni regolari di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bbe77-120">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)  
 [<span data-ttu-id="bbe77-121">Linguaggio di espressioni regolari - Riferimento rapido</span><span class="sxs-lookup"><span data-stu-id="bbe77-121">Regular Expression Language - Quick Reference</span></span>](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)
