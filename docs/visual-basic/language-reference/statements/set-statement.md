---
title: Istruzione Set (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: c6bb924a3c41e1c586f66c9473a94d1971ee262f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973769"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="d9ad0-102">Istruzione Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9ad0-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="d9ad0-103">Dichiara un `Set` routine della proprietà utilizzata per assegnare un valore a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ad0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9ad0-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="d9ad0-105">Parti</span><span class="sxs-lookup"><span data-stu-id="d9ad0-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="d9ad0-106">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-106">Optional.</span></span> <span data-ttu-id="d9ad0-107">Visualizzare [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad0-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="d9ad0-108">Facoltativo in al massimo uno tra i `Get` e `Set` istruzioni in questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="d9ad0-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9ad0-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="d9ad0-110">Protected</span><span class="sxs-lookup"><span data-stu-id="d9ad0-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [<span data-ttu-id="d9ad0-111">Friend</span><span class="sxs-lookup"><span data-stu-id="d9ad0-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [<span data-ttu-id="d9ad0-112">Private</span><span class="sxs-lookup"><span data-stu-id="d9ad0-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 <span data-ttu-id="d9ad0-113">Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad0-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="d9ad0-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-114">Required.</span></span> <span data-ttu-id="d9ad0-115">Parametro che contiene il nuovo valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="d9ad0-116">Obbligatorio se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="d9ad0-117">Tipo di dati del `value` parametro.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="d9ad0-118">Tipo di dati specificato deve essere lo stesso come il tipo di dati della proprietà in cui questo `Set` istruzione viene dichiarata.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="d9ad0-119">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-119">Optional.</span></span> <span data-ttu-id="d9ad0-120">Una o più istruzioni che vengono eseguite quando il `Set` routine della proprietà viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="d9ad0-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-121">Required.</span></span> <span data-ttu-id="d9ad0-122">Termina la definizione del `Set` routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9ad0-123">Note</span><span class="sxs-lookup"><span data-stu-id="d9ad0-123">Remarks</span></span>  
 <span data-ttu-id="d9ad0-124">Ogni proprietà deve avere una `Set` routine della proprietà, a meno che la proprietà è contrassegnata `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="d9ad0-125">Il `Set` procedure viene utilizzata per impostare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="d9ad0-126">Visual Basic viene chiamata automaticamente una proprietà `Set` procedure quando un'istruzione di assegnazione fornisce un valore da archiviare nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="d9ad0-127">Visual Basic passa un parametro per il `Set` procedura durante le assegnazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="d9ad0-128">Se non si specifica un parametro per `Set`, l'ambiente di sviluppo integrato (IDE) usa un parametro implicito denominato `value`.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="d9ad0-129">Il parametro contiene il valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="d9ad0-130">In genere archivia questo valore in una variabile locale privata e restituirlo ogni volta che il `Get` routine viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="d9ad0-131">Il corpo della dichiarazione di proprietà può contenere solo della proprietà `Get` e `Set` procedure tra il [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) e il `End Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="d9ad0-132">Non può contenere qualsiasi elemento diverso da tali procedure.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="d9ad0-133">In particolare, è possibile archiviare il valore della proprietà corrente.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="d9ad0-134">È necessario archiviare questo valore di fuori della proprietà, poiché se si archivia, all'interno di una delle routine della proprietà, le altre routine di proprietà non è possibile accedervi.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="d9ad0-135">In genere questo consiste nell'archiviare il valore in una [privato](../../../visual-basic/language-reference/modifiers/private.md) variabile dichiarata allo stesso livello della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="d9ad0-136">È necessario definire un `Set` procedure all'interno della proprietà a cui viene applicata.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="d9ad0-137">Il `Set` predefinito usato dalla procedura a livello di accesso della proprietà che la contiene meno di utilizzare `accessmodifier` nel `Set` istruzione.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d9ad0-138">Regole</span><span class="sxs-lookup"><span data-stu-id="d9ad0-138">Rules</span></span>  
  
-   <span data-ttu-id="d9ad0-139">**Livelli di accesso misti.**</span><span class="sxs-lookup"><span data-stu-id="d9ad0-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="d9ad0-140">Se si sta definendo una proprietà di lettura / scrittura, è possibile specificare facoltativamente un livello di accesso diversi per il `Get` o il `Set` procedure, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="d9ad0-141">In questo caso, il livello di accesso di routine deve essere più restrittivo rispetto a livello di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="d9ad0-142">Ad esempio, se la proprietà è dichiarata `Friend`, è possibile dichiarare il `Set` routine `Private`, ma non `Public`.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="d9ad0-143">Se si sta definendo un `WriteOnly` proprietà, il `Set` procedure rappresenta l'intera proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="d9ad0-144">Non è possibile dichiarare un accesso diverso a livello di `Set`, poiché verrebbero specificati due livelli di accesso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d9ad0-145">Comportamento</span><span class="sxs-lookup"><span data-stu-id="d9ad0-145">Behavior</span></span>  
  
-   <span data-ttu-id="d9ad0-146">**Restituzione da una routine di proprietà.**</span><span class="sxs-lookup"><span data-stu-id="d9ad0-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="d9ad0-147">Quando il `Set` routine restituisce al codice chiamante, l'esecuzione continua subito dopo l'istruzione che ha fornito il valore da archiviare.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="d9ad0-148">`Set` le routine della proprietà possono restituire utilizzando il [istruzione Return](../../../visual-basic/language-reference/statements/return-statement.md) o il [Esci da istruzione](../../../visual-basic/language-reference/statements/exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d9ad0-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="d9ad0-149">Il `Exit Property` e `Return` istruzioni di uscire immediatamente da una routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="d9ad0-150">Un numero qualsiasi di `Exit Property` e `Return` istruzioni possono trovarsi in qualsiasi punto della procedura, ed è possibile combinare `Exit Property` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9ad0-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="d9ad0-151">Example</span></span>  
 <span data-ttu-id="d9ad0-152">L'esempio seguente usa il `Set` istruzione per impostare il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9ad0-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="d9ad0-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9ad0-153">See also</span></span>
- [<span data-ttu-id="d9ad0-154">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="d9ad0-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="d9ad0-155">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="d9ad0-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="d9ad0-156">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="d9ad0-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d9ad0-157">Routine Property</span><span class="sxs-lookup"><span data-stu-id="d9ad0-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
