---
title: 'Procedura: convertire una stringa in una matrice di caratteri in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59d0da52c8f78b93c76325e6242156c106deeaf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a><span data-ttu-id="064d9-102">Procedura: convertire una stringa in una matrice di caratteri in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="064d9-102">How to: Convert a String to an Array of Characters in Visual Basic</span></span>
<span data-ttu-id="064d9-103">Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni dei caratteri all'interno della stringa, ad esempio quando si analizza una stringa.</span><span class="sxs-lookup"><span data-stu-id="064d9-103">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string, such as when you are parsing a string.</span></span> <span data-ttu-id="064d9-104">Questo esempio viene illustrato come è possibile ottenere una matrice di caratteri in una stringa chiamando la stringa <xref:System.String.ToCharArray%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="064d9-104">This example shows how you can get an array of the characters in a string by calling the string's <xref:System.String.ToCharArray%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="064d9-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="064d9-105">Example</span></span>  
 <span data-ttu-id="064d9-106">In questo esempio viene illustrato come suddividere una stringa in un `Char` matrice e come suddividere una stringa in un `String` matrice dei relativi caratteri di testo Unicode.</span><span class="sxs-lookup"><span data-stu-id="064d9-106">This example demonstrates how to split a string into a `Char` array, and how to split a string into a `String` array of its Unicode text characters.</span></span> <span data-ttu-id="064d9-107">Il motivo di questa distinzione è che i caratteri di testo Unicode possono essere composti da due o più `Char` caratteri (ad esempio una coppia di surrogati o una combinazione sequenza di caratteri).</span><span class="sxs-lookup"><span data-stu-id="064d9-107">The reason for this distinction is that Unicode text characters can be composed of two or more `Char` characters (such as a surrogate pair or a combining character sequence).</span></span> <span data-ttu-id="064d9-108">Per ulteriori informazioni, vedere <xref:System.Globalization.TextElementEnumerator> e "Lo Standard Unicode" indirizzo http://www.unicode.org.</span><span class="sxs-lookup"><span data-stu-id="064d9-108">For more information, see <xref:System.Globalization.TextElementEnumerator> and "The Unicode Standard" at http://www.unicode.org.</span></span>  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="064d9-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="064d9-109">Example</span></span>  
 <span data-ttu-id="064d9-110">È più difficile suddividere una stringa in relativi caratteri di testo Unicode, ma questa operazione è necessaria se sono necessarie informazioni sulla rappresentazione visiva di una stringa.</span><span class="sxs-lookup"><span data-stu-id="064d9-110">It is more difficult to split a string into its Unicode text characters, but this is necessary if you need information about the visual representation of a string.</span></span> <span data-ttu-id="064d9-111">Questo esempio viene utilizzato il <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> metodo per ottenere informazioni sui caratteri che costituiscono una stringa di testo Unicode.</span><span class="sxs-lookup"><span data-stu-id="064d9-111">This example uses the <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> method to get information about the Unicode text characters that make up a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="064d9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="064d9-112">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [<span data-ttu-id="064d9-113">Procedura: Accedere ai caratteri delle stringhe</span><span class="sxs-lookup"><span data-stu-id="064d9-113">How to: Access Characters in Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [<span data-ttu-id="064d9-114">Conversione tra stringhe e altri tipi di dati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="064d9-114">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="064d9-115">Stringhe</span><span class="sxs-lookup"><span data-stu-id="064d9-115">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
