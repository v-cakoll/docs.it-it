---
title: Funzioni di conversione del tipo (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605082"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="50103-102">Funzioni di conversione del tipo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50103-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="50103-103">Queste funzioni vengono compilate inline, ovvero che la conversione di codice fa parte del codice che valuta l'espressione.</span><span class="sxs-lookup"><span data-stu-id="50103-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="50103-104">A volte non sussiste alcuna chiamata a una stored procedure per eseguire la conversione, che migliora le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="50103-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="50103-105">Ogni funzione forza un'espressione al tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="50103-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50103-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50103-106">Syntax</span></span>  
  
```  
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
  
## <a name="part"></a><span data-ttu-id="50103-107">Parte</span><span class="sxs-lookup"><span data-stu-id="50103-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="50103-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="50103-108">Required.</span></span> <span data-ttu-id="50103-109">Qualsiasi espressione del tipo di dati di origine.</span><span class="sxs-lookup"><span data-stu-id="50103-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="50103-110">Tipo di dati di valore restituito</span><span class="sxs-lookup"><span data-stu-id="50103-110">Return Value Data Type</span></span>  
 <span data-ttu-id="50103-111">Il nome della funzione determina il tipo di dati del valore che viene restituito, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="50103-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="50103-112">Nome della funzione</span><span class="sxs-lookup"><span data-stu-id="50103-112">Function name</span></span>|<span data-ttu-id="50103-113">Tipo di dati restituito</span><span class="sxs-lookup"><span data-stu-id="50103-113">Return data type</span></span>|<span data-ttu-id="50103-114">Intervallo per `expression` argomento</span><span class="sxs-lookup"><span data-stu-id="50103-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="50103-115">Tipo di dati Boolean</span><span class="sxs-lookup"><span data-stu-id="50103-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="50103-116">Qualsiasi `Char` o `String` o espressione numerica.</span><span class="sxs-lookup"><span data-stu-id="50103-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="50103-117">Tipo di dati Byte</span><span class="sxs-lookup"><span data-stu-id="50103-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="50103-118">da 0 a 255 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-118">0 through 255 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CChar`|[<span data-ttu-id="50103-119">Tipo di dati Char</span><span class="sxs-lookup"><span data-stu-id="50103-119">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="50103-120">Qualsiasi `Char` o `String` espressione; solo primo carattere di un `String` viene convertito; valore può essere 0 e 65535 (senza segno).</span><span class="sxs-lookup"><span data-stu-id="50103-120">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="50103-121">Tipo di dati Date</span><span class="sxs-lookup"><span data-stu-id="50103-121">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="50103-122">Qualsiasi rappresentazione valida di una data e ora.</span><span class="sxs-lookup"><span data-stu-id="50103-122">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="50103-123">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="50103-123">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="50103-124">-1.79769313486231570 e + 308 e - 4, 94065645841246544E-324 per valori negativi. 4, 94065645841246544E-324 e 1.79769313486231570 e + 308 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="50103-124">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="50103-125">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="50103-125">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="50103-126">+ /-79.228.162.514.264.337.593.543.950.335 per zero-numeri, ovvero numeri senza cifre decimali.</span><span class="sxs-lookup"><span data-stu-id="50103-126">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="50103-127">Per i numeri con 28 cifre decimali, l'intervallo è + /-7,9228162514264337593543950335.</span><span class="sxs-lookup"><span data-stu-id="50103-127">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="50103-128">Il minor numero possibile di diverso da zero è 0,0000000000000000000000000001 (+ /-1E-28).</span><span class="sxs-lookup"><span data-stu-id="50103-128">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="50103-129">Tipo di dati Integer</span><span class="sxs-lookup"><span data-stu-id="50103-129">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="50103-130">tra -2.147.483.648 e 2.147.483.647. parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-130">-2,147,483,648 through 2,147,483,647; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CLng`|[<span data-ttu-id="50103-131">Tipo di dati Long</span><span class="sxs-lookup"><span data-stu-id="50103-131">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="50103-132">-9.223.372.036.854.775.808 a 9.223.372.036.854.775.807; parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-132">-9,223,372,036,854,775,808 through 9,223,372,036,854,775,807; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CObj`|[<span data-ttu-id="50103-133">Tipo di dati Object</span><span class="sxs-lookup"><span data-stu-id="50103-133">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="50103-134">Qualsiasi espressione valida.</span><span class="sxs-lookup"><span data-stu-id="50103-134">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="50103-135">Tipo di dati SByte</span><span class="sxs-lookup"><span data-stu-id="50103-135">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="50103-136">-128 e 127; parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-136">-128 through 127; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CShort`|[<span data-ttu-id="50103-137">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="50103-137">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="50103-138">da -32.768 e 32.767; parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-138">-32,768 through 32,767; fractional parts are rounded.<sup>1</sup></span></span>|  
|`CSng`|[<span data-ttu-id="50103-139">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="50103-139">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="50103-140">-3, 402823E + 38 a - 1, 401298E-45 per valori negativi. 1, 401298E-45 a 3, 402823E + 38 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="50103-140">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="50103-141">Tipo di dati String</span><span class="sxs-lookup"><span data-stu-id="50103-141">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="50103-142">Restituisce per `CStr` dipendono il `expression` argomento.</span><span class="sxs-lookup"><span data-stu-id="50103-142">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="50103-143">Vedere [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="50103-143">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="50103-144">Tipo di dati UInteger</span><span class="sxs-lookup"><span data-stu-id="50103-144">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="50103-145">da 0 a 4.294.967.295 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-145">0 through 4,294,967,295 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CULng`|[<span data-ttu-id="50103-146">Tipo di dati ULong</span><span class="sxs-lookup"><span data-stu-id="50103-146">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="50103-147">da 0 a 18.446.744.073.709.551.615 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-147">0 through 18,446,744,073,709,551,615 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
|`CUShort`|[<span data-ttu-id="50103-148">Tipo di dati UShort</span><span class="sxs-lookup"><span data-stu-id="50103-148">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="50103-149">da 0 a 65.535 (senza segno). parti frazionarie vengono arrotondate. <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="50103-149">0 through 65,535 (unsigned); fractional parts are rounded.<sup>1</sup></span></span>|  
  
 <span data-ttu-id="50103-150"><sup>1</sup> parti frazionarie possono essere soggetta a un tipo speciale di arrotondamento chiamato *arrotondamento*.</span><span class="sxs-lookup"><span data-stu-id="50103-150"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="50103-151">Per ulteriori informazioni, vedere "la sezione Osservazioni".</span><span class="sxs-lookup"><span data-stu-id="50103-151">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50103-152">Note</span><span class="sxs-lookup"><span data-stu-id="50103-152">Remarks</span></span>  
 <span data-ttu-id="50103-153">Come regola, utilizzare le funzioni di conversione di tipo Visual Basic anziché i metodi di .NET Framework, ad esempio `ToString()`, entrambi nel <xref:System.Convert> classe o in una classe o struttura di tipo individuale.</span><span class="sxs-lookup"><span data-stu-id="50103-153">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="50103-154">Le funzioni di Visual Basic sono progettate per l'interazione ottimale con codice di Visual Basic e rendono il codice sorgente più breve e facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="50103-154">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="50103-155">Inoltre, i metodi di conversione di .NET Framework non producono sempre gli stessi risultati di funzioni di Visual Basic, ad esempio durante la conversione `Boolean` a `Integer`.</span><span class="sxs-lookup"><span data-stu-id="50103-155">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="50103-156">Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="50103-156">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="50103-157">Comportamento</span><span class="sxs-lookup"><span data-stu-id="50103-157">Behavior</span></span>  
  
-   <span data-ttu-id="50103-158">**Coercizione.**</span><span class="sxs-lookup"><span data-stu-id="50103-158">**Coercion.**</span></span> <span data-ttu-id="50103-159">In generale, è possibile utilizzare le funzioni di conversione di tipo di dati per assegnare il risultato di un'operazione a un particolare tipo di dati anziché il tipo di dati predefinito.</span><span class="sxs-lookup"><span data-stu-id="50103-159">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="50103-160">Ad esempio, utilizzare `CDec` per forzare l'aritmetica decimale nei casi in cui e con precisione singola e precisione doppia o calcoli di interi normalmente avrà luogo.</span><span class="sxs-lookup"><span data-stu-id="50103-160">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="50103-161">**Conversioni non riuscite.**</span><span class="sxs-lookup"><span data-stu-id="50103-161">**Failed Conversions.**</span></span> <span data-ttu-id="50103-162">Se il `expression` passato alla funzione è compreso nell'intervallo del tipo di dati a cui si desidera convertire, un <xref:System.OverflowException> si verifica.</span><span class="sxs-lookup"><span data-stu-id="50103-162">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="50103-163">**Parti frazionarie.**</span><span class="sxs-lookup"><span data-stu-id="50103-163">**Fractional Parts.**</span></span> <span data-ttu-id="50103-164">Quando si converte un valore non integrale in un tipo integrale tipo, le funzioni di conversione di integer (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, e `CUShort`) rimuovere il frazionari parte e arrotondare il valore all'intero più vicino.</span><span class="sxs-lookup"><span data-stu-id="50103-164">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="50103-165">Se la parte frazionaria è esattamente 0,5, arrotondano le funzioni di conversione di valori integer per l'intero pari più vicino.</span><span class="sxs-lookup"><span data-stu-id="50103-165">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="50103-166">Ad esempio 0,5 verrà arrotondato a 0 e 1,5 e 2,5 che entrambi arrotondato a 2.</span><span class="sxs-lookup"><span data-stu-id="50103-166">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="50103-167">Talvolta chiamato *arrotondamento*, e il suo scopo consiste nel compensare la distorsione che potrebbero accumularsi quando aggiungono molti tali numeri.</span><span class="sxs-lookup"><span data-stu-id="50103-167">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="50103-168">`CInt` e `CLng` diversi dai <xref:Microsoft.VisualBasic.Conversion.Int%2A> e <xref:Microsoft.VisualBasic.Conversion.Fix%2A> funzioni, che, anziché troncano l'arrotondamento, la parte frazionaria di un numero.</span><span class="sxs-lookup"><span data-stu-id="50103-168">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="50103-169">Inoltre, `Fix` e `Int` restituiscono sempre un valore dello stesso tipo di dati di quello passato.</span><span class="sxs-lookup"><span data-stu-id="50103-169">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="50103-170">**Conversioni di data/ora.**</span><span class="sxs-lookup"><span data-stu-id="50103-170">**Date/Time Conversions.**</span></span> <span data-ttu-id="50103-171">Utilizzare il <xref:Microsoft.VisualBasic.Information.IsDate%2A> funzione per determinare se un valore può essere convertito in una data e ora.</span><span class="sxs-lookup"><span data-stu-id="50103-171">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="50103-172">`CDate` riconosce i valori letterali data e ora, ma i valori non numerici.</span><span class="sxs-lookup"><span data-stu-id="50103-172">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="50103-173">Per convertire un Visual Basic 6.0 `Date` valore un `Date` valore in Visual Basic 2005 o versioni successive, è possibile utilizzare il <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="50103-173">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="50103-174">**Neutro valori data/ora.**</span><span class="sxs-lookup"><span data-stu-id="50103-174">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="50103-175">Il [tipo di dati Date](../../../visual-basic/language-reference/data-types/date-data-type.md) contiene sempre le informazioni sia data e ora.</span><span class="sxs-lookup"><span data-stu-id="50103-175">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="50103-176">Ai fini della conversione del tipo, Visual Basic considera 1/1/0001 (1 ° gennaio dell'anno 1) da un *valore neutro* per la data e 00:00:00 (mezzanotte) come valore neutro per l'ora.</span><span class="sxs-lookup"><span data-stu-id="50103-176">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="50103-177">Se si converte un `Date` , una stringa a valore `CStr` non include valori neutri nella stringa risultante.</span><span class="sxs-lookup"><span data-stu-id="50103-177">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="50103-178">Ad esempio, se si converte `#January 1, 0001 9:30:00#` in una stringa, il risultato è "9:30:00 AM"; le informazioni sulla data viene eliminate.</span><span class="sxs-lookup"><span data-stu-id="50103-178">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="50103-179">Tuttavia, le informazioni sulla data è ancora presente nell'originale `Date` valore e possono essere recuperate con funzioni, ad esempio <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> (funzione).</span><span class="sxs-lookup"><span data-stu-id="50103-179">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="50103-180">**Distinzione di impostazioni cultura.**</span><span class="sxs-lookup"><span data-stu-id="50103-180">**Culture Sensitivity.**</span></span> <span data-ttu-id="50103-181">Le funzioni di conversione di tipo che riguardano le stringhe eseguono conversioni in base alle impostazioni cultura correnti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="50103-181">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="50103-182">Ad esempio, `CDate` riconosce i formati di data in base all'impostazione delle impostazioni locali del sistema.</span><span class="sxs-lookup"><span data-stu-id="50103-182">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="50103-183">È necessario specificare il giorno, mese e anno nell'ordine corretto delle impostazioni locali o la data potrebbe non essere interpretata correttamente.</span><span class="sxs-lookup"><span data-stu-id="50103-183">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="50103-184">Se contiene una stringa di giorno della settimana, ad esempio "Mercoledì", un formato di data estesa non è riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="50103-184">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="50103-185">Se è necessario convertire verso o da una rappresentazione di stringa di un valore in un formato diverso da quello specificato dalle impostazioni locali, è possibile utilizzare le funzioni di conversione di tipo Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="50103-185">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="50103-186">A tale scopo, utilizzare il `ToString(IFormatProvider)` e `Parse(String, IFormatProvider)` metodi del tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="50103-186">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="50103-187">Ad esempio, utilizzare <xref:System.Double.Parse%2A?displayProperty=nameWithType> quando si converte una stringa in un `Double`e utilizzare <xref:System.Double.ToString%2A?displayProperty=nameWithType> durante la conversione di un valore di tipo `Double` in una stringa.</span><span class="sxs-lookup"><span data-stu-id="50103-187">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="50103-188">CType Function</span><span class="sxs-lookup"><span data-stu-id="50103-188">CType Function</span></span>  
 <span data-ttu-id="50103-189">Il [CType (funzione)](../../../visual-basic/language-reference/functions/ctype-function.md) accetta un secondo argomento `typename`e assegna `expression` a `typename`, dove `typename` può essere qualsiasi tipo di dati, struttura, classe o interfaccia a cui è presente una conversione valida.</span><span class="sxs-lookup"><span data-stu-id="50103-189">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="50103-190">Per un confronto tra `CType` con l'altra tipo parole chiave di conversione, vedere [operatore DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) e [operatore TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="50103-190">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="50103-191">Esempio di CBool</span><span class="sxs-lookup"><span data-stu-id="50103-191">CBool Example</span></span>  
 <span data-ttu-id="50103-192">L'esempio seguente usa il `CBool` funzione per convertire le espressioni di `Boolean` valori.</span><span class="sxs-lookup"><span data-stu-id="50103-192">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="50103-193">Se un'espressione restituisce un valore diverso da zero, `CBool` restituisce `True`; in caso contrario, restituisce `False`.</span><span class="sxs-lookup"><span data-stu-id="50103-193">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="50103-194">Esempio di CByte</span><span class="sxs-lookup"><span data-stu-id="50103-194">CByte Example</span></span>  
 <span data-ttu-id="50103-195">L'esempio seguente usa il `CByte` funzione per convertire un'espressione in un `Byte`.</span><span class="sxs-lookup"><span data-stu-id="50103-195">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a><span data-ttu-id="50103-196">Esempio di CChar</span><span class="sxs-lookup"><span data-stu-id="50103-196">CChar Example</span></span>  
 <span data-ttu-id="50103-197">L'esempio seguente usa il `CChar` funzione per convertire il primo carattere di un `String` espressione da un `Char` tipo.</span><span class="sxs-lookup"><span data-stu-id="50103-197">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 <span data-ttu-id="50103-198">Argomento di input per `CChar` deve essere di tipo di dati `Char` o `String`.</span><span class="sxs-lookup"><span data-stu-id="50103-198">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="50103-199">Non è possibile utilizzare `CChar` per convertire un numero in un carattere, perché `CChar` non può accettare un tipo di dati numerici.</span><span class="sxs-lookup"><span data-stu-id="50103-199">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="50103-200">Nell'esempio seguente viene ottenuto un numero che rappresenta un punto di codice (codice carattere) e converte il carattere corrispondente.</span><span class="sxs-lookup"><span data-stu-id="50103-200">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="50103-201">Usa il <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> funzione per ottenere la stringa di cifre, `CInt` per convertire la stringa al tipo `Integer`, e `ChrW` effettuare la conversione al tipo `Char`.</span><span class="sxs-lookup"><span data-stu-id="50103-201">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a><span data-ttu-id="50103-202">Esempio di CDate</span><span class="sxs-lookup"><span data-stu-id="50103-202">CDate Example</span></span>  
 <span data-ttu-id="50103-203">L'esempio seguente usa il `CDate` funzione per convertire le stringhe in `Date` valori.</span><span class="sxs-lookup"><span data-stu-id="50103-203">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="50103-204">In generale, non è consigliabile impostare come hardcoded date e ore come stringhe (come illustrato in questo esempio).</span><span class="sxs-lookup"><span data-stu-id="50103-204">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="50103-205">Utilizzare valori letterali di data e ora, ad esempio #Feb 12, 1969 # e # 4:45:23 PM # invece.</span><span class="sxs-lookup"><span data-stu-id="50103-205">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="50103-206">Esempio di CDbl</span><span class="sxs-lookup"><span data-stu-id="50103-206">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a><span data-ttu-id="50103-207">Esempio di CDec</span><span class="sxs-lookup"><span data-stu-id="50103-207">CDec Example</span></span>  
 <span data-ttu-id="50103-208">L'esempio seguente usa il `CDec` funzione per convertire un valore numerico per `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="50103-208">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a><span data-ttu-id="50103-209">Esempio di CInt</span><span class="sxs-lookup"><span data-stu-id="50103-209">CInt Example</span></span>  
 <span data-ttu-id="50103-210">L'esempio seguente usa il `CInt` funzione per convertire un valore `Integer`.</span><span class="sxs-lookup"><span data-stu-id="50103-210">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a><span data-ttu-id="50103-211">Esempio di CLng</span><span class="sxs-lookup"><span data-stu-id="50103-211">CLng Example</span></span>  
 <span data-ttu-id="50103-212">L'esempio seguente usa il `CLng` funzione per convertire i valori per `Long`.</span><span class="sxs-lookup"><span data-stu-id="50103-212">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a><span data-ttu-id="50103-213">Esempio di CObj</span><span class="sxs-lookup"><span data-stu-id="50103-213">CObj Example</span></span>  
 <span data-ttu-id="50103-214">L'esempio seguente usa il `CObj` funzione per convertire un valore numerico per `Object`.</span><span class="sxs-lookup"><span data-stu-id="50103-214">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="50103-215">Il `Object` variabile contiene solo un puntatore a quattro byte, che fa riferimento al `Double` valore assegnato a esso.</span><span class="sxs-lookup"><span data-stu-id="50103-215">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="50103-216">Esempio di CSByte</span><span class="sxs-lookup"><span data-stu-id="50103-216">CSByte Example</span></span>  
 <span data-ttu-id="50103-217">L'esempio seguente usa il `CSByte` funzione per convertire un valore numerico per `SByte`.</span><span class="sxs-lookup"><span data-stu-id="50103-217">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a><span data-ttu-id="50103-218">Esempio di CShort</span><span class="sxs-lookup"><span data-stu-id="50103-218">CShort Example</span></span>  
 <span data-ttu-id="50103-219">L'esempio seguente usa il `CShort` funzione per convertire un valore numerico per `Short`.</span><span class="sxs-lookup"><span data-stu-id="50103-219">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a><span data-ttu-id="50103-220">Esempio di CSng</span><span class="sxs-lookup"><span data-stu-id="50103-220">CSng Example</span></span>  
 <span data-ttu-id="50103-221">L'esempio seguente usa il `CSng` funzione per convertire i valori per `Single`.</span><span class="sxs-lookup"><span data-stu-id="50103-221">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a><span data-ttu-id="50103-222">Esempio di funzione CStr</span><span class="sxs-lookup"><span data-stu-id="50103-222">CStr Example</span></span>  
 <span data-ttu-id="50103-223">L'esempio seguente usa il `CStr` funzione per convertire un valore numerico per `String`.</span><span class="sxs-lookup"><span data-stu-id="50103-223">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 <span data-ttu-id="50103-224">L'esempio seguente usa il `CStr` funzione per convertire `Date` valori `String` valori.</span><span class="sxs-lookup"><span data-stu-id="50103-224">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 <span data-ttu-id="50103-225">`CStr` Visualizza sempre un `Date` valore nel formato breve standard per le impostazioni locali correnti, ad esempio, "6/15/2003 4:35:47 PM".</span><span class="sxs-lookup"><span data-stu-id="50103-225">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="50103-226">Tuttavia, `CStr` Sopprime il *valori neutri* di 1/1/0001 per la data e 00:00:00 per il periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="50103-226">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="50103-227">Per informazioni dettagliate sui valori restituiti da `CStr`, vedere [valori restituiti dalla funzione CStr](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span><span class="sxs-lookup"><span data-stu-id="50103-227">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="50103-228">Esempio di CUInt</span><span class="sxs-lookup"><span data-stu-id="50103-228">CUInt Example</span></span>  
 <span data-ttu-id="50103-229">L'esempio seguente usa il `CUInt` funzione per convertire un valore numerico per `UInteger`.</span><span class="sxs-lookup"><span data-stu-id="50103-229">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a><span data-ttu-id="50103-230">Esempio di CULng</span><span class="sxs-lookup"><span data-stu-id="50103-230">CULng Example</span></span>  
 <span data-ttu-id="50103-231">L'esempio seguente usa il `CULng` funzione per convertire un valore numerico per `ULong`.</span><span class="sxs-lookup"><span data-stu-id="50103-231">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a><span data-ttu-id="50103-232">Esempio di CUShort</span><span class="sxs-lookup"><span data-stu-id="50103-232">CUShort Example</span></span>  
 <span data-ttu-id="50103-233">L'esempio seguente usa il `CUShort` funzione per convertire un valore numerico per `UShort`.</span><span class="sxs-lookup"><span data-stu-id="50103-233">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="50103-234">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50103-234">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="50103-235">Funzioni di conversione</span><span class="sxs-lookup"><span data-stu-id="50103-235">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [<span data-ttu-id="50103-236">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="50103-236">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
