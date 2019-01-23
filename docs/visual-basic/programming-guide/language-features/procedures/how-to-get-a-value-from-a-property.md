---
title: 'Procedura: Ottenere un valore da una proprietà (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 356230a0b5a2c575ee554ce7f2cdb4a2f741ecac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543370"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="7a961-102">Procedura: Ottenere un valore da una proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a961-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="7a961-103">Per recuperare un valore della proprietà di includere il nome della proprietà in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7a961-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="7a961-104">La proprietà `Get` procedura recupera il valore, ma è non chiamare in modo esplicito in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7a961-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="7a961-105">Utilizzare la proprietà esattamente come si utilizzerebbe una variabile.</span><span class="sxs-lookup"><span data-stu-id="7a961-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="7a961-106">Visual Basic effettua le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7a961-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="7a961-107">Per recuperare un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="7a961-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="7a961-108">Usare il nome della proprietà in un'espressione simile a quello è necessario usare un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="7a961-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="7a961-109">È possibile usare una proprietà in qualsiasi punto è possibile usare una variabile o una costante.</span><span class="sxs-lookup"><span data-stu-id="7a961-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="7a961-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7a961-110">-or-</span></span>  
  
     <span data-ttu-id="7a961-111">Usare il nome della proprietà seguente uguali (`=`) Accedi a un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7a961-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="7a961-112">Nell'esempio seguente legge il valore di Visual Basic `Now` proprietà, chiamare in modo implicito il `Get` procedure.</span><span class="sxs-lookup"><span data-stu-id="7a961-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  <span data-ttu-id="7a961-113">Se la proprietà accetta argomenti, seguire il nome della proprietà tra parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="7a961-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7a961-114">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="7a961-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="7a961-115">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="7a961-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7a961-116">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7a961-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="7a961-117">Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7a961-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a961-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a961-118">See also</span></span>
- [<span data-ttu-id="7a961-119">Routine</span><span class="sxs-lookup"><span data-stu-id="7a961-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="7a961-120">Routine Property</span><span class="sxs-lookup"><span data-stu-id="7a961-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="7a961-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="7a961-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7a961-122">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="7a961-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="7a961-123">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a961-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="7a961-124">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="7a961-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="7a961-125">Procedura: Dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="7a961-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="7a961-126">Procedura: Chiamare una routine Property</span><span class="sxs-lookup"><span data-stu-id="7a961-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="7a961-127">Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a961-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="7a961-128">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="7a961-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
