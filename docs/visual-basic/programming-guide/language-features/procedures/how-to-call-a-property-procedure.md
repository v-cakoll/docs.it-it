---
title: 'Procedura: chiamare una routine di proprietà'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 006961a0f1d4be6b0d52be5bc273dad9733bfe56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388699"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="80cb2-102">Procedura: chiamare una routine di proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80cb2-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="80cb2-103">È possibile chiamare una routine di proprietà archiviando un valore nella proprietà o recuperando il relativo valore.</span><span class="sxs-lookup"><span data-stu-id="80cb2-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="80cb2-104">È possibile accedere a una proprietà nello stesso modo in cui si accede a una variabile.</span><span class="sxs-lookup"><span data-stu-id="80cb2-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="80cb2-105">La routine della proprietà `Set` Archivia un valore e la relativa `Get` routine Recupera il valore.</span><span class="sxs-lookup"><span data-stu-id="80cb2-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="80cb2-106">Tuttavia, queste procedure non vengono chiamate in modo esplicito in base al nome.</span><span class="sxs-lookup"><span data-stu-id="80cb2-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="80cb2-107">È possibile utilizzare la proprietà in un'istruzione di assegnazione o in un'espressione, così come si archivia o si recupera il valore di una variabile.</span><span class="sxs-lookup"><span data-stu-id="80cb2-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="80cb2-108">Visual Basic esegue le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="80cb2-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="80cb2-109">Per chiamare la routine Get di una proprietà</span><span class="sxs-lookup"><span data-stu-id="80cb2-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="80cb2-110">Usare il nome della proprietà in un'espressione nello stesso modo in cui si usa un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="80cb2-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="80cb2-111">È possibile usare una proprietà ovunque sia possibile usare una variabile o una costante.</span><span class="sxs-lookup"><span data-stu-id="80cb2-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="80cb2-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="80cb2-112">-or-</span></span>  
  
     <span data-ttu-id="80cb2-113">Usare il nome della proprietà che segue il `=` segno di uguale () in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="80cb2-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="80cb2-114">Nell'esempio seguente viene letto il valore della <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> proprietà, chiamando in modo implicito la relativa `Get` routine.</span><span class="sxs-lookup"><span data-stu-id="80cb2-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="80cb2-115">Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="80cb2-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="80cb2-116">Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.</span><span class="sxs-lookup"><span data-stu-id="80cb2-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="80cb2-117">Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="80cb2-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="80cb2-118">Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="80cb2-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="80cb2-119">Il valore della proprietà partecipa all'espressione come una variabile o una costante oppure viene archiviato nella variabile o nella proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="80cb2-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="80cb2-120">Per chiamare la routine set di una proprietà</span><span class="sxs-lookup"><span data-stu-id="80cb2-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="80cb2-121">Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="80cb2-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="80cb2-122">Nell'esempio seguente viene impostato il valore della <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> proprietà, chiamando in modo implicito la `Set` routine.</span><span class="sxs-lookup"><span data-stu-id="80cb2-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="80cb2-123">Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="80cb2-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="80cb2-124">Se non è presente alcun argomento, è possibile omettere facoltativamente le parentesi.</span><span class="sxs-lookup"><span data-stu-id="80cb2-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="80cb2-125">Inserire gli argomenti nell'elenco di argomenti tra parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="80cb2-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="80cb2-126">Assicurarsi di specificare gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="80cb2-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="80cb2-127">Il valore generato sul lato destro dell'istruzione di assegnazione viene archiviato nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="80cb2-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cb2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80cb2-128">See also</span></span>

- [<span data-ttu-id="80cb2-129">Routine Property</span><span class="sxs-lookup"><span data-stu-id="80cb2-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="80cb2-130">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="80cb2-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="80cb2-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="80cb2-131">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="80cb2-132">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80cb2-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="80cb2-133">Procedura: creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="80cb2-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="80cb2-134">Procedura: dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="80cb2-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="80cb2-135">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80cb2-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="80cb2-136">Procedura: inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="80cb2-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="80cb2-137">Procedura: ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="80cb2-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="80cb2-138">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="80cb2-138">Get Statement</span></span>](../../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="80cb2-139">Istruzione set</span><span class="sxs-lookup"><span data-stu-id="80cb2-139">Set Statement</span></span>](../../../language-reference/statements/set-statement.md)
