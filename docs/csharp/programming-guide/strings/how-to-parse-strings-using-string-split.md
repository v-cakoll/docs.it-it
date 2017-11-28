---
title: 'Procedura: Analizzare le stringhe con String.Split (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7b97d1d89a4c74a4c759d1ed41a0bc2476b3b07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a><span data-ttu-id="01088-102">Procedura: Analizzare le stringhe con String.Split (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="01088-102">How to: Parse Strings Using String.Split (C# Programming Guide)</span></span>
<span data-ttu-id="01088-103">L'esempio di codice seguente mostra come analizzare una stringa con il metodo <xref:System.String.Split%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="01088-103">The following code example demonstrates how a string can be parsed using the <xref:System.String.Split%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="01088-104"><xref:System.String.Split%2A> accetta come input una matrice di caratteri che indica quali caratteri separano le sottostringhe rilevanti della stringa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="01088-104">As input, <xref:System.String.Split%2A> takes an array of characters that indicate which characters separate interesting sub strings of the target string.</span></span>  <span data-ttu-id="01088-105">La funzione restituisce una matrice di sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="01088-105">The function returns an array of the sub strings.</span></span>  
  
 <span data-ttu-id="01088-106">Questo esempio usa spazi, virgole, punti, due punti e tabulazioni, tutti passati in una matrice che contiene questi caratteri di separazione per <xref:System.String.Split%2A>.</span><span class="sxs-lookup"><span data-stu-id="01088-106">This example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="01088-107">Ogni parola nella frase della stringa di destinazione viene visualizzata separatamente rispetto alla matrice di stringhe risultante.</span><span class="sxs-lookup"><span data-stu-id="01088-107">Each word in the target string's sentence displays separately from the resulting array of strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01088-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="01088-108">Example</span></span>  
 [!code-csharp[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="01088-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="01088-109">Example</span></span>  
 <span data-ttu-id="01088-110">Per impostazione predefinita, String.Split restituisce stringhe vuote quando vengono visualizzati due caratteri di separazione adiacenti nella stringa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="01088-110">By default, String.Split returns empty strings when two separating characters appear contiguously in the target string.</span></span>  <span data-ttu-id="01088-111">È possibile passare un parametro facoltativo StringSplitOptions.RemoveEmptyEntries per escludere le stringhe vuote nell'output.</span><span class="sxs-lookup"><span data-stu-id="01088-111">You can pass an optional StringSplitOptions.RemoveEmptyEntries parameter to exclude any empty strings in the output.</span></span>  
  
 <span data-ttu-id="01088-112">String.Split può accettare una matrice di stringhe (sequenze di caratteri, al posto di caratteri singoli, che fungono da separatori per l'analisi della stringa di destinazione).</span><span class="sxs-lookup"><span data-stu-id="01088-112">String.Split can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
```csharp  
class TestStringSplit  
{  
    static void Main()  
    {  
        string[] separatingChars = { "<<", "..." };  
  
        string text = "one<<two......three<four";  
        System.Console.WriteLine("Original text: '{0}'", text);  
  
        string[] words = text.Split(separatingChars, System.StringSplitOptions.RemoveEmptyEntries );  
        System.Console.WriteLine("{0} substrings in text:", words.Length);  
  
        foreach (string s in words)  
        {  
            System.Console.WriteLine(s);  
        }  
  
        // Keep the console window open in debug mode.  
        System.Console.WriteLine("Press any key to exit.");  
        System.Console.ReadKey();  
    }  
}  
/* Output:  
    Original text: 'one<<two......three<four'  
    3 words in text:  
    one  
    two  
    three<four  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="01088-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01088-113">See Also</span></span>  
 [<span data-ttu-id="01088-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="01088-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="01088-115">Stringhe</span><span class="sxs-lookup"><span data-stu-id="01088-115">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="01088-116">Espressioni regolari di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="01088-116">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)
