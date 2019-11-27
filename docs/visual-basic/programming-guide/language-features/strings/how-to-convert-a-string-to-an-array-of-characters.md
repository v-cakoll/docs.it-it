---
title: 'Procedura: convertire una stringa in una matrice di caratteri'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: d2f7128f97e576d37216d3aa9736921f13f77004
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352452"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="f35e7-102">Procedura: convertire una stringa in una matrice di caratteri in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f35e7-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="f35e7-103">A volte è utile avere dati sui caratteri nella stringa e le posizioni dei caratteri all'interno della stringa, ad esempio durante l'analisi di una stringa.</span><span class="sxs-lookup"><span data-stu-id="f35e7-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="f35e7-104">Questo esempio illustra come ottenere una matrice di caratteri in una stringa chiamando il metodo <xref:System.String.ToCharArray%2A> della stringa.</span><span class="sxs-lookup"><span data-stu-id="f35e7-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f35e7-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f35e7-105">Example</span></span>  
 <span data-ttu-id="f35e7-106">In questo esempio viene illustrato come suddividere una stringa in una matrice di `Char` e come suddividere una stringa in una matrice di `String` dei caratteri di testo Unicode.</span><span class="sxs-lookup"><span data-stu-id="f35e7-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="f35e7-107">Il motivo di questa distinzione è che i caratteri di testo Unicode possono essere composti da due o più caratteri di `Char` (ad esempio una coppia di surrogati o una sequenza di caratteri di combinazione).</span><span class="sxs-lookup"><span data-stu-id="f35e7-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="f35e7-108">Per ulteriori informazioni, vedere <xref:System.Globalization.TextElementEnumerator> e [lo standard Unicode](https://www.unicode.org/standard/standard.html).</span><span class="sxs-lookup"><span data-stu-id="f35e7-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and [The Unicode Standard](https://www.unicode.org/standard/standard.html).</span></span>  
  
 [!code-vb[VbVbalrStrings#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#75)]  
  
## <a name="example"></a><span data-ttu-id="f35e7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="f35e7-109">Example</span></span>  
 <span data-ttu-id="f35e7-110">È più difficile suddividere una stringa nei caratteri di testo Unicode, ma questa operazione è necessaria se sono necessarie informazioni sulla rappresentazione visiva di una stringa.</span><span class="sxs-lookup"><span data-stu-id="f35e7-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="f35e7-111">In questo esempio viene usato il metodo <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> per ottenere informazioni sui caratteri di testo Unicode che costituiscono una stringa.</span><span class="sxs-lookup"><span data-stu-id="f35e7-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class4.vb#76)]  
  
## <a name="see-also"></a><span data-ttu-id="f35e7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f35e7-112">See also</span></span>

- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [<span data-ttu-id="f35e7-113">Procedura: Accedere ai caratteri delle stringhe</span><span class="sxs-lookup"><span data-stu-id="f35e7-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [<span data-ttu-id="f35e7-114">Conversione tra stringhe e altri tipi di dati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f35e7-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="f35e7-115">Stringhe</span><span class="sxs-lookup"><span data-stu-id="f35e7-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
