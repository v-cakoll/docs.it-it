---
title: Conversioni implicite ed esplicite (Visual Basic)
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
ms.openlocfilehash: 09d96b304ba3bcf2a9de2812ce37ae69dba73a41
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037240"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="a8588-102">Conversioni implicite ed esplicite (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8588-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="a8588-103">Un' *conversione implicita* non richiede alcuna sintassi speciale nel codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="a8588-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="a8588-104">Nell'esempio seguente, Visual Basic converte in modo implicito il valore del `k` su un valore a virgola mobile a precisione singola prima di assegnarlo a `q`.</span><span class="sxs-lookup"><span data-stu-id="a8588-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="a8588-105">Un' *conversione esplicita* utilizza una parola chiave la conversione del tipo.</span><span class="sxs-lookup"><span data-stu-id="a8588-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="a8588-106">Visual Basic fornisce diverse parole chiave di tale tipo, che assegnano un'espressione tra parentesi per il tipo di dati desiderato.</span><span class="sxs-lookup"><span data-stu-id="a8588-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="a8588-107">Queste parole chiave fungono da funzioni, ma il compilatore genera il codice inline, in modo che l'esecuzione è leggermente più veloce con una chiamata di funzione.</span><span class="sxs-lookup"><span data-stu-id="a8588-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="a8588-108">Nell'estensione seguente dell'esempio precedente, il `CInt` parola chiave converte il valore del `q` in un intero prima di assegnarlo a `k`.</span><span class="sxs-lookup"><span data-stu-id="a8588-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="a8588-109">Parole chiave di conversione</span><span class="sxs-lookup"><span data-stu-id="a8588-109">Conversion Keywords</span></span>  
 <span data-ttu-id="a8588-110">La tabella seguente illustra le parole chiave di conversione disponibili.</span><span class="sxs-lookup"><span data-stu-id="a8588-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="a8588-111">Parola chiave di conversione tipo</span><span class="sxs-lookup"><span data-stu-id="a8588-111">Type conversion keyword</span></span>|<span data-ttu-id="a8588-112">Converte un'espressione al tipo di dati</span><span class="sxs-lookup"><span data-stu-id="a8588-112">Converts an expression to data type</span></span>|<span data-ttu-id="a8588-113">Tipi di dati consentiti dell'espressione da convertire</span><span class="sxs-lookup"><span data-stu-id="a8588-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="a8588-114">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="a8588-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="a8588-115">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="a8588-116">Tipo di dati Byte</span><span class="sxs-lookup"><span data-stu-id="a8588-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="a8588-117">Qualsiasi tipo numerico (incluso `SByte` e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="a8588-118">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="a8588-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="a8588-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="a8588-120">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="a8588-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="a8588-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="a8588-122">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="a8588-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="a8588-123">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="a8588-124">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="a8588-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="a8588-125">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="a8588-126">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="a8588-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="a8588-127">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="a8588-128">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="a8588-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="a8588-129">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="a8588-130">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="a8588-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="a8588-131">Qualsiasi tipo</span><span class="sxs-lookup"><span data-stu-id="a8588-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="a8588-132">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="a8588-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="a8588-133">Qualsiasi tipo numerico (incluso `Byte` e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="a8588-134">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="a8588-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="a8588-135">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="a8588-136">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="a8588-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="a8588-137">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="a8588-138">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="a8588-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="a8588-139">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `Char`, `Char` matrice, `Date`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="a8588-140">Tipo specificato dopo la virgola (`,`)</span><span class="sxs-lookup"><span data-stu-id="a8588-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="a8588-141">Durante la conversione in un *tipo di dati elementare* (inclusa un'ampia gamma di un tipo elementare), lo stesso tipi consentito per la parola chiave corrispondente</span><span class="sxs-lookup"><span data-stu-id="a8588-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="a8588-142">Durante la conversione in un *tipo di dati composito*, le interfacce implementate e le classi da cui eredita</span><span class="sxs-lookup"><span data-stu-id="a8588-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="a8588-143">Durante la conversione in una classe o struttura in cui hanno eseguito l'overload `CType`, tale classe o struttura</span><span class="sxs-lookup"><span data-stu-id="a8588-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="a8588-144">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="a8588-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="a8588-145">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="a8588-146">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="a8588-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="a8588-147">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="a8588-148">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="a8588-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="a8588-149">Qualsiasi tipo numerico (incluso `Byte`, `SByte`e i tipi enumerati), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="a8588-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="a8588-150">La funzione CType</span><span class="sxs-lookup"><span data-stu-id="a8588-150">The CType Function</span></span>  
 <span data-ttu-id="a8588-151">Il [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) opera su due argomenti.</span><span class="sxs-lookup"><span data-stu-id="a8588-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="a8588-152">Il primo è l'espressione da convertire e il secondo è la classe di tipo o un oggetto data destinazione.</span><span class="sxs-lookup"><span data-stu-id="a8588-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="a8588-153">Si noti che il primo argomento deve essere un'espressione, non è un tipo.</span><span class="sxs-lookup"><span data-stu-id="a8588-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="a8588-154">`CType` è un' *funzione inline*, vale a dire il codice compilato effettua la conversione, spesso senza la generazione di una funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="a8588-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="a8588-155">Ciò migliora le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a8588-155">This improves performance.</span></span>  
  
 <span data-ttu-id="a8588-156">Per un confronto delle `CType` con l'altra tipo parole chiave di conversione, vedere [operatore DirectCast](../../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a8588-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="a8588-157">Tipi di base</span><span class="sxs-lookup"><span data-stu-id="a8588-157">Elementary Types</span></span>  
 <span data-ttu-id="a8588-158">L'esempio seguente illustra l'uso di `CType`.</span><span class="sxs-lookup"><span data-stu-id="a8588-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="a8588-159">Tipi composti</span><span class="sxs-lookup"><span data-stu-id="a8588-159">Composite Types</span></span>  
 <span data-ttu-id="a8588-160">È possibile usare `CType` per convertire i valori in tipi di dati compositi anche in tipi di base.</span><span class="sxs-lookup"><span data-stu-id="a8588-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="a8588-161">È anche possibile usarlo da assegnare a una classe di oggetti per il tipo di una delle relative interfacce, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a8588-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="a8588-162">Tipi di matrice</span><span class="sxs-lookup"><span data-stu-id="a8588-162">Array Types</span></span>  
 <span data-ttu-id="a8588-163">`CType` Inoltre è possibile convertire i tipi di dati di matrice, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="a8588-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 <span data-ttu-id="a8588-164">Per altre informazioni e un esempio, vedere [conversioni di matrici](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="a8588-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="a8588-165">Tipi che definiscono CType</span><span class="sxs-lookup"><span data-stu-id="a8588-165">Types Defining CType</span></span>  
 <span data-ttu-id="a8588-166">È possibile definire `CType` in una classe o struttura definita.</span><span class="sxs-lookup"><span data-stu-id="a8588-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="a8588-167">In questo modo è possibile convertire i valori da e verso il tipo di classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="a8588-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="a8588-168">Per altre informazioni e un esempio, vedere [procedura: definire un operatore di conversione](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a8588-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8588-169">I valori utilizzati con una parola chiave di conversione devono essere validi per il tipo di dati di destinazione o si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="a8588-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="a8588-170">Ad esempio, se si prova a convertire un `Long` a un `Integer`, il valore della `Long` deve essere compreso nell'intervallo valido per il `Integer` tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="a8588-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a8588-171">Specifica di `CType` per convertire un tipo di classe in un altro non riesce in fase di esecuzione se il tipo di origine non deriva dal tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a8588-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="a8588-172">Questo errore genera un <xref:System.InvalidCastException> eccezione.</span><span class="sxs-lookup"><span data-stu-id="a8588-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="a8588-173">Tuttavia, se uno dei tipi è una struttura o una classe è stato definito e se sono stati definiti `CType` su tale classe o struttura, una conversione può avere esito positivo se soddisfa i requisiti del `CType`.</span><span class="sxs-lookup"><span data-stu-id="a8588-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="a8588-174">Visualizzare [procedura: definire un operatore di conversione](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a8588-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="a8588-175">L'esecuzione di una conversione esplicita è noto anche come *cast* un'espressione a una classe di tipo o un oggetto dati specificato.</span><span class="sxs-lookup"><span data-stu-id="a8588-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8588-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8588-176">See Also</span></span>  
 [<span data-ttu-id="a8588-177">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8588-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="a8588-178">Conversioni fra stringhe e altri tipi</span><span class="sxs-lookup"><span data-stu-id="a8588-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 [<span data-ttu-id="a8588-179">Procedura: convertire un oggetto in un altro tipo in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8588-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="a8588-180">Strutture</span><span class="sxs-lookup"><span data-stu-id="a8588-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="a8588-181">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a8588-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="a8588-182">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="a8588-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="a8588-183">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="a8588-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
