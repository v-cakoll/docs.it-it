---
title: "Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8baa03e37325a6ad7065ec1a60052b3ea6a46c6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="7f90e-102">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f90e-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="7f90e-103">Oggetto *proprietà predefinita* è una proprietà di classe o struttura che il codice può accedere senza specificarla.</span><span class="sxs-lookup"><span data-stu-id="7f90e-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="7f90e-104">Quando la chiamata di codice i nomi di una classe o struttura ma non una proprietà e il contesto consente l'accesso a una proprietà, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] viene risolto l'accesso a tale classe o una proprietà predefinita della struttura, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="7f90e-104">When calling code names a class or structure but not a property, and the context allows access to a property, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="7f90e-105">Una classe o struttura può contenere al massimo una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="7f90e-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="7f90e-106">Tuttavia, è possibile eseguire l'overload di una proprietà predefinita e più di una versione di esso.</span><span class="sxs-lookup"><span data-stu-id="7f90e-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="7f90e-107">Per ulteriori informazioni, vedere [predefinito](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="7f90e-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="7f90e-108">Per dichiarare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="7f90e-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="7f90e-109">Dichiarare la proprietà in modo normale.</span><span class="sxs-lookup"><span data-stu-id="7f90e-109">Declare the property in the normal way.</span></span> <span data-ttu-id="7f90e-110">Non si specifica il `Shared` o `Private` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="7f90e-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="7f90e-111">Includere il `Default` parola chiave nella dichiarazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="7f90e-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="7f90e-112">Specificare almeno un parametro per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="7f90e-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="7f90e-113">È possibile definire una proprietà predefinita che non accetta almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="7f90e-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="7f90e-114">Per chiamare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="7f90e-114">To call a default property</span></span>  
  
1.  <span data-ttu-id="7f90e-115">Dichiarare una variabile del tipo di classe o struttura contenitore.</span><span class="sxs-lookup"><span data-stu-id="7f90e-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  <span data-ttu-id="7f90e-116">Utilizzare il nome della variabile da solo in un'espressione in cui è in genere necessario includere il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="7f90e-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  <span data-ttu-id="7f90e-117">Seguire il nome della variabile con un elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="7f90e-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="7f90e-118">Una proprietà predefinita deve accettare almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="7f90e-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  <span data-ttu-id="7f90e-119">Per recuperare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti, in un'espressione o in seguito uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7f90e-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  <span data-ttu-id="7f90e-120">Per impostare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7f90e-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  <span data-ttu-id="7f90e-121">È sempre possibile specificare il nome predefinito della proprietà con il nome della variabile, così come si farebbe per accedere a qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="7f90e-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="7f90e-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f90e-122">Example</span></span>  
 <span data-ttu-id="7f90e-123">Nell'esempio seguente dichiara una proprietà predefinita in una classe.</span><span class="sxs-lookup"><span data-stu-id="7f90e-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a><span data-ttu-id="7f90e-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f90e-124">Example</span></span>  
 <span data-ttu-id="7f90e-125">Nell'esempio seguente viene illustrato come chiamare la proprietà predefinita `myProperty` sulla classe `class1`.</span><span class="sxs-lookup"><span data-stu-id="7f90e-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="7f90e-126">Le istruzioni di assegnazione di tre valori memorizzati in `myProperty`e <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata legge i valori.</span><span class="sxs-lookup"><span data-stu-id="7f90e-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 <span data-ttu-id="7f90e-127">L'utilizzo più comune di una proprietà predefinita è la <xref:Microsoft.VisualBasic.Collection.Item%2A> proprietà in varie classi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="7f90e-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7f90e-128">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="7f90e-128">Robust Programming</span></span>  
 <span data-ttu-id="7f90e-129">Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma può rendere più difficile la lettura di codice.</span><span class="sxs-lookup"><span data-stu-id="7f90e-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="7f90e-130">Se il codice chiamante non ha familiarità con la classe o struttura, quando fa riferimento al nome di classe o struttura non può essere determinato se il riferimento accede la classe o struttura o una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="7f90e-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="7f90e-131">Questo può causare errori del compilatore o meno evidenti della logica di runtime.</span><span class="sxs-lookup"><span data-stu-id="7f90e-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="7f90e-132">Piuttosto, è possibile ridurre il rischio di errori di proprietà predefiniti utilizzando sempre la [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo di compilatore controllo `On`.</span><span class="sxs-lookup"><span data-stu-id="7f90e-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="7f90e-133">Se si intende utilizzare una struttura o classe predefiniti nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, il relativo nome novità.</span><span class="sxs-lookup"><span data-stu-id="7f90e-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="7f90e-134">A causa di questi svantaggi, è consigliabile non definire proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="7f90e-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="7f90e-135">Per la leggibilità del codice, è necessario anche valutare fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="7f90e-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f90e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f90e-136">See Also</span></span>  
 [<span data-ttu-id="7f90e-137">Routine Property</span><span class="sxs-lookup"><span data-stu-id="7f90e-137">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="7f90e-138">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="7f90e-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="7f90e-139">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="7f90e-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="7f90e-140">Default</span><span class="sxs-lookup"><span data-stu-id="7f90e-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)  
 [<span data-ttu-id="7f90e-141">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f90e-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="7f90e-142">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="7f90e-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="7f90e-143">Procedura: Dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="7f90e-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="7f90e-144">Procedura: Chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="7f90e-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="7f90e-145">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="7f90e-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="7f90e-146">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="7f90e-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
