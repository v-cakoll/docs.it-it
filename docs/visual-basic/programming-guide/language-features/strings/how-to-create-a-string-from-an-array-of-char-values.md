---
title: 'Procedura: Creare una stringa da una matrice di valori Char (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 1f72cb86ffa38dc929062fab2f5592a781f2de27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831826"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="3ac34-102">Procedura: Creare una stringa da una matrice di valori Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ac34-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="3ac34-103">Questo esempio crea la stringa di "abcd" da singoli caratteri.</span><span class="sxs-lookup"><span data-stu-id="3ac34-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ac34-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3ac34-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ac34-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3ac34-105">Compiling the Code</span></span>  
 <span data-ttu-id="3ac34-106">Questo metodo non presenta particolari requisiti.</span><span class="sxs-lookup"><span data-stu-id="3ac34-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="3ac34-107">La sintassi `"a"c`, in cui un singolo `c` segue un singolo carattere racchiuso tra virgolette, è possibile creare un carattere letterale.</span><span class="sxs-lookup"><span data-stu-id="3ac34-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3ac34-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="3ac34-108">Robust Programming</span></span>  
 <span data-ttu-id="3ac34-109">Caratteri null (equivalente a `Chr(0)`) nella stringa di provocare risultati imprevisti quando si usa la stringa.</span><span class="sxs-lookup"><span data-stu-id="3ac34-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="3ac34-110">Il carattere null verranno incluso con la stringa, ma non verranno visualizzati caratteri che seguono il carattere null in alcune situazioni.</span><span class="sxs-lookup"><span data-stu-id="3ac34-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac34-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ac34-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="3ac34-112">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="3ac34-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="3ac34-113">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3ac34-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
