---
title: 'Procedura: Dichiarare una proprietà con livelli di accesso misti (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: e899b57e02f492b0e4909aca84c069e5b7688618
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339814"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a><span data-ttu-id="1471f-102">Procedura: Dichiarare una proprietà con livelli di accesso misti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1471f-102">How to: Declare a Property with Mixed Access Levels (Visual Basic)</span></span>
<span data-ttu-id="1471f-103">Se si desidera che il `Get` e `Set` procedure su una proprietà per avere diversi livelli di accesso, è possibile usare il livello più ampio nel `Property` istruzione e il livello più restrittivo in entrambi il `Get` o `Set` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1471f-103">If you want the `Get` and `Set` procedures on a property to have different access levels, you can use the more permissive level in the `Property` statement and the more restrictive level in either the `Get` or `Set` statement.</span></span> <span data-ttu-id="1471f-104">Si usano livelli di accesso misti su una proprietà quando si desidera che alcune parti del codice sia in grado di ottenere il valore della proprietà e alcune altre parti del codice sia in grado di modificare il valore.</span><span class="sxs-lookup"><span data-stu-id="1471f-104">You use mixed access levels on a property when you want certain parts of the code to be able to get the property's value, and certain other parts of the code to be able to change the value.</span></span>  
  
 <span data-ttu-id="1471f-105">Per altre informazioni sui livelli di accesso, vedere [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="1471f-105">For more information on access levels, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a><span data-ttu-id="1471f-106">Per dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="1471f-106">To declare a property with mixed access levels</span></span>  
  
1. <span data-ttu-id="1471f-107">Dichiarare la proprietà in modo normale e specificare il livello di accesso meno restrittivo (ad esempio `Public`) nel `Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1471f-107">Declare the property in the normal way, and specify the less restrictive access level (such as `Public`) in the `Property` statement.</span></span>  
  
2. <span data-ttu-id="1471f-108">Dichiarare uno il `Get` o il `Set` procedura specificando il livello di accesso più restrittivo (ad esempio `Friend`).</span><span class="sxs-lookup"><span data-stu-id="1471f-108">Declare either the `Get` or the `Set` procedure specifying the more restrictive access level (such as `Friend`).</span></span>  
  
3. <span data-ttu-id="1471f-109">Non specificare un livello di accesso nella routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="1471f-109">Do not specify an access level on the other property procedure.</span></span> <span data-ttu-id="1471f-110">Presuppone che il livello di accesso dichiarato nel `Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="1471f-110">It assumes the access level declared in the `Property` statement.</span></span> <span data-ttu-id="1471f-111">È possibile limitare l'accesso solo su una delle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="1471f-111">You can restrict access on only one of the property procedures.</span></span>  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     <span data-ttu-id="1471f-112">Nell'esempio precedente, il `Get` procedure con lo stesso `Protected` accesso della proprietà stessa, mentre le `Set` routine ha `Private` accesso.</span><span class="sxs-lookup"><span data-stu-id="1471f-112">In the preceding example, the `Get` procedure has the same `Protected` access as the property itself, while the `Set` procedure has `Private` access.</span></span> <span data-ttu-id="1471f-113">Una classe derivata da `employee` può leggere il `salary` valore, ma solo il `employee` classe possibile impostarlo.</span><span class="sxs-lookup"><span data-stu-id="1471f-113">A class derived from `employee` can read the `salary` value, but only the `employee` class can set it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1471f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1471f-114">See also</span></span>

- [<span data-ttu-id="1471f-115">Procedure</span><span class="sxs-lookup"><span data-stu-id="1471f-115">Procedures</span></span>](./index.md)
- [<span data-ttu-id="1471f-116">Routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="1471f-116">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="1471f-117">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="1471f-117">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1471f-118">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1471f-118">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="1471f-119">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1471f-119">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="1471f-120">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="1471f-120">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="1471f-121">Procedura: Chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="1471f-121">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="1471f-122">Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1471f-122">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="1471f-123">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="1471f-123">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="1471f-124">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="1471f-124">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
