---
title: Funzioni di conversione del tipo (Visual Basic)
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: 0516a579c1ad9944284d25f2f057f2f03619bbab
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582982"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="19431-102">Funzioni di conversione del tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19431-102">Type Conversion Functions (Visual Basic)</span></span>

<span data-ttu-id="19431-103">Queste funzioni vengono compilate inline, ovvero il codice di conversione fa parte del codice che valuta l'espressione.</span><span class="sxs-lookup"><span data-stu-id="19431-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="19431-104">A volte non viene eseguita alcuna chiamata a una procedura per eseguire la conversione, migliorando le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="19431-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="19431-105">Ogni funzione assegna un'espressione a un tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="19431-105">Each function coerces an expression to a specific data type.</span></span>

## <a name="syntax"></a><span data-ttu-id="19431-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19431-106">Syntax</span></span>

```vb
CBool(expression)
CByte(expression)
CChar(expression)
CDate(expression)
CDbl(expression)
CDec(expression)
CInt(expression)
CLng(expression)
CObj(expression)
CSByte(expression)
CShort(expression)
CSng(expression)
CStr(expression)
CUInt(expression)
CULng(expression)
CUShort(expression)
```

## <a name="part"></a><span data-ttu-id="19431-107">Parte</span><span class="sxs-lookup"><span data-stu-id="19431-107">Part</span></span>

`expression`  
<span data-ttu-id="19431-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="19431-108">Required.</span></span> <span data-ttu-id="19431-109">Qualsiasi espressione del tipo di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="19431-109">Any expression of the source data type.</span></span>

## <a name="return-value-data-type"></a><span data-ttu-id="19431-110">Tipo di dati del valore restituito</span><span class="sxs-lookup"><span data-stu-id="19431-110">Return Value Data Type</span></span>

<span data-ttu-id="19431-111">Il nome della funzione determina il tipo di dati del valore restituito, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="19431-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>

