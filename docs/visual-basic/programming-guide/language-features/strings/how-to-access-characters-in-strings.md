---
title: 'Procedura: accedere ai caratteri delle stringhe'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352468"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="de4c7-102">Procedura: accedere ai caratteri delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="de4c7-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="de4c7-103">Questo esempio illustra come usare la proprietà <xref:System.String.Chars%2A> per accedere al carattere in corrispondenza della posizione specificata in una stringa.</span><span class="sxs-lookup"><span data-stu-id="de4c7-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de4c7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="de4c7-104">Example</span></span>  
 <span data-ttu-id="de4c7-105">A volte è utile avere dati sui caratteri nella stringa e le posizioni dei caratteri all'interno della stringa.</span><span class="sxs-lookup"><span data-stu-id="de4c7-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="de4c7-106">È possibile considerare una stringa come una matrice di caratteri (`Char` istanze); è possibile recuperare un particolare carattere facendo riferimento all'indice di tale carattere tramite la proprietà <xref:System.String.Chars%2A>.</span><span class="sxs-lookup"><span data-stu-id="de4c7-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="de4c7-107">Il parametro `index` della proprietà <xref:System.String.Chars%2A> è in base zero.</span><span class="sxs-lookup"><span data-stu-id="de4c7-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="de4c7-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="de4c7-108">Robust Programming</span></span>  
 <span data-ttu-id="de4c7-109">La proprietà <xref:System.String.Chars%2A> restituisce il carattere in corrispondenza della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="de4c7-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="de4c7-110">Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere.</span><span class="sxs-lookup"><span data-stu-id="de4c7-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="de4c7-111">Per altre informazioni su come usare i caratteri Unicode, vedere [procedura: convertire una stringa in una matrice di caratteri](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="de4c7-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="de4c7-112">La proprietà <xref:System.String.Chars%2A> genera un'eccezione <xref:System.IndexOutOfRangeException> se il parametro `index` è maggiore o uguale alla lunghezza della stringa o se è minore di zero</span><span class="sxs-lookup"><span data-stu-id="de4c7-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4c7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="de4c7-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="de4c7-114">Procedura: Convertire una stringa in una matrice di caratteri</span><span class="sxs-lookup"><span data-stu-id="de4c7-114">How to: Convert a String to an Array of Characters</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="de4c7-115">Conversione tra stringhe e altri tipi di dati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="de4c7-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="de4c7-116">Stringhe</span><span class="sxs-lookup"><span data-stu-id="de4c7-116">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
