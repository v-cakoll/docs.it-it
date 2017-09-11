---
title: 'Procedura: chiamare una routine (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d0d37fc2b7ae1d563a7e9d0a8e75343dd690089b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="e8976-102">Procedura: chiamare una routine di proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8976-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="e8976-103">Chiamare una routine di proprietà mediante l'archiviazione di un valore nella proprietà o recuperarne il valore.</span><span class="sxs-lookup"><span data-stu-id="e8976-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="e8976-104">Si accede alla proprietà esattamente come si accede a una variabile.</span><span class="sxs-lookup"><span data-stu-id="e8976-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="e8976-105">La proprietà `Set` procedura archivia un valore e il relativo `Get` procedura recupera il valore.</span><span class="sxs-lookup"><span data-stu-id="e8976-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="e8976-106">Tuttavia, non chiamare in modo esplicito queste procedure in base al nome.</span><span class="sxs-lookup"><span data-stu-id="e8976-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="e8976-107">Utilizzare la proprietà in un'istruzione di assegnazione o un'espressione, così come viene archiviato o recuperare il valore di una variabile.</span><span class="sxs-lookup"><span data-stu-id="e8976-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="e8976-108">effettua le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e8976-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="e8976-109">Per chiamare routine Get della proprietà</span><span class="sxs-lookup"><span data-stu-id="e8976-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="e8976-110">Utilizzare il nome della proprietà in un'espressione simile a quello è necessario utilizzare un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="e8976-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="e8976-111">È possibile utilizzare una proprietà in qualsiasi punto è possibile utilizzare una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="e8976-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="e8976-112">-oppure-</span><span class="sxs-lookup"><span data-stu-id="e8976-112">-or-</span></span>  
  
     <span data-ttu-id="e8976-113">Utilizzare il nome della proprietà seguente uguali (`=`) accedere in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e8976-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="e8976-114">Nell'esempio seguente viene letto il valore della <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>proprietà, in modo implicito chiamando il relativo `Get` procedura.</xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="e8976-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="e8976-115">[!code-vb[VbVbalrDateProperties n.&4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8976-115">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="e8976-116">Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="e8976-116">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e8976-117">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="e8976-117">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="e8976-118">Inserire gli argomenti nell'elenco di argomenti all'interno delle parentesi, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="e8976-118">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e8976-119">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e8976-119">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="e8976-120">Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e8976-120">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="e8976-121">Per chiamare una proprietà dell'insieme di procedure</span><span class="sxs-lookup"><span data-stu-id="e8976-121">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="e8976-122">Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e8976-122">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="e8976-123">Nell'esempio seguente imposta il valore della <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>proprietà, in modo implicito la chiamata di `Set` procedura.</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="e8976-123">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     <span data-ttu-id="e8976-124">[!code-vb[VbVbcnProcedures&#11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e8976-124">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span></span>  
  
2.  <span data-ttu-id="e8976-125">Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="e8976-125">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e8976-126">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="e8976-126">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="e8976-127">Inserire gli argomenti nell'elenco di argomenti all'interno delle parentesi, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="e8976-127">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e8976-128">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="e8976-128">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="e8976-129">Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="e8976-129">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8976-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8976-130">See Also</span></span>  
 <span data-ttu-id="e8976-131">[Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-131">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="e8976-132"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="e8976-133"> [Property (istruzione)](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-133"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="e8976-134"> [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-134"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="e8976-135"> [Procedura: creare una proprietà](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-135"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="e8976-136"> [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-136"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="e8976-137"> [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-137"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="e8976-138"> [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-138"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="e8976-139"> [Procedura: ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-139"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md) </span></span>  
<span data-ttu-id="e8976-140"> [Get (istruzione)](../../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e8976-140"> [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="e8976-141"> [Istruzione Set](../../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="e8976-141"> [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
