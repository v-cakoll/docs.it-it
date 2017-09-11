---
title: 'Procedura: Analizzare le stringhe con String.Split (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- splitting strings [C#]
- Split method [C#]
- strings [C#], splitting
- parse strings
ms.assetid: 729c2923-4169-41c6-9c90-ef176c1e2953
caps.latest.revision: 17
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
ms.sourcegitcommit: d74c1d0760d4e776c2cf4c7dea1dac060c85a83c
ms.openlocfilehash: e25dbf6b86c82808622377c0618cd956541c6e09
ms.contentlocale: it-it
ms.lasthandoff: 09/05/2017

---
# <a name="how-to-parse-strings-using-stringsplit-c-programming-guide"></a><span data-ttu-id="c739c-102">Procedura: Analizzare le stringhe con String.Split (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c739c-102">How to: Parse Strings Using String.Split (C# Programming Guide)</span></span>
<span data-ttu-id="c739c-103">L'esempio di codice seguente mostra come analizzare una stringa con il metodo <xref:System.String.Split%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="c739c-103">The following code example demonstrates how a string can be parsed using the <xref:System.String.Split%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="c739c-104"><xref:System.String.Split%2A> accetta come input una matrice di caratteri che indica quali caratteri separano le sottostringhe rilevanti della stringa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c739c-104">As input, <xref:System.String.Split%2A> takes an array of characters that indicate which characters separate interesting sub strings of the target string.</span></span>  <span data-ttu-id="c739c-105">La funzione restituisce una matrice di sottostringhe.</span><span class="sxs-lookup"><span data-stu-id="c739c-105">The function returns an array of the sub strings.</span></span>  
  
 <span data-ttu-id="c739c-106">Questo esempio usa spazi, virgole, punti, due punti e tabulazioni, tutti passati in una matrice che contiene questi caratteri di separazione per <xref:System.String.Split%2A>.</span><span class="sxs-lookup"><span data-stu-id="c739c-106">This example uses spaces, commas, periods, colons, and tabs, all passed in an array containing these separating characters to <xref:System.String.Split%2A>.</span></span>  <span data-ttu-id="c739c-107">Ogni parola nella frase della stringa di destinazione viene visualizzata separatamente rispetto alla matrice di stringhe risultante.</span><span class="sxs-lookup"><span data-stu-id="c739c-107">Each word in the target string's sentence displays separately from the resulting array of strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c739c-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c739c-108">Example</span></span>  
 <span data-ttu-id="c739c-109">[!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c739c-109">[!code-cs[csProgGuideStrings#16](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-parse-strings-using-string-split_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="c739c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="c739c-110">Example</span></span>  
 <span data-ttu-id="c739c-111">Per impostazione predefinita, String.Split restituisce stringhe vuote quando vengono visualizzati due caratteri di separazione adiacenti nella stringa di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c739c-111">By default, String.Split returns empty strings when two separating characters appear contiguously in the target string.</span></span>  <span data-ttu-id="c739c-112">È possibile passare un parametro facoltativo StringSplitOptions.RemoveEmptyEntries per escludere le stringhe vuote nell'output.</span><span class="sxs-lookup"><span data-stu-id="c739c-112">You can pass an optional StringSplitOptions.RemoveEmptyEntries parameter to exclude any empty strings in the output.</span></span>  
  
 <span data-ttu-id="c739c-113">String.Split può accettare una matrice di stringhe (sequenze di caratteri, al posto di caratteri singoli, che fungono da separatori per l'analisi della stringa di destinazione).</span><span class="sxs-lookup"><span data-stu-id="c739c-113">String.Split can take an array of strings (character sequences that act as separators for parsing the target string, instead of single characters).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c739c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c739c-114">See Also</span></span>  
 <span data-ttu-id="c739c-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c739c-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c739c-116">[Stringhe](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="c739c-116">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 [<span data-ttu-id="c739c-117">Espressioni regolari di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c739c-117">.NET Framework Regular Expressions</span></span>](https://msdn.microsoft.com/library/hs600312)

