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
ms.openlocfilehash: cb0dc76d110f3e6a3ea3e74cc0bfb5a669b35396
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583230"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="fa79f-102">Istruzione Set (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa79f-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="fa79f-103">Dichiara una routine della proprietà `Set` utilizzata per assegnare un valore a una proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa79f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa79f-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="fa79f-105">Parti</span><span class="sxs-lookup"><span data-stu-id="fa79f-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="fa79f-106">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fa79f-106">Optional.</span></span> <span data-ttu-id="fa79f-107">Vedere [elenco attributi](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="fa79f-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="fa79f-108">Facoltativo al massimo una delle istruzioni `Get` e `Set` in questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="fa79f-109">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="fa79f-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="fa79f-110">Protected</span><span class="sxs-lookup"><span data-stu-id="fa79f-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="fa79f-111">Friend</span><span class="sxs-lookup"><span data-stu-id="fa79f-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="fa79f-112">Private</span><span class="sxs-lookup"><span data-stu-id="fa79f-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="fa79f-113">Vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="fa79f-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="fa79f-114">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fa79f-114">Required.</span></span> <span data-ttu-id="fa79f-115">Parametro che contiene il nuovo valore per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="fa79f-116">Obbligatorio se `Option Strict` è `On`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="fa79f-117">Tipo di dati del parametro `value`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="fa79f-118">Il tipo di dati specificato deve corrispondere al tipo di dati della proprietà in cui è dichiarata questa istruzione `Set`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="fa79f-119">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fa79f-119">Optional.</span></span> <span data-ttu-id="fa79f-120">Una o più istruzioni eseguite quando viene chiamata la routine della proprietà `Set`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="fa79f-121">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="fa79f-121">Required.</span></span> <span data-ttu-id="fa79f-122">Termina la definizione della routine della proprietà `Set`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa79f-123">Note</span><span class="sxs-lookup"><span data-stu-id="fa79f-123">Remarks</span></span>  
 <span data-ttu-id="fa79f-124">Ogni proprietà deve disporre di una routine della proprietà `Set`, a meno che la proprietà non sia contrassegnata `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="fa79f-125">La procedura `Set` viene utilizzata per impostare il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="fa79f-126">Visual Basic chiama automaticamente una routine `Set` della proprietà quando un'istruzione di assegnazione fornisce un valore da archiviare nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="fa79f-127">Visual Basic passa un parametro alla routine `Set` durante le assegnazioni di proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="fa79f-128">Se non si specifica un parametro per `Set`, l'Integrated Development Environment (IDE) utilizza un parametro implicito denominato `value`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="fa79f-129">Il parametro include il valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="fa79f-130">Questo valore viene in genere archiviato in una variabile locale privata e restituito ogni volta che viene chiamata la procedura `Get`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="fa79f-131">Il corpo della dichiarazione di proprietà può contenere solo le `Get` della proprietà e `Set` le routine tra l' [istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md) e l'istruzione `End Property`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="fa79f-132">Non è possibile archiviare un valore diverso da tali procedure.</span><span class="sxs-lookup"><span data-stu-id="fa79f-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="fa79f-133">In particolare, non è possibile archiviare il valore corrente della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="fa79f-134">È necessario archiviare questo valore all'esterno della proprietà, perché se viene archiviato in una delle routine della proprietà, l'altra routine della proprietà non potrà accedervi.</span><span class="sxs-lookup"><span data-stu-id="fa79f-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="fa79f-135">L'approccio usuale consiste nell'archiviare il valore in una variabile [privata](../../../visual-basic/language-reference/modifiers/private.md) dichiarata allo stesso livello della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="fa79f-136">È necessario definire una procedura di `Set` all'interno della proprietà a cui si applica.</span><span class="sxs-lookup"><span data-stu-id="fa79f-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="fa79f-137">Per impostazione predefinita, la procedura `Set` il livello di accesso della proprietà che lo contiene, a meno che non si usi `accessmodifier` nell'istruzione `Set`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="fa79f-138">Regole</span><span class="sxs-lookup"><span data-stu-id="fa79f-138">Rules</span></span>  
  
- <span data-ttu-id="fa79f-139">**Livelli di accesso misti.**</span><span class="sxs-lookup"><span data-stu-id="fa79f-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="fa79f-140">Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la procedura `Get` o per la `Set`, ma non per entrambi.</span><span class="sxs-lookup"><span data-stu-id="fa79f-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="fa79f-141">In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="fa79f-142">Se, ad esempio, la proprietà viene dichiarata `Friend`, è possibile dichiarare la routine `Set` `Private`, ma non `Public`.</span><span class="sxs-lookup"><span data-stu-id="fa79f-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="fa79f-143">Se si definisce una proprietà `WriteOnly`, la routine `Set` rappresenta l'intera proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="fa79f-144">Non è possibile dichiarare un livello di accesso diverso per `Set`, perché in questo modo verrebbero impostati due livelli di accesso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="fa79f-145">Comportamento</span><span class="sxs-lookup"><span data-stu-id="fa79f-145">Behavior</span></span>  
  
- <span data-ttu-id="fa79f-146">**Restituzione da una routine di proprietà.**</span><span class="sxs-lookup"><span data-stu-id="fa79f-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="fa79f-147">Quando la `Set` procedura restituisce al codice chiamante, l'esecuzione continua seguendo l'istruzione che ha fornito il valore da archiviare.</span><span class="sxs-lookup"><span data-stu-id="fa79f-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="fa79f-148">`Set` le routine della proprietà possono restituire utilizzando l'istruzione [return](../../../visual-basic/language-reference/statements/return-statement.md) o l' [istruzione Exit](../../../visual-basic/language-reference/statements/exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fa79f-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="fa79f-149">Le istruzioni `Exit Property` e `Return` generano un'uscita immediata da una routine Property.</span><span class="sxs-lookup"><span data-stu-id="fa79f-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="fa79f-150">Un numero qualsiasi di istruzioni `Exit Property` e `Return` può essere visualizzato in qualsiasi punto della procedura ed è possibile combinare `Exit Property` e `Return` istruzioni.</span><span class="sxs-lookup"><span data-stu-id="fa79f-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa79f-151">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa79f-151">Example</span></span>  
 <span data-ttu-id="fa79f-152">Nell'esempio seguente viene utilizzata l'istruzione `Set` per impostare il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="fa79f-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="fa79f-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa79f-153">See also</span></span>

- [<span data-ttu-id="fa79f-154">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="fa79f-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="fa79f-155">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="fa79f-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="fa79f-156">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="fa79f-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="fa79f-157">Routine Property</span><span class="sxs-lookup"><span data-stu-id="fa79f-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
