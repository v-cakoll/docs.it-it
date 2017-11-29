---
title: "Procedura: chiamare una routine di proprietà (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cf9080e3c2b23302257499f13e734231f3614495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="e4547-102">Procedura: chiamare una routine di proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4547-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="e4547-103">Per chiamare una routine di proprietà per archiviare un valore nella proprietà o recuperarne il valore.</span><span class="sxs-lookup"><span data-stu-id="e4547-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="e4547-104">Si accede alla proprietà allo stesso modo accedere a una variabile.</span><span class="sxs-lookup"><span data-stu-id="e4547-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="e4547-105">La proprietà `Set` routine memorizza un valore e il relativo `Get` procedura recupera il valore.</span><span class="sxs-lookup"><span data-stu-id="e4547-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="e4547-106">Tuttavia, non chiamare in modo esplicito queste procedure in base al nome.</span><span class="sxs-lookup"><span data-stu-id="e4547-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="e4547-107">Utilizzare la proprietà in un'istruzione di assegnazione o un'espressione, così come viene archiviato o recuperare il valore di una variabile.</span><span class="sxs-lookup"><span data-stu-id="e4547-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="e4547-108">effettua le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e4547-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="e4547-109">Per chiamare routine Get di una proprietà</span><span class="sxs-lookup"><span data-stu-id="e4547-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="e4547-110">Utilizzare il nome della proprietà in un'espressione esattamente come si utilizzerebbe un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="e4547-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="e4547-111">È possibile utilizzare una proprietà in qualsiasi punto è possibile utilizzare una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="e4547-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="e4547-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e4547-112">-or-</span></span>  
  
     <span data-ttu-id="e4547-113">Utilizzare il nome della proprietà seguente uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e4547-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="e4547-114">Nell'esempio seguente viene letto il valore della <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> proprietà, la chiamata in modo implicito il `Get` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="e4547-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  <span data-ttu-id="e4547-115">Se la proprietà accetta argomenti, dopo il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="e4547-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e4547-116">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="e4547-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="e4547-117">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="e4547-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e4547-118">Assicurarsi che fornire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e4547-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="e4547-119">Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e4547-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="e4547-120">Per chiamare una proprietà dell'insieme di procedure</span><span class="sxs-lookup"><span data-stu-id="e4547-120">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="e4547-121">Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e4547-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="e4547-122">Nell'esempio seguente imposta il valore della <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> proprietà, la chiamata in modo implicito il `Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="e4547-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  <span data-ttu-id="e4547-123">Se la proprietà accetta argomenti, dopo il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="e4547-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e4547-124">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="e4547-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="e4547-125">Posizionare gli argomenti nell'elenco di argomenti all'interno delle parentesi, separate da virgole.</span><span class="sxs-lookup"><span data-stu-id="e4547-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e4547-126">Assicurarsi che fornire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e4547-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="e4547-127">Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="e4547-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4547-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4547-128">See Also</span></span>  
 [<span data-ttu-id="e4547-129">Routine Property</span><span class="sxs-lookup"><span data-stu-id="e4547-129">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="e4547-130">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="e4547-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="e4547-131">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="e4547-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="e4547-132">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4547-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="e4547-133">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="e4547-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="e4547-134">Procedura: Dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="e4547-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="e4547-135">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4547-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="e4547-136">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="e4547-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="e4547-137">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="e4547-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)  
 [<span data-ttu-id="e4547-138">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="e4547-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="e4547-139">Istruzione Set</span><span class="sxs-lookup"><span data-stu-id="e4547-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
