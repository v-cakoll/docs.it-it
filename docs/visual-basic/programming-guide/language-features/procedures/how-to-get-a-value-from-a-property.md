---
title: "Procedura: ottenere un valore da una proprietà (Visual Basic) | Documenti di Microsoft"
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
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
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
ms.openlocfilehash: 719a4fc9ff163fb4437ea40c8265a5e36232347e
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="7f374-102">Procedura: ottenere un valore da una proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f374-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="7f374-103">Per recuperare il valore della proprietà, includendo il nome della proprietà in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="7f374-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="7f374-104">La proprietà `Get` procedura recupera il valore, ma non viene chiamato esplicitamente in base al nome.</span><span class="sxs-lookup"><span data-stu-id="7f374-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="7f374-105">Utilizzare la proprietà esattamente come si utilizzerebbe una variabile.</span><span class="sxs-lookup"><span data-stu-id="7f374-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7f374-106">effettua le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7f374-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="7f374-107">Per recuperare un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="7f374-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="7f374-108">Utilizzare il nome della proprietà in un'espressione simile a quello è necessario utilizzare un nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="7f374-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="7f374-109">È possibile utilizzare una proprietà in qualsiasi punto è possibile utilizzare una variabile o costante.</span><span class="sxs-lookup"><span data-stu-id="7f374-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="7f374-110">-oppure-</span><span class="sxs-lookup"><span data-stu-id="7f374-110">-or-</span></span>  
  
     <span data-ttu-id="7f374-111">Utilizzare il nome della proprietà seguente uguali (`=`) accedere in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7f374-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="7f374-112">Nell'esempio seguente viene letto il valore della [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` proprietà, in modo implicito chiamando il relativo `Get` procedura.</span><span class="sxs-lookup"><span data-stu-id="7f374-112">The following example reads the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="7f374-113">[!code-vb[VbVbalrDateProperties n.&4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7f374-113">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="7f374-114">Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="7f374-114">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7f374-115">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="7f374-115">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="7f374-116">Inserire gli argomenti nell'elenco di argomenti all'interno delle parentesi, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="7f374-116">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7f374-117">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="7f374-117">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="7f374-118">Il valore della proprietà fa parte dell'espressione come una variabile o costante viene archiviato nella variabile o proprietà sul lato sinistro dell'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7f374-118">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f374-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f374-119">See Also</span></span>  
 <span data-ttu-id="7f374-120">[Procedure](./index.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-120">[Procedures](./index.md) </span></span>  
<span data-ttu-id="7f374-121"> [Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="7f374-122"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-122"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="7f374-123"> [Property (istruzione)](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-123"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="7f374-124"> [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-124"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="7f374-125"> [Procedura: creare una proprietà](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-125"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="7f374-126"> [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-126"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="7f374-127"> [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-127"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="7f374-128"> [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="7f374-128"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="7f374-129"> [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="7f374-129"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md)</span></span>
