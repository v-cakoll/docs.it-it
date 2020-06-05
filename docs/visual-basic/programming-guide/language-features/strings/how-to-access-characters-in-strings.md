---
title: 'Procedura: accedere ai caratteri delle stringhe'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: fa5920cfd25f61f6e6c7d5438ef7c0e38a48fa1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401953"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a><span data-ttu-id="8c870-102">Procedura: accedere ai caratteri delle stringhe in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c870-102">How to: Access Characters in Strings in Visual Basic</span></span>
<span data-ttu-id="8c870-103">Questo esempio illustra come usare la <xref:System.String.Chars%2A> proprietà per accedere al carattere in corrispondenza della posizione specificata in una stringa.</span><span class="sxs-lookup"><span data-stu-id="8c870-103">This example demonstrates how to use the <xref:System.String.Chars%2A> property to access the character at the specified location in a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c870-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c870-104">Example</span></span>  
 <span data-ttu-id="8c870-105">A volte è utile avere dati sui caratteri nella stringa e le posizioni dei caratteri all'interno della stringa.</span><span class="sxs-lookup"><span data-stu-id="8c870-105">Sometimes it is useful to have data about the characters in your string and the positions of those characters within your string.</span></span> <span data-ttu-id="8c870-106">È possibile considerare una stringa come una matrice di caratteri ( `Char` istanze); è possibile recuperare un particolare carattere facendo riferimento all'indice di tale carattere tramite la <xref:System.String.Chars%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="8c870-106">You can think of a string as an array of characters (`Char` instances); you can retrieve a particular character by referencing the index of that character through the <xref:System.String.Chars%2A> property.</span></span>  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <span data-ttu-id="8c870-107">Il `index` parametro della <xref:System.String.Chars%2A> proprietà è in base zero.</span><span class="sxs-lookup"><span data-stu-id="8c870-107">The `index` parameter of the <xref:System.String.Chars%2A> property is zero-based.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8c870-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="8c870-108">Robust Programming</span></span>  
 <span data-ttu-id="8c870-109">La <xref:System.String.Chars%2A> proprietà restituisce il carattere in corrispondenza della posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="8c870-109">The <xref:System.String.Chars%2A> property returns the character at the specified position.</span></span> <span data-ttu-id="8c870-110">Tuttavia, alcuni caratteri Unicode possono essere rappresentati da più di un carattere.</span><span class="sxs-lookup"><span data-stu-id="8c870-110">However, some Unicode characters can be represented by more than one character.</span></span> <span data-ttu-id="8c870-111">Per altre informazioni su come usare i caratteri Unicode, vedere [procedura: convertire una stringa in una matrice di caratteri](how-to-convert-a-string-to-an-array-of-characters.md).</span><span class="sxs-lookup"><span data-stu-id="8c870-111">For more information on how to work with Unicode characters, see [How to: Convert a String to an Array of Characters](how-to-convert-a-string-to-an-array-of-characters.md).</span></span>  
  
 <span data-ttu-id="8c870-112">La <xref:System.String.Chars%2A> proprietà genera un' <xref:System.IndexOutOfRangeException> eccezione se il `index` parametro è maggiore o uguale alla lunghezza della stringa o se è minore di zero.</span><span class="sxs-lookup"><span data-stu-id="8c870-112">The <xref:System.String.Chars%2A> property throws an <xref:System.IndexOutOfRangeException> exception if the `index` parameter is greater than or equal to the length of the string, or if it is less than zero</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c870-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c870-113">See also</span></span>

- <xref:System.String.Chars%2A>
- [<span data-ttu-id="8c870-114">Procedura: convertire una stringa in una matrice di caratteri</span><span class="sxs-lookup"><span data-stu-id="8c870-114">How to: Convert a String to an Array of Characters</span></span>](how-to-convert-a-string-to-an-array-of-characters.md)
- [<span data-ttu-id="8c870-115">Conversione tra stringhe e altri tipi di dati in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8c870-115">Converting Between Strings and Other Data Types in Visual Basic</span></span>](converting-between-strings-and-other-data-types.md)
- [<span data-ttu-id="8c870-116">Stringhe</span><span class="sxs-lookup"><span data-stu-id="8c870-116">Strings</span></span>](index.md)