|<span data-ttu-id="19431-112">Nome funzione</span><span class="sxs-lookup"><span data-stu-id="19431-112">Function name</span></span>|<span data-ttu-id="19431-113">Tipo di dati restituito</span><span class="sxs-lookup"><span data-stu-id="19431-113">Return data type</span></span>|<span data-ttu-id="19431-114">Intervallo per argomento `expression`</span><span class="sxs-lookup"><span data-stu-id="19431-114">Range for `expression` argument</span></span>|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[<span data-ttu-id="19431-115">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="19431-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="19431-116">Qualsiasi espressione `Char` o `String` o numeric valida.</span><span class="sxs-lookup"><span data-stu-id="19431-116">Any valid `Char` or `String` or numeric expression.</span></span>|
|`CByte`|[<span data-ttu-id="19431-117">Tipo di dati Byte</span><span class="sxs-lookup"><span data-stu-id="19431-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="19431-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) tramite <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (senza segno); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="19431-119">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione da virgola mobile a byte con la funzione `CByte`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-120">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-120">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CChar`|[<span data-ttu-id="19431-121">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="19431-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="19431-122">Qualsiasi espressione `Char` o `String` valida; viene convertito solo il primo carattere di un `String`; il valore può essere compreso tra 0 e 65535 (senza segno).</span><span class="sxs-lookup"><span data-stu-id="19431-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|
|`CDate`|[<span data-ttu-id="19431-123">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="19431-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="19431-124">Qualsiasi rappresentazione valida di data e ora.</span><span class="sxs-lookup"><span data-stu-id="19431-124">Any valid representation of a date and time.</span></span>|
|`CDbl`|[<span data-ttu-id="19431-125">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="19431-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="19431-126">-1.79769313486231570 e + 308 a-4.94065645841246544 E-324 per i valori negativi; 4.94065645841246544 e-324 tramite 1.79769313486231570 E + 308 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="19431-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|
|`CDec`|[<span data-ttu-id="19431-127">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="19431-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="19431-128">+/-79.228.162.514.264.337.593.543.950.335 per numeri con scala zero, ovvero numeri senza posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="19431-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="19431-129">Per i numeri con 28 cifre decimali, l'intervallo è +/-7.9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="19431-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="19431-130">Il numero più piccolo possibile diverso da zero è 0,0000000000000000000000000001 (+/-1E-28).</span><span class="sxs-lookup"><span data-stu-id="19431-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|
|`CInt`|[<span data-ttu-id="19431-131">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="19431-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="19431-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2.147.483.648) tramite <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="19431-133">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione da virgola mobile a integer con la funzione `CInt`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-134">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-134">See the [CInt Example](#cint-example) section for an example.</span></span> |
|`CLng`|[<span data-ttu-id="19431-135">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="19431-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="19431-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9.223.372.036.854.775.808) tramite <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="19431-137">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione di interi a virgola mobile a 64 bit con la funzione `CLng`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-138">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-138">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CObj`|[<span data-ttu-id="19431-139">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="19431-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="19431-140">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="19431-140">Any valid expression.</span></span>|
|`CSByte`|[<span data-ttu-id="19431-141">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="19431-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="19431-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) tramite <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="19431-143">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione in byte a virgola mobile e con firma con la funzione `CSByte`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-144">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-144">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CShort`|[<span data-ttu-id="19431-145">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="19431-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="19431-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) tramite <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="19431-147">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione da virgola mobile a a 16 bit con la funzione `CShort`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-148">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-148">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CSng`|[<span data-ttu-id="19431-149">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="19431-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="19431-150">-3 402823e38 e + 38 fino a-401298E E-45 per i valori negativi; 401298E e-45 tramite 3 402823e38 E + 38 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="19431-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|
|`CStr`|[<span data-ttu-id="19431-151">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="19431-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="19431-152">Restituisce per `CStr` dipendono dall'argomento `expression`.</span><span class="sxs-lookup"><span data-stu-id="19431-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="19431-153">Vedere [valori restituiti per la funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="19431-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|
|`CUInt`|[<span data-ttu-id="19431-154">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="19431-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="19431-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) tramite <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (senza segno); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="19431-156">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione a virgola mobile e Unsigned Integer con la funzione `CUInt`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-157">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-157">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CULng`|[<span data-ttu-id="19431-158">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="19431-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="19431-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) tramite <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18.446.744.073.709.551.615) (senza segno); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="19431-160">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione a virgola mobile e long integer senza segno con la funzione `CULng`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-161">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-161">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CUShort`|[<span data-ttu-id="19431-162">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="19431-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="19431-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) tramite <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (senza segno); le parti frazionarie sono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="19431-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="19431-164">A partire da Visual Basic 15,8, Visual Basic ottimizza le prestazioni della conversione di interi a 16 bit senza segno a virgola mobile con la funzione `CUShort`; Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .</span><span class="sxs-lookup"><span data-stu-id="19431-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="19431-165">Per un esempio, vedere la sezione di [esempio CInt](#cint-example) .</span><span class="sxs-lookup"><span data-stu-id="19431-165">See the [CInt Example](#cint-example) section for an example.</span></span>|

<span data-ttu-id="19431-166"><sup>1</sup> le parti frazionarie possono essere soggette a un tipo speciale di arrotondamento denominato *arrotondamento del banco*.</span><span class="sxs-lookup"><span data-stu-id="19431-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="19431-167">Per ulteriori informazioni, vedere la sezione "osservazioni".</span><span class="sxs-lookup"><span data-stu-id="19431-167">See "Remarks" for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="19431-168">Note</span><span class="sxs-lookup"><span data-stu-id="19431-168">Remarks</span></span>

<span data-ttu-id="19431-169">Come regola, è consigliabile usare le funzioni di conversione dei tipi di Visual Basic in preferenza ai metodi di .NET Framework, ad esempio `ToString()`, nella classe <xref:System.Convert> o in una singola struttura o classe del tipo.</span><span class="sxs-lookup"><span data-stu-id="19431-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="19431-170">Le funzioni Visual Basic sono progettate per un'interazione ottimale con il codice Visual Basic e rendono anche il codice sorgente più breve e più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="19431-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="19431-171">Inoltre, i metodi di conversione .NET Framework non producono sempre gli stessi risultati delle funzioni di Visual Basic, ad esempio quando si converte `Boolean` in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="19431-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="19431-172">Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="19431-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

<span data-ttu-id="19431-173">A partire da Visual Basic 15,8, le prestazioni della conversione da virgola mobile a integer sono ottimizzate quando si passa il valore <xref:System.Single> o <xref:System.Double> restituito dai metodi seguenti a una delle funzioni di conversione integer (`CByte`, `CShort`, `CInt` @no__ t_5, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="19431-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="19431-174">Questa ottimizzazione consente di eseguire il codice che esegue un numero elevato di conversioni di valori integer fino a due volte più velocemente.</span><span class="sxs-lookup"><span data-stu-id="19431-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="19431-175">Nell'esempio seguente vengono illustrate le conversioni a virgola mobile ottimizzate:</span><span class="sxs-lookup"><span data-stu-id="19431-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="19431-176">Comportamento</span><span class="sxs-lookup"><span data-stu-id="19431-176">Behavior</span></span>

- <span data-ttu-id="19431-177">**Coercizione.**</span><span class="sxs-lookup"><span data-stu-id="19431-177">**Coercion.**</span></span> <span data-ttu-id="19431-178">In generale, è possibile utilizzare le funzioni di conversione del tipo di dati per assegnare il risultato di un'operazione a un tipo di dati specifico anziché al tipo di dati predefinito.</span><span class="sxs-lookup"><span data-stu-id="19431-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="19431-179">Usare, ad esempio, `CDec` per forzare l'aritmetica decimale nei casi in cui in genere si verificano operazioni aritmetiche a precisione singola, a precisione doppia o Integer.</span><span class="sxs-lookup"><span data-stu-id="19431-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>

- <span data-ttu-id="19431-180">**Conversioni non riuscite.**</span><span class="sxs-lookup"><span data-stu-id="19431-180">**Failed Conversions.**</span></span> <span data-ttu-id="19431-181">Se il `expression` passato alla funzione non è compreso nell'intervallo del tipo di dati in cui deve essere convertito, viene eseguita una <xref:System.OverflowException>.</span><span class="sxs-lookup"><span data-stu-id="19431-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>

- <span data-ttu-id="19431-182">**Parti frazionarie.**</span><span class="sxs-lookup"><span data-stu-id="19431-182">**Fractional Parts.**</span></span> <span data-ttu-id="19431-183">Quando si converte un valore non integrale in un tipo integrale, le funzioni di conversione integer (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng` e `CUShort`) rimuovono la parte frazionaria e arrotondano il valore all'intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="19431-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>

     <span data-ttu-id="19431-184">Se la parte frazionaria è esattamente 0,5, le funzioni di conversione integer arrotondano al numero intero pari più vicino.</span><span class="sxs-lookup"><span data-stu-id="19431-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="19431-185">0,5, ad esempio, viene arrotondato a 0, 1,5 e 2,5 entrambi arrotondati a 2.</span><span class="sxs-lookup"><span data-stu-id="19431-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="19431-186">Questa operazione viene talvolta denominata *arrotondamento del banco*e il suo scopo consiste nel compensare la distorsione che potrebbe accumularsi durante l'aggiunta di molti di questi numeri.</span><span class="sxs-lookup"><span data-stu-id="19431-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>

     <span data-ttu-id="19431-187">`CInt` e `CLng` differiscono dalle funzioni <xref:Microsoft.VisualBasic.Conversion.Int%2A> e <xref:Microsoft.VisualBasic.Conversion.Fix%2A>, che troncano, anziché arrotondare, la parte frazionaria di un numero.</span><span class="sxs-lookup"><span data-stu-id="19431-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="19431-188">Inoltre, `Fix` e `Int` restituiscono sempre un valore dello stesso tipo di dati passato.</span><span class="sxs-lookup"><span data-stu-id="19431-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>

- <span data-ttu-id="19431-189">**Conversioni di data e ora.**</span><span class="sxs-lookup"><span data-stu-id="19431-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="19431-190">Utilizzare la funzione <xref:Microsoft.VisualBasic.Information.IsDate%2A> per determinare se un valore può essere convertito in una data e ora.</span><span class="sxs-lookup"><span data-stu-id="19431-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="19431-191">`CDate` riconosce i valori letterali di data e ora, ma non i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="19431-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="19431-192">Per convertire un valore di `Date` Visual Basic 6,0 in un valore `Date` in Visual Basic 2005 o versioni successive, è possibile usare il metodo <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="19431-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="19431-193">**Valori di data/ora neutri.**</span><span class="sxs-lookup"><span data-stu-id="19431-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="19431-194">Il [tipo di dati date](../../../visual-basic/language-reference/data-types/date-data-type.md) contiene sempre le informazioni di data e ora.</span><span class="sxs-lookup"><span data-stu-id="19431-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="19431-195">Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 gennaio dell'anno 1) come *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora.</span><span class="sxs-lookup"><span data-stu-id="19431-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="19431-196">Se si converte un valore `Date` in una stringa, `CStr` non include valori neutri nella stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="19431-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="19431-197">Se ad esempio si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato sarà "9:30:00 AM"; le informazioni sulla data vengono omesse.</span><span class="sxs-lookup"><span data-stu-id="19431-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="19431-198">Tuttavia, le informazioni sulla data sono ancora presenti nel valore di `Date` originale e possono essere ripristinate con funzioni come <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> funzione.</span><span class="sxs-lookup"><span data-stu-id="19431-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>

- <span data-ttu-id="19431-199">**Sensibilità delle impostazioni cultura.**</span><span class="sxs-lookup"><span data-stu-id="19431-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="19431-200">Le funzioni di conversione dei tipi che coinvolgono stringhe eseguono conversioni in base alle impostazioni cultura correnti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="19431-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="19431-201">@No__t_0, ad esempio, riconosce i formati di data in base alle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="19431-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="19431-202">È necessario specificare il giorno, il mese e l'anno nell'ordine corretto per le impostazioni locali o la data potrebbe non essere interpretata correttamente.</span><span class="sxs-lookup"><span data-stu-id="19431-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="19431-203">Un formato di data estesa non viene riconosciuto se contiene una stringa del giorno della settimana, ad esempio "mercoledì".</span><span class="sxs-lookup"><span data-stu-id="19431-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>

     <span data-ttu-id="19431-204">Se è necessario eseguire la conversione da o verso una rappresentazione di stringa di un valore in un formato diverso da quello specificato dalle impostazioni locali, non è possibile usare le funzioni di conversione del tipo di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="19431-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="19431-205">A tale scopo, usare i metodi `ToString(IFormatProvider)` e `Parse(String, IFormatProvider)` del tipo di tale valore.</span><span class="sxs-lookup"><span data-stu-id="19431-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="19431-206">Usare, ad esempio, <xref:System.Double.Parse%2A?displayProperty=nameWithType> durante la conversione di una stringa in una `Double` e usare <xref:System.Double.ToString%2A?displayProperty=nameWithType> quando si converte un valore di tipo `Double` in una stringa.</span><span class="sxs-lookup"><span data-stu-id="19431-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>

## <a name="ctype-function"></a><span data-ttu-id="19431-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="19431-207">CType Function</span></span>

<span data-ttu-id="19431-208">La [funzione CType](../../../visual-basic/language-reference/functions/ctype-function.md) accetta un secondo argomento, `typename` e assegna `expression` a `typename`, dove `typename` può essere qualsiasi tipo di dati, struttura, classe o interfaccia a cui esiste una conversione valida.</span><span class="sxs-lookup"><span data-stu-id="19431-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>

<span data-ttu-id="19431-209">Per un confronto tra `CType` con le altre parole chiave di conversione dei tipi, vedere [Operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="19431-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>

## <a name="cbool-example"></a><span data-ttu-id="19431-210">Esempio di CBool</span><span class="sxs-lookup"><span data-stu-id="19431-210">CBool Example</span></span>

<span data-ttu-id="19431-211">Nell'esempio seguente viene utilizzata la funzione `CBool` per convertire espressioni in valori `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="19431-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="19431-212">Se un'espressione restituisce un valore diverso da zero, `CBool` restituisce `True`; in caso contrario, restituisce `False`.</span><span class="sxs-lookup"><span data-stu-id="19431-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a><span data-ttu-id="19431-213">Esempio di CByte</span><span class="sxs-lookup"><span data-stu-id="19431-213">CByte Example</span></span>

<span data-ttu-id="19431-214">Nell'esempio seguente viene utilizzata la funzione `CByte` per convertire un'espressione in un `Byte`.</span><span class="sxs-lookup"><span data-stu-id="19431-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a><span data-ttu-id="19431-215">Esempio di CChar</span><span class="sxs-lookup"><span data-stu-id="19431-215">CChar Example</span></span>

<span data-ttu-id="19431-216">Nell'esempio seguente viene utilizzata la funzione `CChar` per convertire il primo carattere di un'espressione `String` in un tipo di `Char`.</span><span class="sxs-lookup"><span data-stu-id="19431-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

<span data-ttu-id="19431-217">Il tipo di dati dell'argomento di input `CChar` deve essere `Char` o `String`.</span><span class="sxs-lookup"><span data-stu-id="19431-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="19431-218">Non è possibile usare `CChar` per convertire un numero in un carattere, perché `CChar` non può accettare un tipo di dati numerico.</span><span class="sxs-lookup"><span data-stu-id="19431-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="19431-219">Nell'esempio seguente viene ottenuto un numero che rappresenta un punto di codice (codice carattere) e lo converte nel carattere corrispondente.</span><span class="sxs-lookup"><span data-stu-id="19431-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="19431-220">Usa la funzione <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> per ottenere la stringa di cifre, `CInt` per convertire la stringa nel tipo `Integer` e `ChrW` per convertire il numero nel tipo `Char`.</span><span class="sxs-lookup"><span data-stu-id="19431-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a><span data-ttu-id="19431-221">Esempio di CDate</span><span class="sxs-lookup"><span data-stu-id="19431-221">CDate Example</span></span>

<span data-ttu-id="19431-222">Nell'esempio seguente viene usata la funzione `CDate` per convertire le stringhe in valori `Date`.</span><span class="sxs-lookup"><span data-stu-id="19431-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="19431-223">In generale, le date e le ore di codifica hardcoded come stringhe, come illustrato in questo esempio, non sono consigliate.</span><span class="sxs-lookup"><span data-stu-id="19431-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="19431-224">Usare i valori letterali di data e ora, ad esempio #Feb 12, 1969 # e #4:45:23 PM #, in alternativa.</span><span class="sxs-lookup"><span data-stu-id="19431-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a><span data-ttu-id="19431-225">Esempio di CDbl</span><span class="sxs-lookup"><span data-stu-id="19431-225">CDbl Example</span></span>

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a><span data-ttu-id="19431-226">Esempio di CDec</span><span class="sxs-lookup"><span data-stu-id="19431-226">CDec Example</span></span>

<span data-ttu-id="19431-227">Nell'esempio seguente viene utilizzata la funzione `CDec` per convertire un valore numerico in `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="19431-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a><span data-ttu-id="19431-228">Esempio di CInt</span><span class="sxs-lookup"><span data-stu-id="19431-228">CInt Example</span></span>

<span data-ttu-id="19431-229">Nell'esempio seguente viene utilizzata la funzione `CInt` per convertire un valore in `Integer`.</span><span class="sxs-lookup"><span data-stu-id="19431-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a><span data-ttu-id="19431-230">Esempio di CLng</span><span class="sxs-lookup"><span data-stu-id="19431-230">CLng Example</span></span>

<span data-ttu-id="19431-231">Nell'esempio seguente viene utilizzata la funzione `CLng` per convertire i valori `Long`.</span><span class="sxs-lookup"><span data-stu-id="19431-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a><span data-ttu-id="19431-232">Esempio di CObj</span><span class="sxs-lookup"><span data-stu-id="19431-232">CObj Example</span></span>

<span data-ttu-id="19431-233">Nell'esempio seguente viene utilizzata la funzione `CObj` per convertire un valore numerico in `Object`.</span><span class="sxs-lookup"><span data-stu-id="19431-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="19431-234">La variabile `Object` contiene solo un puntatore a quattro byte, che punta al valore `Double` assegnato.</span><span class="sxs-lookup"><span data-stu-id="19431-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a><span data-ttu-id="19431-235">Esempio di CSByte</span><span class="sxs-lookup"><span data-stu-id="19431-235">CSByte Example</span></span>

<span data-ttu-id="19431-236">Nell'esempio seguente viene utilizzata la funzione `CSByte` per convertire un valore numerico in `SByte`.</span><span class="sxs-lookup"><span data-stu-id="19431-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a><span data-ttu-id="19431-237">Esempio di CShort</span><span class="sxs-lookup"><span data-stu-id="19431-237">CShort Example</span></span>

<span data-ttu-id="19431-238">Nell'esempio seguente viene utilizzata la funzione `CShort` per convertire un valore numerico in `Short`.</span><span class="sxs-lookup"><span data-stu-id="19431-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a><span data-ttu-id="19431-239">Esempio di CSng</span><span class="sxs-lookup"><span data-stu-id="19431-239">CSng Example</span></span>

<span data-ttu-id="19431-240">Nell'esempio seguente viene utilizzata la funzione `CSng` per convertire i valori `Single`.</span><span class="sxs-lookup"><span data-stu-id="19431-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a><span data-ttu-id="19431-241">Esempio di CStr</span><span class="sxs-lookup"><span data-stu-id="19431-241">CStr Example</span></span>

<span data-ttu-id="19431-242">Nell'esempio seguente viene utilizzata la funzione `CStr` per convertire un valore numerico in `String`.</span><span class="sxs-lookup"><span data-stu-id="19431-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

<span data-ttu-id="19431-243">Nell'esempio seguente viene utilizzata la funzione `CStr` per convertire i valori di `Date` in `String` valori.</span><span class="sxs-lookup"><span data-stu-id="19431-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

<span data-ttu-id="19431-244">`CStr` esegue sempre il rendering di un valore `Date` nel formato breve standard per le impostazioni locali correnti, ad esempio, "6/15/2003 4:35:47 PM".</span><span class="sxs-lookup"><span data-stu-id="19431-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="19431-245">Tuttavia, `CStr` non vengono eliminati i *valori neutri* 1/1/0001 per la data e 00:00:00 per l'ora.</span><span class="sxs-lookup"><span data-stu-id="19431-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>

<span data-ttu-id="19431-246">Per informazioni più dettagliate sui valori restituiti da `CStr`, vedere [valori restituiti per la funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="19431-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>

## <a name="cuint-example"></a><span data-ttu-id="19431-247">Esempio di CUInt</span><span class="sxs-lookup"><span data-stu-id="19431-247">CUInt Example</span></span>

<span data-ttu-id="19431-248">Nell'esempio seguente viene utilizzata la funzione `CUInt` per convertire un valore numerico in `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="19431-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a><span data-ttu-id="19431-249">Esempio di CULng</span><span class="sxs-lookup"><span data-stu-id="19431-249">CULng Example</span></span>

<span data-ttu-id="19431-250">Nell'esempio seguente viene utilizzata la funzione `CULng` per convertire un valore numerico in `ULong`.</span><span class="sxs-lookup"><span data-stu-id="19431-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a><span data-ttu-id="19431-251">Esempio di CUShort</span><span class="sxs-lookup"><span data-stu-id="19431-251">CUShort Example</span></span>

<span data-ttu-id="19431-252">Nell'esempio seguente viene utilizzata la funzione `CUShort` per convertire un valore numerico in `UShort`.</span><span class="sxs-lookup"><span data-stu-id="19431-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a><span data-ttu-id="19431-253">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19431-253">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="19431-254">Funzioni di conversione</span><span class="sxs-lookup"><span data-stu-id="19431-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="19431-255">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19431-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
