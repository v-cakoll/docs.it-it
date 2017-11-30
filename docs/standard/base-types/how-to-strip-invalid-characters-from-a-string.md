---
title: 'Procedura: Rimuovere caratteri non validi da una stringa'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- cleaning input
- user input, examples
- .NET Framework regular expressions, examples
- regular expressions [.NET Framework], examples
- Regex.Replace method
- stripping invalid characters
- Replace method
- validating user input
ms.assetid: b4319c8a-9032-4129-a9d5-6f6fc28e7f32
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f676ca9121498da7c88cdec8b49586bde91b181
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-strip-invalid-characters-from-a-string"></a><span data-ttu-id="bf981-102">Procedura: Rimuovere caratteri non validi da una stringa</span><span class="sxs-lookup"><span data-stu-id="bf981-102">How to: Strip Invalid Characters from a String</span></span>
<span data-ttu-id="bf981-103">L'esempio seguente usa il metodo statico <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> metodo per rimuovere i caratteri non validi da una stringa.</span><span class="sxs-lookup"><span data-stu-id="bf981-103">The following example uses the static <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> method to strip invalid characters from a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf981-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bf981-104">Example</span></span>  
 <span data-ttu-id="bf981-105">È possibile usare il metodo `CleanInput` definito in questo esempio per rimuovere i caratteri potenzialmente dannosi che sono stati inseriti in un campo di testo che accetta l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="bf981-105">You can use the `CleanInput` method defined in this example to strip potentially harmful characters that have been entered into a text field that accepts user input.</span></span> <span data-ttu-id="bf981-106">In questo caso, `CleanInput` rimuove tutti i caratteri non alfanumerici tranne punto (.), simboli "at" (@) e trattini (-) e restituisce la stringa restante.</span><span class="sxs-lookup"><span data-stu-id="bf981-106">In this case, `CleanInput` strips out all nonalphanumeric characters except periods (.), at symbols (@), and hyphens (-), and returns the remaining string.</span></span> <span data-ttu-id="bf981-107">È tuttavia possibile modificare l'espressione regolare in modo che rimuova i caratteri che non devono essere inclusi in una stringa di input.</span><span class="sxs-lookup"><span data-stu-id="bf981-107">However, you can modify the regular expression pattern so that it strips out any characters that should not be included in an input string.</span></span>  
  
 [!code-csharp[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/cs/Example.cs#1)]
 [!code-vb[RegularExpressions.Examples.StripChars#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.StripChars/vb/Example.vb#1)]  
  
 <span data-ttu-id="bf981-108">Il criterio di espressione regolare `[^\w\.@-]` corrisponde a qualsiasi carattere che non è un carattere alfanumerico, un punto, un simbolo @ o un trattino.</span><span class="sxs-lookup"><span data-stu-id="bf981-108">The regular expression pattern `[^\w\.@-]` matches any character that is not a word character, a period, an @ symbol, or a hyphen.</span></span> <span data-ttu-id="bf981-109">Un carattere alfanumerico è qualsiasi lettera, numero decimale o connettore di punteggiatura, ad esempio un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="bf981-109">A word character is any letter, decimal digit, or punctuation connector such as an underscore.</span></span> <span data-ttu-id="bf981-110">Qualsiasi carattere che corrisponde a questo modello viene sostituito da <xref:System.String.Empty?displayProperty=nameWithType>, ovvero la stringa definita dal modello di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="bf981-110">Any character that matches this pattern is replaced by <xref:System.String.Empty?displayProperty=nameWithType>, which is the string defined by the replacement pattern.</span></span> <span data-ttu-id="bf981-111">Per consentire ulteriori caratteri nell'input dell'utente, aggiungere tali caratteri alla classe di caratteri nel criterio di espressione regolare.</span><span class="sxs-lookup"><span data-stu-id="bf981-111">To allow additional characters in user input, add those characters to the character class in the regular expression pattern.</span></span> <span data-ttu-id="bf981-112">Ad esempio, il criterio di espressione regolare `[^\w\.@-\\%]` consente inoltre di un simbolo di percentuale e una barra rovesciata nella stringa di input.</span><span class="sxs-lookup"><span data-stu-id="bf981-112">For example, the regular expression pattern `[^\w\.@-\\%]` also allows a percentage symbol and a backslash in an input string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf981-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf981-113">See Also</span></span>  
 [<span data-ttu-id="bf981-114">Espressioni regolari di .NET</span><span class="sxs-lookup"><span data-stu-id="bf981-114">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
