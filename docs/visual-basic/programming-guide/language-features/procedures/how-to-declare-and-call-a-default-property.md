---
title: 'Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 7805ee4dcd4bad0d0624c97ccc25232e9bc31ba4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650995"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="d9387-102">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9387-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="d9387-103">Oggetto *proprietà predefinita* è una proprietà di classe o struttura che il codice può accedere senza specificarla.</span><span class="sxs-lookup"><span data-stu-id="d9387-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="d9387-104">Quando si chiama codice nomi una classe o struttura ma non una proprietà e il contesto consente l'accesso a una proprietà, Visual Basic viene risolto l'accesso a tale classe o una proprietà predefinita della struttura, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="d9387-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="d9387-105">Una classe o struttura può contenere al massimo una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9387-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="d9387-106">Tuttavia, è possibile eseguire l'overload di una proprietà predefinita e più di una versione di esso.</span><span class="sxs-lookup"><span data-stu-id="d9387-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="d9387-107">Per ulteriori informazioni, vedere [predefinito](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="d9387-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="d9387-108">Per dichiarare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="d9387-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="d9387-109">Dichiarare la proprietà in modo normale.</span><span class="sxs-lookup"><span data-stu-id="d9387-109">Declare the property in the normal way.</span></span> <span data-ttu-id="d9387-110">Non si specifica il `Shared` o `Private` (parola chiave).</span><span class="sxs-lookup"><span data-stu-id="d9387-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="d9387-111">Includere il `Default` parola chiave nella dichiarazione di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9387-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="d9387-112">Specificare almeno un parametro per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9387-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="d9387-113">È possibile definire una proprietà predefinita che non accetta almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="d9387-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="d9387-114">Per chiamare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="d9387-114">To call a default property</span></span>  
  
1.  <span data-ttu-id="d9387-115">Dichiarare una variabile del tipo di classe o struttura contenitore.</span><span class="sxs-lookup"><span data-stu-id="d9387-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  <span data-ttu-id="d9387-116">Utilizzare il nome della variabile da solo in un'espressione in cui è in genere necessario includere il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9387-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  <span data-ttu-id="d9387-117">Seguire il nome della variabile con un elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="d9387-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="d9387-118">Una proprietà predefinita deve accettare almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="d9387-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  <span data-ttu-id="d9387-119">Per recuperare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti, in un'espressione o in seguito uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d9387-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  <span data-ttu-id="d9387-120">Per impostare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d9387-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  <span data-ttu-id="d9387-121">È sempre possibile specificare il nome predefinito della proprietà con il nome della variabile, così come si farebbe per accedere a qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9387-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="d9387-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9387-122">Example</span></span>  
 <span data-ttu-id="d9387-123">Nell'esempio seguente dichiara una proprietà predefinita in una classe.</span><span class="sxs-lookup"><span data-stu-id="d9387-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a><span data-ttu-id="d9387-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9387-124">Example</span></span>  
 <span data-ttu-id="d9387-125">Nell'esempio seguente viene illustrato come chiamare la proprietà predefinita `myProperty` sulla classe `class1`.</span><span class="sxs-lookup"><span data-stu-id="d9387-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="d9387-126">Le istruzioni di assegnazione di tre valori memorizzati in `myProperty`e <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata legge i valori.</span><span class="sxs-lookup"><span data-stu-id="d9387-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 <span data-ttu-id="d9387-127">L'utilizzo più comune di una proprietà predefinita è la <xref:Microsoft.VisualBasic.Collection.Item%2A> proprietà in varie classi di raccolta.</span><span class="sxs-lookup"><span data-stu-id="d9387-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d9387-128">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="d9387-128">Robust Programming</span></span>  
 <span data-ttu-id="d9387-129">Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma può rendere più difficile la lettura di codice.</span><span class="sxs-lookup"><span data-stu-id="d9387-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="d9387-130">Se il codice chiamante non ha familiarità con la classe o struttura, quando fa riferimento al nome di classe o struttura non può essere determinato se il riferimento accede la classe o struttura o una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9387-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="d9387-131">Questo può causare errori del compilatore o meno evidenti della logica di runtime.</span><span class="sxs-lookup"><span data-stu-id="d9387-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="d9387-132">Piuttosto, è possibile ridurre il rischio di errori di proprietà predefiniti utilizzando sempre la [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo di compilatore controllo `On`.</span><span class="sxs-lookup"><span data-stu-id="d9387-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="d9387-133">Se si intende utilizzare una struttura o classe predefiniti nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, il relativo nome novità.</span><span class="sxs-lookup"><span data-stu-id="d9387-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="d9387-134">A causa di questi svantaggi, è consigliabile non definire proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="d9387-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="d9387-135">Per la leggibilità del codice, è necessario anche valutare fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="d9387-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9387-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9387-136">See Also</span></span>  
 [<span data-ttu-id="d9387-137">Routine Property</span><span class="sxs-lookup"><span data-stu-id="d9387-137">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="d9387-138">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="d9387-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d9387-139">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="d9387-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="d9387-140">Default</span><span class="sxs-lookup"><span data-stu-id="d9387-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)  
 [<span data-ttu-id="d9387-141">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d9387-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="d9387-142">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="d9387-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="d9387-143">Procedura: Dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="d9387-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="d9387-144">Procedura: Chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="d9387-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="d9387-145">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="d9387-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="d9387-146">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="d9387-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
