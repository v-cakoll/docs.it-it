---
title: Routine Property (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9df6f381c89263aa16315fb06a2b3b0d645bbf
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="65fd3-102">Routine Property (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65fd3-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="65fd3-103">Una routine di proprietà è una serie di istruzioni di Visual Basic che consentono di modificare una proprietà personalizzata in un modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="65fd3-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="65fd3-104">Le routine della proprietà sono anche noti come *accesso della proprietà*.</span><span class="sxs-lookup"><span data-stu-id="65fd3-104">Property procedures are also known as *property accessors*.</span></span>  
  
 <span data-ttu-id="65fd3-105">Visual Basic fornisce le routine della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="65fd3-105">Visual Basic provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="65fd3-106">Oggetto `Get` procedura restituisce il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="65fd3-107">Viene chiamato quando si accede alla proprietà in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="65fd3-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="65fd3-108">Oggetto `Set` routine imposta una proprietà su un valore, incluso un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="65fd3-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="65fd3-109">Viene chiamato quando si assegna un valore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="65fd3-110">È in genere definire le routine di proprietà in coppie, mediante il `Get` e `Set` istruzione, ma è possibile definire una routine singolarmente se la proprietà è di sola lettura ([l'istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o di sola scrittura ([impostato Istruzione](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="65fd3-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="65fd3-111">È possibile omettere il `Get` e `Set` procedura quando si usa una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="65fd3-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="65fd3-112">Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="65fd3-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="65fd3-113">È possibile definire le proprietà nelle classi, strutture e i moduli.</span><span class="sxs-lookup"><span data-stu-id="65fd3-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="65fd3-114">Le proprietà sono `Public` per impostazione predefinita, il che significa che è possibile chiamarle da qualsiasi punto dell'applicazione che è possibile accedere al contenitore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="65fd3-115">Per un confronto tra proprietà e variabili, vedere [le differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="65fd3-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="65fd3-116">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="65fd3-116">Declaration Syntax</span></span>  
 <span data-ttu-id="65fd3-117">Una proprietà è definita da un blocco di codice incluso all'interno di [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md) e `End Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="65fd3-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="65fd3-118">All'interno del blocco, ogni routine della proprietà viene visualizzato come un blocco interno racchiuso tra un'istruzione di dichiarazione (`Get` o `Set`) e il corrispondente `End` dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="65fd3-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="65fd3-119">La sintassi per dichiarare una proprietà e le relative procedure è come segue:</span><span class="sxs-lookup"><span data-stu-id="65fd3-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 <span data-ttu-id="65fd3-120">Il `Modifiers` può specificare il livello di accesso e le informazioni su overload, override, condivisione e shadowing, nonché se la proprietà è di sola lettura o in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="65fd3-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="65fd3-121">Il `AccessLevel` sul `Get` o `Set` procedura può essere qualsiasi livello più restrittivo rispetto al livello di accesso specificato per la proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="65fd3-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="65fd3-122">Per ulteriori informazioni, vedere [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="65fd3-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="65fd3-123">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="65fd3-123">Data Type</span></span>  
 <span data-ttu-id="65fd3-124">Tipo di dati di una proprietà e il livello di accesso dell'entità sono definiti nel `Property` istruzione, non nelle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="65fd3-125">Una proprietà può avere solo un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="65fd3-125">A property can have only one data type.</span></span> <span data-ttu-id="65fd3-126">Ad esempio, è possibile definire una proprietà per archiviare un `Decimal` valore ma che recuperano un `Double` valore.</span><span class="sxs-lookup"><span data-stu-id="65fd3-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="65fd3-127">Livello di accesso</span><span class="sxs-lookup"><span data-stu-id="65fd3-127">Access Level</span></span>  
 <span data-ttu-id="65fd3-128">Tuttavia, è possibile definire un livello di accesso dell'entità per una proprietà e limitare ulteriormente il livello di accesso in una delle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="65fd3-129">Ad esempio, è possibile definire un `Public` proprietà e quindi definire un `Private Set` stored procedure.</span><span class="sxs-lookup"><span data-stu-id="65fd3-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="65fd3-130">Il `Get` procedura rimane `Public`.</span><span class="sxs-lookup"><span data-stu-id="65fd3-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="65fd3-131">È possibile modificare il livello di accesso in sola delle routine della proprietà e, è possibile solo apportare più restrittivo rispetto al livello di accesso dell'entità.</span><span class="sxs-lookup"><span data-stu-id="65fd3-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="65fd3-132">Per ulteriori informazioni, vedere [procedura: dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="65fd3-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="65fd3-133">Dichiarazione di parametro</span><span class="sxs-lookup"><span data-stu-id="65fd3-133">Parameter Declaration</span></span>  
 <span data-ttu-id="65fd3-134">Ciascun parametro viene dichiarato esattamente come avviene per [Sub (routine)](./sub-procedures.md), ad eccezione del fatto che il meccanismo di passaggio deve essere `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="65fd3-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="65fd3-135">La sintassi per ogni parametro nell'elenco di parametri è come segue:</span><span class="sxs-lookup"><span data-stu-id="65fd3-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="65fd3-136">Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="65fd3-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="65fd3-137">La sintassi per specificare un valore predefinito è come segue:</span><span class="sxs-lookup"><span data-stu-id="65fd3-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="65fd3-138">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="65fd3-138">Property Value</span></span>  
 <span data-ttu-id="65fd3-139">In un `Get` procedure, il valore restituito viene fornita all'espressione chiamante come valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="65fd3-140">In un `Set` procedure, il nuovo valore della proprietà viene passato al parametro del `Set` istruzione.</span><span class="sxs-lookup"><span data-stu-id="65fd3-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="65fd3-141">Se si dichiara in modo esplicito un parametro, è necessario dichiararla con lo stesso tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="65fd3-142">Se non si dichiara un parametro, il compilatore utilizza il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="65fd3-143">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="65fd3-143">Calling Syntax</span></span>  
 <span data-ttu-id="65fd3-144">Richiamare una routine di proprietà in modo implicito facendo riferimento alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="65fd3-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="65fd3-145">Utilizzare il nome della proprietà esattamente come si utilizzerebbe il nome di una variabile, ad eccezione del fatto che è necessario fornire valori per tutti gli argomenti non facoltativi e, è necessario racchiudere l'elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="65fd3-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="65fd3-146">Se non vengono forniti argomenti, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="65fd3-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="65fd3-147">La sintassi per una chiamata implicita a un `Set` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="65fd3-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="65fd3-148">La sintassi per una chiamata implicita a un `Get` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="65fd3-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="65fd3-149">Illustrazione di dichiarazione e chiamata</span><span class="sxs-lookup"><span data-stu-id="65fd3-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="65fd3-150">La seguente proprietà archiviato un nome completo come due parti costitutive, il nome e il cognome.</span><span class="sxs-lookup"><span data-stu-id="65fd3-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="65fd3-151">Quando viene letto il codice chiamante `fullName`, `Get` procedure combina le due parti costitutive e restituisce il nome completo.</span><span class="sxs-lookup"><span data-stu-id="65fd3-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="65fd3-152">Quando il codice chiamante viene assegnato un nuovo nome completo, il `Set` routine tenta di suddividerla in due parti costitutive.</span><span class="sxs-lookup"><span data-stu-id="65fd3-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="65fd3-153">Se non viene trovato uno spazio, memorizzato tutto come il nome.</span><span class="sxs-lookup"><span data-stu-id="65fd3-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 <span data-ttu-id="65fd3-154">L'esempio seguente mostra le chiamate alle routine della proprietà di tipiche `fullName`.</span><span class="sxs-lookup"><span data-stu-id="65fd3-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="65fd3-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65fd3-155">See Also</span></span>  
 [<span data-ttu-id="65fd3-156">Routine</span><span class="sxs-lookup"><span data-stu-id="65fd3-156">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="65fd3-157">Routine Function</span><span class="sxs-lookup"><span data-stu-id="65fd3-157">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="65fd3-158">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="65fd3-158">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="65fd3-159">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="65fd3-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="65fd3-160">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65fd3-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="65fd3-161">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="65fd3-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="65fd3-162">Procedura: Chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="65fd3-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="65fd3-163">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="65fd3-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="65fd3-164">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="65fd3-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="65fd3-165">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="65fd3-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
