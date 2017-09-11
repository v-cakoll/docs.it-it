---
title: "Procedura: inserire un valore in una proprietà (Visual Basic) | Documenti di Microsoft"
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
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
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
ms.openlocfilehash: c838141a27c30b11765d30ae8b0c19bccc929f4b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="0e9bb-102">Procedura: inserire un valore in una proprietà (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e9bb-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="0e9bb-103">Archiviare un valore in una proprietà inserendo il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="0e9bb-104">La proprietà `Set` procedure archivia un valore, ma non viene chiamato esplicitamente in base al nome.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="0e9bb-105">Utilizzare la proprietà esattamente come si utilizzerebbe una variabile.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0e9bb-106">effettua le chiamate alle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="0e9bb-107">Per archiviare un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="0e9bb-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="0e9bb-108">Utilizzare il nome della proprietà sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="0e9bb-109">Nell'esempio seguente imposta il valore della [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` proprietà mezzogiorno, la chiamata in modo implicito il `Set` procedura.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-109">The following example sets the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     <span data-ttu-id="0e9bb-110">[!code-vb[VbVbcnProcedures&#11;](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0e9bb-110">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="0e9bb-111">Se la proprietà accetta argomenti, seguire il nome della proprietà con le parentesi per racchiudere l'elenco di argomenti.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-111">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="0e9bb-112">Se non sono presenti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-112">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="0e9bb-113">Inserire gli argomenti nell'elenco di argomenti all'interno delle parentesi, separati da virgole.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-113">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="0e9bb-114">Assicurarsi di inserire gli argomenti nello stesso ordine in cui la proprietà definisce i parametri corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-114">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="0e9bb-115">Il valore generato sul lato destro dell'istruzione di assegnazione è archiviato nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-115">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9bb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e9bb-116">See Also</span></span>  
 <span data-ttu-id="0e9bb-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="0e9bb-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span></span>   
<span data-ttu-id="0e9bb-118"> [Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-118"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="0e9bb-119"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-119"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="0e9bb-120"> [Property (istruzione)](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-120"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="0e9bb-121"> [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-121"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="0e9bb-122"> [Procedura: creare una proprietà](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-122"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="0e9bb-123"> [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-123"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="0e9bb-124"> [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-124"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="0e9bb-125"> [Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="0e9bb-125"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="0e9bb-126"> [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="0e9bb-126"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
