---
title: Conversioni implicite ed esplicite
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: b7215933cec89b7023f08e8996a283b39b3a3c83
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346363"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="6e2aa-102">Conversioni implicite ed esplicite (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e2aa-102">Implicit and Explicit Conversions (Visual Basic)</span></span>

<span data-ttu-id="6e2aa-103">Una *conversione implicita* non richiede alcuna sintassi speciale nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="6e2aa-104">Nell'esempio seguente Visual Basic converte in modo implicito il valore di `k` in un valore a virgola mobile a precisione singola prima di assegnarlo a `q`.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

<span data-ttu-id="6e2aa-105">Una *conversione esplicita* usa una parola chiave di conversione del tipo.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="6e2aa-106">Visual Basic fornisce diverse parole chiave, che assegnano un'espressione tra parentesi al tipo di dati desiderato.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="6e2aa-107">Queste parole chiave agiscono come funzioni, ma il compilatore genera il codice inline, quindi l'esecuzione è leggermente più veloce rispetto a una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>

<span data-ttu-id="6e2aa-108">Nell'estensione seguente dell'esempio precedente, la parola chiave `CInt` converte il valore di `q` di nuovo in un valore integer prima di assegnarlo a `k`.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a><span data-ttu-id="6e2aa-109">Parole chiave di conversione</span><span class="sxs-lookup"><span data-stu-id="6e2aa-109">Conversion Keywords</span></span>

<span data-ttu-id="6e2aa-110">Nella tabella seguente vengono illustrate le parole chiave di conversione disponibili.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-110">The following table shows the available conversion keywords.</span></span>

