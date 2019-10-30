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
ms.openlocfilehash: 118c9e776813f303ed921946f4cf6f1236ac02e3
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040967"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="f32d4-102">Routine Property (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f32d4-102">Property Procedures (Visual Basic)</span></span>

<span data-ttu-id="f32d4-103">Una routine di proprietà è una serie di istruzioni Visual Basic che consentono di modificare una proprietà personalizzata in un modulo, una classe o una struttura.</span><span class="sxs-lookup"><span data-stu-id="f32d4-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="f32d4-104">Le routine di proprietà sono note anche come *funzioni di accesso alle proprietà*.</span><span class="sxs-lookup"><span data-stu-id="f32d4-104">Property procedures are also known as *property accessors*.</span></span>

<span data-ttu-id="f32d4-105">Visual Basic fornisce le routine di proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="f32d4-105">Visual Basic provides for the following property procedures:</span></span>

- <span data-ttu-id="f32d4-106">Una routine `Get` restituisce il valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="f32d4-107">Viene chiamato quando si accede alla proprietà in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="f32d4-107">It is called when you access the property in an expression.</span></span>
- <span data-ttu-id="f32d4-108">Una routine `Set` imposta una proprietà su un valore, incluso un riferimento a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f32d4-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="f32d4-109">Viene chiamato quando si assegna un valore alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-109">It is called when you assign a value to the property.</span></span>

