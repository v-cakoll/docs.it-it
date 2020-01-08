---
title: 'Procedura: creare una stringa da una matrice di valori Char'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: bf37ceba901e712df10ad4b39f9ad74194843136
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346764"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="9befb-102">Procedura: creare una stringa da una matrice di valori Char (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9befb-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>
<span data-ttu-id="9befb-103">In questo esempio viene creata la stringa "abcd" da singoli caratteri.</span><span class="sxs-lookup"><span data-stu-id="9befb-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9befb-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9befb-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="9befb-105">Compilare il codice</span><span class="sxs-lookup"><span data-stu-id="9befb-105">Compile the code</span></span>  
 <span data-ttu-id="9befb-106">Questo metodo non ha requisiti particolari.</span><span class="sxs-lookup"><span data-stu-id="9befb-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="9befb-107">La sintassi `"a"c`, in cui un singolo `c` segue un singolo carattere racchiuso tra virgolette, viene usato per creare un valore letterale carattere.</span><span class="sxs-lookup"><span data-stu-id="9befb-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9befb-108">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="9befb-108">Robust Programming</span></span>  
 <span data-ttu-id="9befb-109">I caratteri null (equivalenti a `Chr(0)`) nella stringa portano a risultati imprevisti quando si usa la stringa.</span><span class="sxs-lookup"><span data-stu-id="9befb-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="9befb-110">Il carattere null verrà incluso nella stringa, ma in alcune situazioni i caratteri che seguono il carattere null non verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="9befb-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9befb-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9befb-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="9befb-112">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="9befb-112">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="9befb-113">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9befb-113">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