|<span data-ttu-id="6e2aa-111">Parola chiave di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="6e2aa-111">Type conversion keyword</span></span>|<span data-ttu-id="6e2aa-112">Converte un'espressione in un tipo di dati</span><span class="sxs-lookup"><span data-stu-id="6e2aa-112">Converts an expression to data type</span></span>|<span data-ttu-id="6e2aa-113">Tipi di dati consentiti di espressione da convertire</span><span class="sxs-lookup"><span data-stu-id="6e2aa-113">Allowable data types of expression to be converted</span></span>|
|---|---|---|
|`CBool`|[<span data-ttu-id="6e2aa-114">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="6e2aa-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="6e2aa-115">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|
|`CByte`|[<span data-ttu-id="6e2aa-116">Tipo di dati Byte</span><span class="sxs-lookup"><span data-stu-id="6e2aa-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="6e2aa-117">Qualsiasi tipo numerico (inclusi `SByte` e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CChar`|[<span data-ttu-id="6e2aa-118">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="6e2aa-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="6e2aa-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-119">`String`, `Object`</span></span>|
|`CDate`|[<span data-ttu-id="6e2aa-120">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="6e2aa-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="6e2aa-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-121">`String`, `Object`</span></span>|
|`CDbl`|[<span data-ttu-id="6e2aa-122">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="6e2aa-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="6e2aa-123">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CDec`|[<span data-ttu-id="6e2aa-124">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="6e2aa-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="6e2aa-125">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CInt`|[<span data-ttu-id="6e2aa-126">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="6e2aa-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="6e2aa-127">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CLng`|[<span data-ttu-id="6e2aa-128">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="6e2aa-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="6e2aa-129">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CObj`|[<span data-ttu-id="6e2aa-130">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="6e2aa-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="6e2aa-131">Qualsiasi tipo</span><span class="sxs-lookup"><span data-stu-id="6e2aa-131">Any type</span></span>|
|`CSByte`|[<span data-ttu-id="6e2aa-132">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="6e2aa-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="6e2aa-133">Qualsiasi tipo numerico (inclusi `Byte` e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CShort`|[<span data-ttu-id="6e2aa-134">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="6e2aa-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="6e2aa-135">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CSng`|[<span data-ttu-id="6e2aa-136">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="6e2aa-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="6e2aa-137">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CStr`|[<span data-ttu-id="6e2aa-138">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="6e2aa-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="6e2aa-139">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `Char`, `Char` Array, `Date``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|
|`CType`|<span data-ttu-id="6e2aa-140">Tipo specificato dopo la virgola (`,`)</span><span class="sxs-lookup"><span data-stu-id="6e2aa-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="6e2aa-141">Quando si esegue la conversione in un *tipo di dati Elementary* (inclusa una matrice di un tipo elementare), gli stessi tipi consentiti per la parola chiave di conversione corrispondente</span><span class="sxs-lookup"><span data-stu-id="6e2aa-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="6e2aa-142">Quando si esegue la conversione in un *tipo di dati composito*, le interfacce implementate e le classi da cui eredita</span><span class="sxs-lookup"><span data-stu-id="6e2aa-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="6e2aa-143">Quando si esegue la conversione in una classe o struttura in cui è stato sottoposto a overload `CType`, tale classe o struttura</span><span class="sxs-lookup"><span data-stu-id="6e2aa-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|
|`CUInt`|[<span data-ttu-id="6e2aa-144">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="6e2aa-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="6e2aa-145">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CULng`|[<span data-ttu-id="6e2aa-146">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="6e2aa-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="6e2aa-147">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CUShort`|[<span data-ttu-id="6e2aa-148">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="6e2aa-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="6e2aa-149">Qualsiasi tipo numerico (inclusi `Byte`, `SByte`e tipi enumerati), `Boolean`, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="6e2aa-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|

## <a name="the-ctype-function"></a><span data-ttu-id="6e2aa-150">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="6e2aa-150">The CType Function</span></span>

<span data-ttu-id="6e2aa-151">La [funzione CType](../../../../visual-basic/language-reference/functions/ctype-function.md) opera su due argomenti.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="6e2aa-152">Il primo è l'espressione da convertire e la seconda è il tipo di dati di destinazione o la classe di oggetti.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="6e2aa-153">Si noti che il primo argomento deve essere un'espressione, non un tipo.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-153">Note that the first argument must be an expression, not a type.</span></span>

<span data-ttu-id="6e2aa-154">`CType` è una *funzione inline*, ovvero il codice compilato esegue la conversione, spesso senza generare una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="6e2aa-155">Ciò migliora le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-155">This improves performance.</span></span>

<span data-ttu-id="6e2aa-156">Per un confronto tra `CType` con le altre parole chiave di conversione dei tipi, vedere [Operatore DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6e2aa-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>

### <a name="elementary-types"></a><span data-ttu-id="6e2aa-157">Tipi elementari</span><span class="sxs-lookup"><span data-stu-id="6e2aa-157">Elementary Types</span></span>

<span data-ttu-id="6e2aa-158">L'esempio seguente illustra l'uso di `CType`.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-158">The following example demonstrates the use of `CType`.</span></span>

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a><span data-ttu-id="6e2aa-159">Tipi compositi</span><span class="sxs-lookup"><span data-stu-id="6e2aa-159">Composite Types</span></span>

<span data-ttu-id="6e2aa-160">È possibile usare `CType` per convertire i valori in tipi di dati compositi e in tipi elementari.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="6e2aa-161">È anche possibile usarlo per forzare una classe di oggetti nel tipo di una delle relative interfacce, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a><span data-ttu-id="6e2aa-162">Tipi di matrice</span><span class="sxs-lookup"><span data-stu-id="6e2aa-162">Array Types</span></span>

<span data-ttu-id="6e2aa-163">`CType` inoltre possibile convertire i tipi di dati della matrice, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-163">`CType` can also convert array data types, as in the following example.</span></span>

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

<span data-ttu-id="6e2aa-164">Per ulteriori informazioni e un esempio, vedere [conversioni di matrici](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="6e2aa-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>

### <a name="types-defining-ctype"></a><span data-ttu-id="6e2aa-165">Tipi che definiscono CType</span><span class="sxs-lookup"><span data-stu-id="6e2aa-165">Types Defining CType</span></span>

<span data-ttu-id="6e2aa-166">È possibile definire `CType` su una classe o una struttura definita.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="6e2aa-167">In questo modo è possibile convertire i valori da e verso il tipo della classe o della struttura.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="6e2aa-168">Per altre informazioni e per un esempio, vedere [procedura: definire un operatore di conversione](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6e2aa-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6e2aa-169">I valori utilizzati con una parola chiave di conversione devono essere validi per il tipo di dati di destinazione oppure si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="6e2aa-170">Se, ad esempio, si tenta di convertire un `Long` in un `Integer`, il valore del `Long` deve essere compreso nell'intervallo valido per il tipo di dati `Integer`.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>

> [!CAUTION]
> <span data-ttu-id="6e2aa-171">Se il tipo di origine non deriva dal tipo di destinazione, la specifica `CType` per la conversione da un tipo di classe a un altro non riesce in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="6e2aa-172">Tale errore genera un'eccezione <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="6e2aa-173">Tuttavia, se uno dei tipi è una struttura o una classe definita e se è stato definito `CType` su tale struttura o classe, una conversione può avere esito positivo se soddisfa i requisiti del `CType`.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="6e2aa-174">Vedere [procedura: definire un operatore di conversione](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="6e2aa-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

<span data-ttu-id="6e2aa-175">L'esecuzione di una conversione esplicita è nota anche come *cast* di un'espressione a un tipo di dati o a una classe di oggetti specificati.</span><span class="sxs-lookup"><span data-stu-id="6e2aa-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e2aa-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e2aa-176">See also</span></span>

- [<span data-ttu-id="6e2aa-177">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e2aa-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="6e2aa-178">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="6e2aa-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="6e2aa-179">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e2aa-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="6e2aa-180">Strutture</span><span class="sxs-lookup"><span data-stu-id="6e2aa-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6e2aa-181">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6e2aa-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="6e2aa-182">CString</span><span class="sxs-lookup"><span data-stu-id="6e2aa-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="6e2aa-183">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="6e2aa-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
