---
title: Istruzione Get
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 31936fb2c8f658203a43702a2b5fa4ee2481beb5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404602"
---
# <a name="get-statement"></a><span data-ttu-id="e6a6a-102">Istruzione Get</span><span class="sxs-lookup"><span data-stu-id="e6a6a-102">Get Statement</span></span>
<span data-ttu-id="e6a6a-103">Dichiara una `Get` routine di proprietà utilizzata per recuperare il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6a6a-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="e6a6a-105">Parti</span><span class="sxs-lookup"><span data-stu-id="e6a6a-105">Parts</span></span>  
  
|<span data-ttu-id="e6a6a-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e6a6a-106">Term</span></span>|<span data-ttu-id="e6a6a-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e6a6a-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="e6a6a-108">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-108">Optional.</span></span> <span data-ttu-id="e6a6a-109">Vedere [elenco attributi](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="e6a6a-109">See [Attribute List](attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="e6a6a-110">Facoltativo al massimo una delle `Get` `Set` istruzioni e in questa proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="e6a6a-111">Può essere uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6a6a-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="e6a6a-112">-   [Protetto](../modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="e6a6a-112">-   [Protected](../modifiers/protected.md)</span></span><br /><span data-ttu-id="e6a6a-113">-   [Amico](../modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="e6a6a-113">-   [Friend](../modifiers/friend.md)</span></span><br /><span data-ttu-id="e6a6a-114">-   [Privata](../modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="e6a6a-114">-   [Private](../modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="e6a6a-115">Vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e6a6a-115">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="e6a6a-116">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-116">Optional.</span></span> <span data-ttu-id="e6a6a-117">Una o più istruzioni che vengono eseguite quando `Get` viene chiamata la routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="e6a6a-118">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-118">Required.</span></span> <span data-ttu-id="e6a6a-119">Termina la definizione della routine della `Get` Proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6a6a-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="e6a6a-120">Remarks</span></span>  
 <span data-ttu-id="e6a6a-121">Ogni proprietà deve disporre di una `Get` routine Property, a meno che la proprietà non sia contrassegnata come `WriteOnly` .</span><span class="sxs-lookup"><span data-stu-id="e6a6a-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="e6a6a-122">La `Get` stored procedure viene utilizzata per restituire il valore corrente della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="e6a6a-123">Visual Basic chiama automaticamente la routine di una proprietà `Get` quando un'espressione richiede il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="e6a6a-124">Il corpo della dichiarazione di proprietà può contenere solo le `Get` routine e della proprietà `Set` tra l' [istruzione Property](property-statement.md) e l' `End Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="e6a6a-125">Non è possibile archiviare un valore diverso da tali procedure.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="e6a6a-126">In particolare, non è possibile archiviare il valore corrente della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="e6a6a-127">È necessario archiviare questo valore all'esterno della proprietà, perché se viene archiviato in una delle routine della proprietà, l'altra routine della proprietà non potrà accedervi.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="e6a6a-128">L'approccio usuale consiste nell'archiviare il valore in una variabile [privata](../modifiers/private.md) dichiarata allo stesso livello della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-128">The usual approach is to store the value in a [Private](../modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="e6a6a-129">È necessario definire una `Get` routine all'interno della proprietà a cui si applica.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="e6a6a-130">`Get`Per impostazione predefinita, la procedura viene impostata sul livello di accesso della proprietà che lo contiene, a meno che non si utilizzi `accessmodifier` nell' `Get` istruzione.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e6a6a-131">Regole</span><span class="sxs-lookup"><span data-stu-id="e6a6a-131">Rules</span></span>  
  
- <span data-ttu-id="e6a6a-132">**Livelli di accesso misti.**</span><span class="sxs-lookup"><span data-stu-id="e6a6a-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="e6a6a-133">Se si definisce una proprietà di lettura/scrittura, è possibile specificare facoltativamente un livello di accesso diverso per la `Get` routine o `Set` , ma non per entrambi.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="e6a6a-134">In tal caso, il livello di accesso della routine deve essere più restrittivo del livello di accesso della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="e6a6a-135">Se, ad esempio, la proprietà è dichiarata `Friend` , è possibile dichiarare la `Get` routine `Private` , ma non `Public` .</span><span class="sxs-lookup"><span data-stu-id="e6a6a-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="e6a6a-136">Se si definisce una `ReadOnly` proprietà, la `Get` routine rappresenta l'intera proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="e6a6a-137">Non è possibile dichiarare un livello di accesso diverso per `Get` , perché in questo caso verrebbero impostati due livelli di accesso per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
- <span data-ttu-id="e6a6a-138">**Tipo restituito.**</span><span class="sxs-lookup"><span data-stu-id="e6a6a-138">**Return Type.**</span></span> <span data-ttu-id="e6a6a-139">L' [istruzione Property](property-statement.md) può dichiarare il tipo di dati del valore restituito.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-139">The [Property Statement](property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="e6a6a-140">La `Get` stored procedure restituisce automaticamente il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="e6a6a-141">È possibile specificare qualsiasi tipo di dati o il nome di un'enumerazione, una struttura, una classe o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="e6a6a-142">Se l' `Property` istruzione non specifica `returntype` , la procedura restituisce `Object` .</span><span class="sxs-lookup"><span data-stu-id="e6a6a-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e6a6a-143">Comportamento</span><span class="sxs-lookup"><span data-stu-id="e6a6a-143">Behavior</span></span>  
  
- <span data-ttu-id="e6a6a-144">**Restituzione da una routine.**</span><span class="sxs-lookup"><span data-stu-id="e6a6a-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="e6a6a-145">Quando la `Get` procedura viene restituita al codice chiamante, l'esecuzione continua all'interno dell'istruzione che ha richiesto il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="e6a6a-146">`Get`le routine Property possono restituire un valore utilizzando l' [istruzione return](return-statement.md) o assegnando il valore restituito al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-146">`Get` property procedures can return a value using either the [Return Statement](return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="e6a6a-147">Per ulteriori informazioni, vedere "valore restituito" nell' [istruzione Function](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e6a6a-147">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="e6a6a-148">Le `Exit Property` `Return` istruzioni e generano un'uscita immediata da una routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="e6a6a-149">Qualsiasi numero di `Exit Property` `Return` istruzioni e può comparire in qualsiasi punto della procedura ed è possibile combinare le `Exit Property` `Return` istruzioni e.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
- <span data-ttu-id="e6a6a-150">**Valore restituito.**</span><span class="sxs-lookup"><span data-stu-id="e6a6a-150">**Return Value.**</span></span> <span data-ttu-id="e6a6a-151">Per restituire un valore da una `Get` routine, è possibile assegnare il valore al nome della proprietà o includerlo in un' [istruzione Return](return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e6a6a-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](return-statement.md).</span></span> <span data-ttu-id="e6a6a-152">L' `Return` istruzione assegna simultaneamente il `Get` valore restituito della routine e chiude la procedura.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="e6a6a-153">Se si utilizza `Exit Property` senza assegnare un valore al nome della proprietà, la `Get` stored procedure restituisce il valore predefinito per il tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="e6a6a-154">Per ulteriori informazioni, vedere "valore restituito" nell' [istruzione Function](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e6a6a-154">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="e6a6a-155">Nell'esempio seguente vengono illustrati due modi in cui la proprietà `quoteForTheDay` di sola lettura può restituire il valore contenuto nella variabile privata `quoteValue` .</span><span class="sxs-lookup"><span data-stu-id="e6a6a-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="e6a6a-156">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6a6a-156">Example</span></span>  
 <span data-ttu-id="e6a6a-157">Nell'esempio seguente viene utilizzata l' `Get` istruzione per restituire il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="e6a6a-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a6a-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6a6a-158">See also</span></span>

- [<span data-ttu-id="e6a6a-159">Istruzione set</span><span class="sxs-lookup"><span data-stu-id="e6a6a-159">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="e6a6a-160">Property Statement</span><span class="sxs-lookup"><span data-stu-id="e6a6a-160">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="e6a6a-161">Istruzione Exit</span><span class="sxs-lookup"><span data-stu-id="e6a6a-161">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="e6a6a-162">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="e6a6a-162">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="e6a6a-163">Procedura dettagliata: definizione delle classi</span><span class="sxs-lookup"><span data-stu-id="e6a6a-163">Walkthrough: Defining Classes</span></span>](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
