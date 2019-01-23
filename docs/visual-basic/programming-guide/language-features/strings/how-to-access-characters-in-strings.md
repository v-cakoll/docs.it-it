---
title: 'Procedura: Accesso caratteri delle stringhe in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 9833b562fc0b4115448ebefb8631f0d73eb15f6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618922"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="c0f4d-102">Procedura: Accesso caratteri delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0f4d-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="c0f4d-103">In questo esempio viene illustrato come utilizzare il <xref:System.String.Chars%2A> proprietà a cui accedere il carattere in corrispondenza della posizione specificata in una stringa.</span><span class="sxs-lookup"><span data-stu-id="c0f4d-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0f4d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0f4d-104">Example</span></span>  
 <span data-ttu-id="c0f4d-105">Talvolta è utile disporre di dati relativi ai caratteri di una stringa e le posizioni di tali caratteri all'interno della stringa.</span><span class="sxs-lookup"><span data-stu-id="c0f4d-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="c0f4d-106">È possibile pensare a una stringa come una matrice di caratteri (`Char` istanze); è possibile recuperare un carattere specifico facendo riferimento all'indice del carattere desiderato tramite il <xref:System.String.Chars%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c0f4d-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 <span data-ttu-id="c0f4d-107">Il `index` parametro il <xref:System.String.Chars%2A> proprietà è in base zero.</span><span class="sxs-lookup"><span data-stu-id="c0f4d-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c0f4d-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="c0f4d-108">Robust Programming</span></span>  
 <span data-ttu-id="c0f4d-109">Il <xref:System.String.Chars%2A> proprietà restituisce il carattere in corrispondenza della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="c0f4d-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="c0f4d-110">Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere.</span><span class="sxs-lookup"><span data-stu-id="c0f4d-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="c0f4d-111">Per altre informazioni su come usare i caratteri Unicode, vedere [come: Convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="c0f4d-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="c0f4d-112">Il <xref:System.String.Chars%2A> proprietà genera un' <xref:System.IndexOutOfRangeException> eccezione se il `index` parametro è maggiore o uguale alla lunghezza della stringa, o se è minore di zero</span><span class="sxs-lookup"><span data-stu-id="c0f4d-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0f4d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f4d-113">See also</span></span>
- <xref:System.String.Chars%2A>
- [<span data-ttu-id="c0f4d-114">Procedura: Convertire una stringa in una matrice di caratteri</span><span class="sxs-lookup"><span data-stu-id="c0f4d-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="c0f4d-115">Conversione tra stringhe e altri tipi di dati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c0f4d-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="c0f4d-116">Stringhe</span><span class="sxs-lookup"><span data-stu-id="c0f4d-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
