---
title: "Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic | Documenti di Microsoft"
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
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
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
ms.openlocfilehash: 7cfd476def67ccf46e524da7943680f9e34b6a26
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="a8149-102">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8149-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="a8149-103">Oggetto *predefiniti delle proprietà* è una proprietà di classe o struttura che il codice può accedere senza specificarla.</span><span class="sxs-lookup"><span data-stu-id="a8149-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="a8149-104">Quando il codice chiamante assegna una classe o struttura ma non una proprietà e il contesto consente l'accesso a una proprietà, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] risolve l'accesso a tale classe o una proprietà predefinita della struttura, se presente.</span><span class="sxs-lookup"><span data-stu-id="a8149-104">When calling code names a class or structure but not a property, and the context allows access to a property, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="a8149-105">Una classe o struttura può avere al massimo una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="a8149-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="a8149-106">Tuttavia, è possibile eseguire l'overload di una proprietà predefinita e dispone di più di una versione di esso.</span><span class="sxs-lookup"><span data-stu-id="a8149-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="a8149-107">Per ulteriori informazioni, vedere [predefinito](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="a8149-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="a8149-108">Per dichiarare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="a8149-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="a8149-109">Dichiarare le proprietà in modo normale.</span><span class="sxs-lookup"><span data-stu-id="a8149-109">Declare the property in the normal way.</span></span> <span data-ttu-id="a8149-110">Non si specifica il `Shared` o `Private` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="a8149-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="a8149-111">Includere il `Default` parola chiave nella dichiarazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8149-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="a8149-112">Specificare almeno un parametro per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8149-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="a8149-113">È possibile definire una proprietà predefinita che non accetta almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="a8149-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     <span data-ttu-id="a8149-114">[!code-vb[VbVbcnProcedures n.&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-114">[!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span></span>  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="a8149-115">Per chiamare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="a8149-115">To call a default property</span></span>  
  
1.  <span data-ttu-id="a8149-116">Dichiarare una variabile di tipo classe o struttura che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="a8149-116">Declare a variable of the containing class or structure type.</span></span>  
  
     <span data-ttu-id="a8149-117">[!code-vb[VbVbcnProcedures&#16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-117">[!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span></span>  
  
2.  <span data-ttu-id="a8149-118">Utilizzare il nome della variabile da solo in un'espressione in cui è in genere necessario includere il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8149-118">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     <span data-ttu-id="a8149-119">[!code-vb[VbVbcnProcedures numero&21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-119">[!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span></span>  
  
3.  <span data-ttu-id="a8149-120">Seguire il nome della variabile con un elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="a8149-120">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="a8149-121">Una proprietà predefinita deve accettare almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="a8149-121">A default property must take at least one argument.</span></span>  
  
     <span data-ttu-id="a8149-122">[!code-vb[VbVbcnProcedures&#20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-122">[!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span></span>  
  
4.  <span data-ttu-id="a8149-123">Per recuperare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti, in un'espressione o in seguito uguali (`=`) accedere in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="a8149-123">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="a8149-124">[!code-vb[VbVbcnProcedures&#15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-124">[!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span></span>  
  
5.  <span data-ttu-id="a8149-125">Per impostare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti, sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="a8149-125">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="a8149-126">[!code-vb[VbVbcnProcedures&#14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-126">[!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span></span>  
  
6.  <span data-ttu-id="a8149-127">È sempre possibile specificare il nome della proprietà predefinita con il nome della variabile, così come si farebbe per accedere a qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8149-127">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     <span data-ttu-id="a8149-128">[!code-vb[&#19; VbVbcnProcedures](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-128">[!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8149-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8149-129">Example</span></span>  
 <span data-ttu-id="a8149-130">Nell'esempio seguente dichiara una proprietà predefinita in una classe.</span><span class="sxs-lookup"><span data-stu-id="a8149-130">The following example declares a default property on a class.</span></span>  
  
 <span data-ttu-id="a8149-131">[!code-vb[VbVbcnProcedures&#12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-131">[!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8149-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="a8149-132">Example</span></span>  
 <span data-ttu-id="a8149-133">Nell'esempio seguente viene illustrato come chiamare la proprietà predefinita `myProperty` sulla classe `class1`.</span><span class="sxs-lookup"><span data-stu-id="a8149-133">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="a8149-134">Le istruzioni di assegnazione di tre valori memorizzati in `myProperty`e <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>chiamata legge i valori.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="a8149-134">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 <span data-ttu-id="a8149-135">[!code-vb[13 VbVbcnProcedures](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8149-135">[!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span></span>  
  
 <span data-ttu-id="a8149-136">L'utilizzo più comune di una proprietà predefinita è la <xref:Microsoft.VisualBasic.Collection.Item%2A>proprietà in varie classi di raccolta.</xref:Microsoft.VisualBasic.Collection.Item%2A></span><span class="sxs-lookup"><span data-stu-id="a8149-136">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a8149-137">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="a8149-137">Robust Programming</span></span>  
 <span data-ttu-id="a8149-138">Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma può rendere il codice più difficili da leggere.</span><span class="sxs-lookup"><span data-stu-id="a8149-138">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="a8149-139">Se il codice chiamante non ha familiarità con la classe o struttura, quando fa riferimento al nome di classe o struttura non può essere determinato se il riferimento accede la classe o struttura o una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="a8149-139">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="a8149-140">Ciò può causare errori del compilatore o meno evidenti della logica di runtime.</span><span class="sxs-lookup"><span data-stu-id="a8149-140">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="a8149-141">Piuttosto, è possibile ridurre il rischio di errori di proprietà predefiniti utilizzando sempre la [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo di compilatore controllo `On`.</span><span class="sxs-lookup"><span data-stu-id="a8149-141">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="a8149-142">Se si intende utilizzare una classe predefinita o una struttura nel codice, è necessario determinare se esiste una proprietà predefinita e in tal caso, il relativo nome novità.</span><span class="sxs-lookup"><span data-stu-id="a8149-142">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="a8149-143">A causa di questi svantaggi, è consigliabile non definire le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="a8149-143">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="a8149-144">Per la leggibilità del codice, si deve anche considerare fare sempre riferimento a tutte le proprietà in modo esplicito, incluse quelle predefinite.</span><span class="sxs-lookup"><span data-stu-id="a8149-144">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8149-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8149-145">See Also</span></span>  
 <span data-ttu-id="a8149-146">[Proprietà (routine)](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-146">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="a8149-147"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-147"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="a8149-148"> [Property (istruzione)](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-148"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="a8149-149"> [Impostazione predefinita](../../../../visual-basic/language-reference/modifiers/default.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-149"> [Default](../../../../visual-basic/language-reference/modifiers/default.md) </span></span>  
<span data-ttu-id="a8149-150"> [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-150"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="a8149-151"> [Procedura: creare una proprietà](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-151"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="a8149-152"> [Procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-152"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="a8149-153"> [Procedura: chiamare una routine di proprietà](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-153"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="a8149-154"> [Procedura: inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="a8149-154"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="a8149-155"> [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="a8149-155"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
