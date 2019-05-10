---
title: Routine Property (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: b637f6a5f3ef367dfe769c2878878eeb938e3c81
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638808"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="c517f-102">Routine Property (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c517f-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="c517f-103">Una routine di proprietà è una serie di istruzioni di Visual Basic che consentono di modificare una proprietà personalizzata in un modulo, classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="c517f-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="c517f-104">Le routine della proprietà sono dette anche *funzioni di accesso proprietà*.</span><span class="sxs-lookup"><span data-stu-id="c517f-104">Property procedures are also known as *property accessors*.</span></span>  
  
 <span data-ttu-id="c517f-105">Visual Basic fornisce le routine della proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="c517f-105">Visual Basic provides for the following property procedures:</span></span>  
  
- <span data-ttu-id="c517f-106">Oggetto `Get` procedure restituisce il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="c517f-107">Viene chiamato quando si accede alla proprietà in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="c517f-107">It is called when you access the property in an expression.</span></span>  
  
- <span data-ttu-id="c517f-108">Oggetto `Set` routine imposta una proprietà su un valore, incluso un riferimento all'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c517f-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="c517f-109">Viene chiamato quando si assegna un valore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="c517f-110">Le routine della proprietà in genere definite in coppie, mediante il `Get` e `Set` istruzioni, ma è possibile definire entrambe le procedure da solo se la proprietà è di sola lettura ([l'istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o in sola lettura ([impostata Istruzione](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="c517f-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="c517f-111">È possibile omettere il `Get` e `Set` procedura quando si usa una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c517f-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="c517f-112">Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c517f-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="c517f-113">È possibile definire le proprietà nelle classi, strutture e i moduli.</span><span class="sxs-lookup"><span data-stu-id="c517f-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="c517f-114">Le proprietà sono `Public` per impostazione predefinita, il che significa che è possibile chiamarle da qualsiasi posizione nell'applicazione che possa accedere al contenitore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="c517f-115">Per un confronto tra proprietà e variabili, vedere [differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="c517f-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="c517f-116">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="c517f-116">Declaration Syntax</span></span>  
 <span data-ttu-id="c517f-117">Una proprietà è definita da un blocco di codice incluso all'interno di [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) e il `End Property` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c517f-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="c517f-118">All'interno del blocco, ogni routine della proprietà viene visualizzata come un blocco interno racchiuso in un'istruzione di dichiarazione (`Get` oppure `Set`) e il corrispondente `End` dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c517f-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="c517f-119">La sintassi per dichiarare una proprietà e le relative procedure è come segue:</span><span class="sxs-lookup"><span data-stu-id="c517f-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
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
  
 <span data-ttu-id="c517f-120">Il `Modifiers` può specificare il livello di accesso e le informazioni riguardanti l'overload, si esegue l'override, la condivisione e shadowing, nonché se la proprietà è di sola lettura o in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c517f-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="c517f-121">Il `AccessLevel` nella `Get` o `Set` routine può essere di qualsiasi livello più restrittivo rispetto al livello di accesso specificato per la proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="c517f-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="c517f-122">Per altre informazioni, vedere [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c517f-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="c517f-123">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c517f-123">Data Type</span></span>  
 <span data-ttu-id="c517f-124">Tipo di dati della proprietà e il livello di accesso dell'entità sono definiti nel `Property` istruzione, non nella routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="c517f-125">Una proprietà può avere solo un tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="c517f-125">A property can have only one data type.</span></span> <span data-ttu-id="c517f-126">Ad esempio, è possibile definire una proprietà per archiviare una `Decimal` valore ma che recuperano un `Double` valore.</span><span class="sxs-lookup"><span data-stu-id="c517f-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="c517f-127">Livello di accesso</span><span class="sxs-lookup"><span data-stu-id="c517f-127">Access Level</span></span>  
 <span data-ttu-id="c517f-128">Tuttavia, è possibile definire un livello di accesso dell'entità per una proprietà e limitare ulteriormente il livello di accesso in una delle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="c517f-129">Ad esempio, è possibile definire un `Public` proprietà, quindi definire un `Private Set` procedure.</span><span class="sxs-lookup"><span data-stu-id="c517f-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="c517f-130">Il `Get` rimane impostato su procedure `Public`.</span><span class="sxs-lookup"><span data-stu-id="c517f-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="c517f-131">È possibile modificare il livello di accesso in solo una delle routine della proprietà e si può solo rendono più restrittivo del livello di accesso dell'entità.</span><span class="sxs-lookup"><span data-stu-id="c517f-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="c517f-132">Per altre informazioni, vedere [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="c517f-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="c517f-133">Dichiarazione di parametro</span><span class="sxs-lookup"><span data-stu-id="c517f-133">Parameter Declaration</span></span>  
 <span data-ttu-id="c517f-134">Ogni parametro è dichiarare la stessa procedura valida per [routine Sub](./sub-procedures.md), ad eccezione del fatto che il meccanismo di passaggio deve essere `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="c517f-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="c517f-135">La sintassi per ogni parametro nell'elenco dei parametri è come segue:</span><span class="sxs-lookup"><span data-stu-id="c517f-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="c517f-136">Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="c517f-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="c517f-137">La sintassi per specificare un valore predefinito è come segue:</span><span class="sxs-lookup"><span data-stu-id="c517f-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="c517f-138">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="c517f-138">Property Value</span></span>  
 <span data-ttu-id="c517f-139">In un `Get` procedure, il valore restituito viene fornita all'espressione chiamante come valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="c517f-140">In un `Set` routine, il nuovo valore della proprietà viene passato al parametro il `Set` istruzione.</span><span class="sxs-lookup"><span data-stu-id="c517f-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="c517f-141">Se si dichiara in modo esplicito un parametro, è necessario dichiararla con lo stesso tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="c517f-142">Se non si dichiara un parametro, il compilatore Usa il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="c517f-143">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="c517f-143">Calling Syntax</span></span>  
 <span data-ttu-id="c517f-144">Una routine di proprietà è richiamare in modo implicito facendo riferimento alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="c517f-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="c517f-145">Si utilizza il nome della proprietà simile a quello è necessario usare il nome di una variabile, ad eccezione del fatto che è necessario fornire valori per tutti gli argomenti che non sono facoltativi ed è necessario racchiudere l'elenco di argomenti racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="c517f-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="c517f-146">Se viene fornito alcun argomento, è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="c517f-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="c517f-147">La sintassi per una chiamata implicita a un `Set` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="c517f-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="c517f-148">La sintassi per una chiamata implicita a un `Get` procedura è la seguente:</span><span class="sxs-lookup"><span data-stu-id="c517f-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="c517f-149">Illustrazione di dichiarazione e di chiamata</span><span class="sxs-lookup"><span data-stu-id="c517f-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="c517f-150">La proprietà seguente archivia un nome completo come due parti costitutive, il nome e cognome.</span><span class="sxs-lookup"><span data-stu-id="c517f-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="c517f-151">Quando legge il codice chiamante `fullName`, il `Get` procedure combina le due parti costitutive e restituisce il nome completo.</span><span class="sxs-lookup"><span data-stu-id="c517f-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="c517f-152">Quando il codice chiamante assegna un nuovo nome completo, il `Set` routine tenta di suddividere l'operazione in due parti costitutive.</span><span class="sxs-lookup"><span data-stu-id="c517f-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="c517f-153">Se non viene trovato uno spazio, li archivia tutti come il nome.</span><span class="sxs-lookup"><span data-stu-id="c517f-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="c517f-154">L'esempio seguente illustra tipici chiamate alle routine della proprietà di `fullName`.</span><span class="sxs-lookup"><span data-stu-id="c517f-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c517f-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c517f-155">See also</span></span>

- [<span data-ttu-id="c517f-156">Routine</span><span class="sxs-lookup"><span data-stu-id="c517f-156">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c517f-157">Routine Function</span><span class="sxs-lookup"><span data-stu-id="c517f-157">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="c517f-158">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="c517f-158">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="c517f-159">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="c517f-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c517f-160">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c517f-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="c517f-161">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="c517f-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="c517f-162">Procedura: Chiamare una routine Property</span><span class="sxs-lookup"><span data-stu-id="c517f-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="c517f-163">Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c517f-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="c517f-164">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="c517f-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="c517f-165">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="c517f-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
