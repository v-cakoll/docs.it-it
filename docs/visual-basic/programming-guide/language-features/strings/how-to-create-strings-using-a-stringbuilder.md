---
title: 'Procedura: Creare stringhe usando StringBuilder in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 5cd118ddd196bdf84045ae8b02fe590e5b087e4e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967958"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="bfc26-102">Procedura: Creare stringhe usando StringBuilder in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bfc26-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="bfc26-103">Questo esempio si costruisce una stringa lunga da molte stringhe più piccole mediante il <xref:System.Text.StringBuilder> classe.</span><span class="sxs-lookup"><span data-stu-id="bfc26-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="bfc26-104">Il <xref:System.Text.StringBuilder> classe risulta più efficiente il `&=` operatore per concatenano più stringhe.</span><span class="sxs-lookup"><span data-stu-id="bfc26-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfc26-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="bfc26-105">Example</span></span>  
 <span data-ttu-id="bfc26-106">L'esempio seguente crea un'istanza di <xref:System.Text.StringBuilder> (classe), aggiunge le stringhe di 1.000 a tale istanza e quindi restituisce una rappresentazione di stringa.</span><span class="sxs-lookup"><span data-stu-id="bfc26-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]  
  
## <a name="see-also"></a><span data-ttu-id="bfc26-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfc26-107">See also</span></span>
- [<span data-ttu-id="bfc26-108">Uso della classe StringBuilder</span><span class="sxs-lookup"><span data-stu-id="bfc26-108">Using the StringBuilder Class</span></span>](../../../../standard/base-types/stringbuilder.md)
- [<span data-ttu-id="bfc26-109">Operatore &=</span><span class="sxs-lookup"><span data-stu-id="bfc26-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="bfc26-110">Stringhe</span><span class="sxs-lookup"><span data-stu-id="bfc26-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="bfc26-111">Creazione di nuove stringhe</span><span class="sxs-lookup"><span data-stu-id="bfc26-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="bfc26-112">Modifica di stringhe</span><span class="sxs-lookup"><span data-stu-id="bfc26-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