<span data-ttu-id="f32d4-110">In genere, le routine di proprietà vengono definite in coppie, usando le istruzioni `Get` e `Set`, ma è possibile definire una sola procedura solo se la proprietà è di sola lettura ([istruzione Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o di sola scrittura ([istruzione set](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="f32d4-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>

<span data-ttu-id="f32d4-111">Quando si usa una proprietà implementata automaticamente, è possibile omettere il `Get` e `Set` procedura.</span><span class="sxs-lookup"><span data-stu-id="f32d4-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="f32d4-112">Per altre informazioni, vedere [Proprietà implementate automaticamente](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f32d4-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>

<span data-ttu-id="f32d4-113">È possibile definire le proprietà in classi, strutture e moduli.</span><span class="sxs-lookup"><span data-stu-id="f32d4-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="f32d4-114">Per impostazione predefinita, le proprietà sono `Public`, quindi è possibile chiamarle da qualsiasi punto dell'applicazione in grado di accedere al contenitore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>

<span data-ttu-id="f32d4-115">Per un confronto tra proprietà e variabili, vedere [differenze tra proprietà e variabili in Visual Basic](differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="f32d4-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](differences-between-properties-and-variables.md).</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="f32d4-116">Sintassi di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="f32d4-116">Declaration syntax</span></span>

<span data-ttu-id="f32d4-117">Una proprietà viene definita da un blocco di codice racchiuso tra l' [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md) e l'istruzione `End Property`.</span><span class="sxs-lookup"><span data-stu-id="f32d4-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="f32d4-118">All'interno di questo blocco ogni routine di proprietà viene visualizzata come un blocco interno racchiuso tra un'istruzione di dichiarazione (`Get` o `Set`) e la dichiarazione `End` corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f32d4-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>

<span data-ttu-id="f32d4-119">La sintassi per la dichiarazione di una proprietà e delle relative procedure è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f32d4-119">The syntax for declaring a property and its procedures is as follows:</span></span>

```vb
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
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

<span data-ttu-id="f32d4-120">Il `Modifiers` può specificare il livello di accesso e le informazioni relative all'overload, all'override, alla condivisione e allo shadowing, nonché se la proprietà è di sola lettura o di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="f32d4-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="f32d4-121">Il `AccessLevel` della procedura `Get` o `Set` può essere qualsiasi livello più restrittivo del livello di accesso specificato per la proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="f32d4-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="f32d4-122">Per ulteriori informazioni, vedere [istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f32d4-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="f32d4-123">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="f32d4-123">Data Type</span></span>

<span data-ttu-id="f32d4-124">Il tipo di dati e il livello di accesso dell'entità di una proprietà sono definiti nell'istruzione `Property`, non nelle routine della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="f32d4-125">Una proprietà può avere un solo tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="f32d4-125">A property can have only one data type.</span></span> <span data-ttu-id="f32d4-126">Non è ad esempio possibile definire una proprietà per archiviare un valore di `Decimal` ma recuperare un valore `Double`.</span><span class="sxs-lookup"><span data-stu-id="f32d4-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>

### <a name="access-level"></a><span data-ttu-id="f32d4-127">Livello di accesso</span><span class="sxs-lookup"><span data-stu-id="f32d4-127">Access Level</span></span>

<span data-ttu-id="f32d4-128">Tuttavia, è possibile definire un livello di accesso principale per una proprietà e limitare ulteriormente il livello di accesso in una delle relative routine di proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="f32d4-129">Ad esempio, è possibile definire una proprietà `Public` e quindi definire una `Private Set` routine.</span><span class="sxs-lookup"><span data-stu-id="f32d4-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="f32d4-130">La `Get` routine rimane `Public`.</span><span class="sxs-lookup"><span data-stu-id="f32d4-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="f32d4-131">È possibile modificare il livello di accesso solo in una delle routine di una proprietà ed è possibile renderlo solo più restrittivo del livello di accesso principale.</span><span class="sxs-lookup"><span data-stu-id="f32d4-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="f32d4-132">Per altre informazioni, vedere [procedura: dichiarare una proprietà con livelli di accesso misti](how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="f32d4-132">For more information, see [How to: Declare a Property with Mixed Access Levels](how-to-declare-a-property-with-mixed-access-levels.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="f32d4-133">Dichiarazione di parametro</span><span class="sxs-lookup"><span data-stu-id="f32d4-133">Parameter declaration</span></span>

<span data-ttu-id="f32d4-134">Ogni parametro viene dichiarato in modo analogo alle [procedure secondarie](sub-procedures.md), con la differenza che il meccanismo di passaggio deve essere `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="f32d4-134">You declare each parameter the same way you do for [Sub Procedures](sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>

<span data-ttu-id="f32d4-135">La sintassi per ogni parametro nell'elenco di parametri è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f32d4-135">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

<span data-ttu-id="f32d4-136">Se il parametro è facoltativo, è necessario specificare anche un valore predefinito come parte della relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f32d4-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="f32d4-137">La sintassi per specificare un valore predefinito è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f32d4-137">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a><span data-ttu-id="f32d4-138">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="f32d4-138">Property value</span></span>

<span data-ttu-id="f32d4-139">In una `Get` routine, il valore restituito viene fornito all'espressione chiamante come valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>

<span data-ttu-id="f32d4-140">In una procedura `Set` il nuovo valore della proprietà viene passato al parametro dell'istruzione `Set`.</span><span class="sxs-lookup"><span data-stu-id="f32d4-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="f32d4-141">Se si dichiara in modo esplicito un parametro, è necessario dichiararlo con lo stesso tipo di dati della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="f32d4-142">Se non si dichiara un parametro, il compilatore usa il parametro implicito `Value` per rappresentare il nuovo valore da assegnare alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="f32d4-143">Sintassi di chiamata</span><span class="sxs-lookup"><span data-stu-id="f32d4-143">Calling syntax</span></span>

<span data-ttu-id="f32d4-144">Per richiamare una routine di proprietà in modo implicito, è necessario fare riferimento alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="f32d4-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="f32d4-145">Usare il nome della proprietà nello stesso modo in cui si usa il nome di una variabile, ad eccezione del fatto che è necessario fornire i valori per tutti gli argomenti non facoltativi ed è necessario racchiudere l'elenco di argomenti tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="f32d4-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="f32d4-146">Se non viene fornito alcun argomento, facoltativamente è possibile omettere le parentesi.</span><span class="sxs-lookup"><span data-stu-id="f32d4-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="f32d4-147">La sintassi per una chiamata implicita a una procedura `Set` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f32d4-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>

```vb
propertyname[(argumentlist)] = expression
```

<span data-ttu-id="f32d4-148">La sintassi per una chiamata implicita a una procedura `Get` è la seguente:</span><span class="sxs-lookup"><span data-stu-id="f32d4-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="f32d4-149">Illustrazione della dichiarazione e della chiamata</span><span class="sxs-lookup"><span data-stu-id="f32d4-149">Illustration of declaration and call</span></span>

<span data-ttu-id="f32d4-150">Nella proprietà seguente viene archiviato un nome completo come due nomi costitutivi, il primo nome e il cognome.</span><span class="sxs-lookup"><span data-stu-id="f32d4-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="f32d4-151">Quando il codice chiamante legge `fullName`, la procedura `Get` combina i due nomi costitutivi e restituisce il nome completo.</span><span class="sxs-lookup"><span data-stu-id="f32d4-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="f32d4-152">Quando il codice chiamante assegna un nuovo nome completo, la `Set` routine tenta di suddividerla in due nomi costitutivi.</span><span class="sxs-lookup"><span data-stu-id="f32d4-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="f32d4-153">Se non trova uno spazio, lo archivia come nome.</span><span class="sxs-lookup"><span data-stu-id="f32d4-153">If it does not find a space, it stores it all as the first name.</span></span>

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

<span data-ttu-id="f32d4-154">Nell'esempio seguente vengono illustrate le chiamate tipiche alle routine di proprietà di `fullName`:</span><span class="sxs-lookup"><span data-stu-id="f32d4-154">The following example shows typical calls to the property procedures of `fullName`:</span></span>

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a><span data-ttu-id="f32d4-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f32d4-155">See also</span></span>

- [<span data-ttu-id="f32d4-156">Routine</span><span class="sxs-lookup"><span data-stu-id="f32d4-156">Procedures</span></span>](index.md)
- [<span data-ttu-id="f32d4-157">Routine Function</span><span class="sxs-lookup"><span data-stu-id="f32d4-157">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="f32d4-158">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="f32d4-158">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="f32d4-159">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="f32d4-159">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="f32d4-160">Differenze tra proprietà e variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f32d4-160">Differences Between Properties and Variables in Visual Basic</span></span>](differences-between-properties-and-variables.md)
- [<span data-ttu-id="f32d4-161">Procedura: Creare una proprietà</span><span class="sxs-lookup"><span data-stu-id="f32d4-161">How to: Create a Property</span></span>](how-to-create-a-property.md)
- [<span data-ttu-id="f32d4-162">Procedura: Chiamare una routine di proprietà</span><span class="sxs-lookup"><span data-stu-id="f32d4-162">How to: Call a Property Procedure</span></span>](how-to-call-a-property-procedure.md)
- [<span data-ttu-id="f32d4-163">Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f32d4-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="f32d4-164">Procedura: Inserire un valore in una proprietà</span><span class="sxs-lookup"><span data-stu-id="f32d4-164">How to: Put a Value in a Property</span></span>](how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="f32d4-165">Procedura: Ottenere un valore da una proprietà</span><span class="sxs-lookup"><span data-stu-id="f32d4-165">How to: Get a Value from a Property</span></span>](how-to-get-a-value-from-a-property.md)
