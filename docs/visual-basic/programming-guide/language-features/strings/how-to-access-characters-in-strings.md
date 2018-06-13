---
title: 'Procedura: accedere ai caratteri delle stringhe in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 48507cade639660e6ce36697975d09fb29206c20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649152"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="60947-102">Procedura: accedere ai caratteri delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60947-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="60947-103">In questo esempio viene illustrato come utilizzare il <xref:System.String.Chars%2A> proprietà per accedere al carattere nella posizione specificata in una stringa.</span><span class="sxs-lookup"><span data-stu-id="60947-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60947-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="60947-104">Example</span></span>  
 <span data-ttu-id="60947-105">Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni dei caratteri all'interno della stringa.</span><span class="sxs-lookup"><span data-stu-id="60947-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="60947-106">È possibile considerare una stringa come matrice di caratteri (`Char` istanze); è possibile recuperare un particolare carattere facendo riferimento all'indice di tale carattere mediante il <xref:System.String.Chars%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="60947-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 <span data-ttu-id="60947-107">Il `index` parametro il <xref:System.String.Chars%2A> proprietà è in base zero.</span><span class="sxs-lookup"><span data-stu-id="60947-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="60947-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="60947-108">Robust Programming</span></span>  
 <span data-ttu-id="60947-109">Il <xref:System.String.Chars%2A> proprietà restituisce il carattere in corrispondenza della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="60947-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="60947-110">Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere.</span><span class="sxs-lookup"><span data-stu-id="60947-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="60947-111">Per ulteriori informazioni su come utilizzare i caratteri Unicode, vedere [procedura: convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="60947-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="60947-112">Il <xref:System.String.Chars%2A> proprietà genera un <xref:System.IndexOutOfRangeException> eccezione se il `index` parametro è maggiore o uguale alla lunghezza della stringa, o se è minore di zero</span><span class="sxs-lookup"><span data-stu-id="60947-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60947-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60947-113">See Also</span></span>  
 <xref:System.String.Chars%2A>  
 [<span data-ttu-id="60947-114">Procedura: Convertire una stringa in una matrice di caratteri</span><span class="sxs-lookup"><span data-stu-id="60947-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [<span data-ttu-id="60947-115">Conversione tra stringhe e altri tipi di dati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60947-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [<span data-ttu-id="60947-116">Stringhe</span><span class="sxs-lookup"><span data-stu-id="60947-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
