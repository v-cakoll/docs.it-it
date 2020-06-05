---
title: 'Procedura: ottenere un valore da una proprietà'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 2c92cd4a869acbb7c8c52fbf4117112967386498
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387894"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="22166-102">Procedura: ottenere un valore da una proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22166-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="22166-103">Per recuperare il valore di una proprietà, è necessario includere il nome della proprietà in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="22166-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="22166-104">La routine della proprietà `Get` Recupera il valore, ma non lo chiama in modo esplicito in base al nome.</span><span class="sxs-lookup"><span data-stu-id="22166-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="22166-105">Usare la proprietà esattamente come si farebbe per usare una variabile.</span><span class="sxs-lookup"><span data-stu-id="22166-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="22166-106">Visual Basic esegue le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="22166-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="22166-107">Per recuperare un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="22166-107">To retrieve a value from a property</span></span>  
  
1. <span data-ttu-id="22166-108">Usare il nome della proprietà in un'espressione nello stesso modo in cui si usa un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="22166-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="22166-109">È possibile usare una proprietà ovunque sia possibile usare una variabile o una costante.</span><span class="sxs-lookup"><span data-stu-id="22166-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="22166-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="22166-110">-or-</span></span>  
  
     <span data-ttu-id="22166-111">Usare il nome della proprietà che segue il `=` segno di uguale () in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="22166-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="22166-112">Nell'esempio seguente viene letto il valore della `Now` proprietà Visual Basic, chiamando in modo implicito la relativa `Get` routine.</span><span class="sxs-lookup"><span data-stu-id="22166-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="22166-113">Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="22166-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="22166-114">Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.</span><span class="sxs-lookup"><span data-stu-id="22166-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="22166-115">Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="22166-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="22166-116">Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="22166-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="22166-117">Il valore della proprietà partecipa all'espressione come una variabile o una costante oppure viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="22166-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22166-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22166-118">See also</span></span>

- [<span data-ttu-id="22166-119">Procedure</span><span class="sxs-lookup"><span data-stu-id="22166-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="22166-120">Routine Property</span><span class="sxs-lookup"><span data-stu-id="22166-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="22166-121">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="22166-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="22166-122">Property Statement</span><span class="sxs-lookup"><span data-stu-id="22166-122">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="22166-123">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22166-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="22166-124">Procedura: creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="22166-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="22166-125">Procedura: dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="22166-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="22166-126">Procedura: chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="22166-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="22166-127">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="22166-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="22166-128">Procedura: inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="22166-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
