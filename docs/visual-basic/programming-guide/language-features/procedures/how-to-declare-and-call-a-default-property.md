---
title: 'Procedura: Dichiarare e chiamare una proprietà predefinita'
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
ms.openlocfilehash: 4de5d94a94e764d1fc543ffae41b00a9bb729c94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388154"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="00b75-102">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00b75-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="00b75-103">Una *proprietà predefinita* è una proprietà di classe o struttura a cui il codice può accedere senza specificarlo.</span><span class="sxs-lookup"><span data-stu-id="00b75-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="00b75-104">Quando si chiama il codice denomina una classe o una struttura ma non una proprietà e il contesto consente l'accesso a una proprietà, Visual Basic risolve l'accesso alla proprietà predefinita della classe o della struttura se ne esiste una.</span><span class="sxs-lookup"><span data-stu-id="00b75-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="00b75-105">Una classe o una struttura può includere al massimo una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="00b75-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="00b75-106">Tuttavia, è possibile eseguire l'overload di una proprietà predefinita e avere più di una versione.</span><span class="sxs-lookup"><span data-stu-id="00b75-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="00b75-107">Per ulteriori informazioni, vedere [default](../../../language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="00b75-107">For more information, see [Default](../../../language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="00b75-108">Per dichiarare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="00b75-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="00b75-109">Dichiarare la proprietà in modo normale.</span><span class="sxs-lookup"><span data-stu-id="00b75-109">Declare the property in the normal way.</span></span> <span data-ttu-id="00b75-110">Non specificare la `Shared` `Private` parola chiave o.</span><span class="sxs-lookup"><span data-stu-id="00b75-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="00b75-111">Includere la `Default` parola chiave nella dichiarazione della proprietà.</span><span class="sxs-lookup"><span data-stu-id="00b75-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="00b75-112">Specificare almeno un parametro per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="00b75-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="00b75-113">Non è possibile definire una proprietà predefinita che non accetta almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="00b75-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="00b75-114">Per chiamare una proprietà predefinita</span><span class="sxs-lookup"><span data-stu-id="00b75-114">To call a default property</span></span>  
  
1. <span data-ttu-id="00b75-115">Dichiarare una variabile della classe o del tipo di struttura che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="00b75-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="00b75-116">Usare il nome della variabile da solo in un'espressione in cui in genere si include il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="00b75-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="00b75-117">Seguire il nome della variabile con un elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="00b75-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="00b75-118">Una proprietà predefinita deve assumere almeno un argomento.</span><span class="sxs-lookup"><span data-stu-id="00b75-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="00b75-119">Per recuperare il valore predefinito della proprietà, usare il nome della variabile, con un elenco di argomenti, in un'espressione o dopo il `=` segno di uguale () in un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="00b75-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="00b75-120">Per impostare il valore predefinito della proprietà, utilizzare il nome della variabile, con un elenco di argomenti, sul lato sinistro di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="00b75-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="00b75-121">È sempre possibile specificare il nome della proprietà predefinita insieme al nome della variabile, esattamente come si farebbe per accedere a qualsiasi altra proprietà.</span><span class="sxs-lookup"><span data-stu-id="00b75-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="00b75-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="00b75-122">Example</span></span>  
 <span data-ttu-id="00b75-123">Nell'esempio seguente viene dichiarata una proprietà predefinita per una classe.</span><span class="sxs-lookup"><span data-stu-id="00b75-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="00b75-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="00b75-124">Example</span></span>  
 <span data-ttu-id="00b75-125">Nell'esempio seguente viene illustrato come chiamare la proprietà predefinita `myProperty` sulla classe `class1` .</span><span class="sxs-lookup"><span data-stu-id="00b75-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="00b75-126">Le tre istruzioni di assegnazione archiviano i valori in `myProperty` e la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata legge i valori.</span><span class="sxs-lookup"><span data-stu-id="00b75-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="00b75-127">L'utilizzo più comune di una proprietà predefinita è la <xref:Microsoft.VisualBasic.Collection.Item%2A> Proprietà in varie classi di raccolte.</span><span class="sxs-lookup"><span data-stu-id="00b75-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="00b75-128">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="00b75-128">Robust Programming</span></span>  
 <span data-ttu-id="00b75-129">Le proprietà predefinite possono causare una riduzione ridotta dei caratteri di codice sorgente, ma possono rendere il codice più difficile da leggere.</span><span class="sxs-lookup"><span data-stu-id="00b75-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="00b75-130">Se il codice chiamante non ha familiarità con la classe o la struttura, quando fa riferimento al nome della classe o della struttura, non può essere certo se il riferimento accede alla classe o alla struttura o a una proprietà predefinita.</span><span class="sxs-lookup"><span data-stu-id="00b75-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="00b75-131">Questo può causare errori del compilatore o errori di logica di run-time sottili.</span><span class="sxs-lookup"><span data-stu-id="00b75-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="00b75-132">È possibile ridurre in qualche modo la probabilità di errori di proprietà predefiniti usando sempre l' [istruzione Option Strict](../../../language-reference/statements/option-strict-statement.md) per impostare il controllo dei tipi del compilatore su `On` .</span><span class="sxs-lookup"><span data-stu-id="00b75-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="00b75-133">Se si prevede di usare una classe o una struttura predefinita nel codice, è necessario determinare se dispone di una proprietà predefinita e, in caso affermativo, il nome.</span><span class="sxs-lookup"><span data-stu-id="00b75-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="00b75-134">A causa di questi svantaggi, è consigliabile non definire le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="00b75-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="00b75-135">Per la leggibilità del codice, è consigliabile considerare sempre il riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.</span><span class="sxs-lookup"><span data-stu-id="00b75-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b75-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00b75-136">See also</span></span>

- [<span data-ttu-id="00b75-137">Routine Property</span><span class="sxs-lookup"><span data-stu-id="00b75-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="00b75-138">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="00b75-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="00b75-139">Property Statement</span><span class="sxs-lookup"><span data-stu-id="00b75-139">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="00b75-140">Default</span><span class="sxs-lookup"><span data-stu-id="00b75-140">Default</span></span>](../../../language-reference/modifiers/default.md)
- [<span data-ttu-id="00b75-141">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00b75-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="00b75-142">Procedura: creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="00b75-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="00b75-143">Procedura: dichiarare una proprietà con livelli di accesso misti</span><span class="sxs-lookup"><span data-stu-id="00b75-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="00b75-144">Procedura: chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="00b75-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="00b75-145">Procedura: inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="00b75-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="00b75-146">Procedura: ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="00b75-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
