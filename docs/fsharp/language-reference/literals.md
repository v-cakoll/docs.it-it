---
title: Valori letterali (F#)
description: 'Informazioni sui tipi di valore letterale in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4b1d6e9d-f933-4cd4-966d-d643152c27e4
ms.openlocfilehash: 6bb1f233b6846e226c4e73aee00b8cf77735fe2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="literals"></a><span data-ttu-id="f55cc-104">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="f55cc-104">Literals</span></span>

> [!NOTE]
<span data-ttu-id="f55cc-105">I collegamenti di riferimento API in questo articolo si passerà a MSDN (per ora).</span><span class="sxs-lookup"><span data-stu-id="f55cc-105">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="f55cc-106">In questo argomento fornisce una tabella in cui viene illustrato come specificare il tipo di un valore letterale in F #.</span><span class="sxs-lookup"><span data-stu-id="f55cc-106">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="f55cc-107">Tipi di valori letterali</span><span class="sxs-lookup"><span data-stu-id="f55cc-107">Literal Types</span></span>
<span data-ttu-id="f55cc-108">La tabella seguente illustra i tipi di valore letterale in F #.</span><span class="sxs-lookup"><span data-stu-id="f55cc-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="f55cc-109">Caratteri che rappresentano cifre in notazione esadecimale non fanno distinzione; caratteri che identificano il tipo di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f55cc-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="f55cc-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="f55cc-110">Type</span></span>|<span data-ttu-id="f55cc-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f55cc-111">Description</span></span>|<span data-ttu-id="f55cc-112">Prefisso o suffisso</span><span class="sxs-lookup"><span data-stu-id="f55cc-112">Suffix or prefix</span></span>|<span data-ttu-id="f55cc-113">Esempi</span><span class="sxs-lookup"><span data-stu-id="f55cc-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="f55cc-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="f55cc-114">sbyte</span></span>|<span data-ttu-id="f55cc-115">Intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-115">signed 8-bit integer</span></span>|<span data-ttu-id="f55cc-116">y</span><span class="sxs-lookup"><span data-stu-id="f55cc-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="f55cc-117">byte</span><span class="sxs-lookup"><span data-stu-id="f55cc-117">byte</span></span>|<span data-ttu-id="f55cc-118">Numero naturale senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="f55cc-119">UY</span><span class="sxs-lookup"><span data-stu-id="f55cc-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="f55cc-120">int16</span><span class="sxs-lookup"><span data-stu-id="f55cc-120">int16</span></span>|<span data-ttu-id="f55cc-121">Intero con segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-121">signed 16-bit integer</span></span>|<span data-ttu-id="f55cc-122">s</span><span class="sxs-lookup"><span data-stu-id="f55cc-122">s</span></span>|`86s`|
|<span data-ttu-id="f55cc-123">uint16</span><span class="sxs-lookup"><span data-stu-id="f55cc-123">uint16</span></span>|<span data-ttu-id="f55cc-124">numero di naturale senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="f55cc-125">us</span><span class="sxs-lookup"><span data-stu-id="f55cc-125">us</span></span>|`86us`|
|<span data-ttu-id="f55cc-126">int</span><span class="sxs-lookup"><span data-stu-id="f55cc-126">int</span></span><br /><br /><span data-ttu-id="f55cc-127">int32</span><span class="sxs-lookup"><span data-stu-id="f55cc-127">int32</span></span>|<span data-ttu-id="f55cc-128">Intero con segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-128">signed 32-bit integer</span></span>|<span data-ttu-id="f55cc-129">l o nessuno</span><span class="sxs-lookup"><span data-stu-id="f55cc-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="f55cc-130">uint</span><span class="sxs-lookup"><span data-stu-id="f55cc-130">uint</span></span><br /><br /><span data-ttu-id="f55cc-131">uint32</span><span class="sxs-lookup"><span data-stu-id="f55cc-131">uint32</span></span>|<span data-ttu-id="f55cc-132">Numero naturale senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="f55cc-133">u o ul</span><span class="sxs-lookup"><span data-stu-id="f55cc-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="f55cc-134">unativeint</span><span class="sxs-lookup"><span data-stu-id="f55cc-134">unativeint</span></span>|<span data-ttu-id="f55cc-135">puntatore nativo come un numero naturale senza segno</span><span class="sxs-lookup"><span data-stu-id="f55cc-135">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="f55cc-136">Annulla</span><span class="sxs-lookup"><span data-stu-id="f55cc-136">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="f55cc-137">int64</span><span class="sxs-lookup"><span data-stu-id="f55cc-137">int64</span></span>|<span data-ttu-id="f55cc-138">Intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-138">signed 64-bit integer</span></span>|<span data-ttu-id="f55cc-139">L</span><span class="sxs-lookup"><span data-stu-id="f55cc-139">L</span></span>|`86L`|
|<span data-ttu-id="f55cc-140">uint64</span><span class="sxs-lookup"><span data-stu-id="f55cc-140">uint64</span></span>|<span data-ttu-id="f55cc-141">numero di naturale senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-141">unsigned 64-bit natural number</span></span>|<span data-ttu-id="f55cc-142">UL</span><span class="sxs-lookup"><span data-stu-id="f55cc-142">UL</span></span>|`86UL`|
|<span data-ttu-id="f55cc-143">float32 singolo,</span><span class="sxs-lookup"><span data-stu-id="f55cc-143">single, float32</span></span>|<span data-ttu-id="f55cc-144">numero a virgola mobile a 32 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-144">32-bit floating point number</span></span>|<span data-ttu-id="f55cc-145">F o f</span><span class="sxs-lookup"><span data-stu-id="f55cc-145">F or f</span></span>|<span data-ttu-id="f55cc-146">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="f55cc-146">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="f55cc-147">LF</span><span class="sxs-lookup"><span data-stu-id="f55cc-147">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="f55cc-148">float; Double</span><span class="sxs-lookup"><span data-stu-id="f55cc-148">float; double</span></span>|<span data-ttu-id="f55cc-149">numero a virgola mobile a 64 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-149">64-bit floating point number</span></span>|<span data-ttu-id="f55cc-150">nessuno</span><span class="sxs-lookup"><span data-stu-id="f55cc-150">none</span></span>|<span data-ttu-id="f55cc-151">`4.14`o `2.3E+32` o`2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="f55cc-151">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="f55cc-152">LF</span><span class="sxs-lookup"><span data-stu-id="f55cc-152">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="f55cc-153">bigint</span><span class="sxs-lookup"><span data-stu-id="f55cc-153">bigint</span></span>|<span data-ttu-id="f55cc-154">numero intero non è limitato a una rappresentazione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="f55cc-154">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="f55cc-155">I</span><span class="sxs-lookup"><span data-stu-id="f55cc-155">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="f55cc-156">decimal</span><span class="sxs-lookup"><span data-stu-id="f55cc-156">decimal</span></span>|<span data-ttu-id="f55cc-157">numero frazionario rappresentato come un punto fisso o un numero razionale</span><span class="sxs-lookup"><span data-stu-id="f55cc-157">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="f55cc-158">M o m</span><span class="sxs-lookup"><span data-stu-id="f55cc-158">M or m</span></span>|<span data-ttu-id="f55cc-159">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="f55cc-159">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="f55cc-160">Char</span><span class="sxs-lookup"><span data-stu-id="f55cc-160">Char</span></span>|<span data-ttu-id="f55cc-161">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="f55cc-161">Unicode character</span></span>|<span data-ttu-id="f55cc-162">nessuno</span><span class="sxs-lookup"><span data-stu-id="f55cc-162">none</span></span>|`'a'`|
|<span data-ttu-id="f55cc-163">Stringa</span><span class="sxs-lookup"><span data-stu-id="f55cc-163">String</span></span>|<span data-ttu-id="f55cc-164">Stringa Unicode</span><span class="sxs-lookup"><span data-stu-id="f55cc-164">Unicode string</span></span>|<span data-ttu-id="f55cc-165">nessuno</span><span class="sxs-lookup"><span data-stu-id="f55cc-165">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="f55cc-166">oppure</span><span class="sxs-lookup"><span data-stu-id="f55cc-166">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="f55cc-167">oppure</span><span class="sxs-lookup"><span data-stu-id="f55cc-167">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="f55cc-168">oppure</span><span class="sxs-lookup"><span data-stu-id="f55cc-168">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="f55cc-169">Vedere anche [stringhe](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="f55cc-169">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="f55cc-170">byte</span><span class="sxs-lookup"><span data-stu-id="f55cc-170">byte</span></span>|<span data-ttu-id="f55cc-171">Carattere ASCII</span><span class="sxs-lookup"><span data-stu-id="f55cc-171">ASCII character</span></span>|<span data-ttu-id="f55cc-172">B</span><span class="sxs-lookup"><span data-stu-id="f55cc-172">B</span></span>|`'a'B`|
|<span data-ttu-id="f55cc-173">byte[]</span><span class="sxs-lookup"><span data-stu-id="f55cc-173">byte[]</span></span>|<span data-ttu-id="f55cc-174">Stringa ASCII</span><span class="sxs-lookup"><span data-stu-id="f55cc-174">ASCII string</span></span>|<span data-ttu-id="f55cc-175">B</span><span class="sxs-lookup"><span data-stu-id="f55cc-175">B</span></span>|`"text"B`|
|<span data-ttu-id="f55cc-176">String o byte]</span><span class="sxs-lookup"><span data-stu-id="f55cc-176">String or byte[]</span></span>|<span data-ttu-id="f55cc-177">stringa verbatim</span><span class="sxs-lookup"><span data-stu-id="f55cc-177">verbatim string</span></span>|<span data-ttu-id="f55cc-178">prefisso @</span><span class="sxs-lookup"><span data-stu-id="f55cc-178">@ prefix</span></span>|<span data-ttu-id="f55cc-179">`@"\\server\share"`(Unicode)</span><span class="sxs-lookup"><span data-stu-id="f55cc-179">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="f55cc-180">`@"\\server\share"B`(ASCII)</span><span class="sxs-lookup"><span data-stu-id="f55cc-180">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="f55cc-181">Note</span><span class="sxs-lookup"><span data-stu-id="f55cc-181">Remarks</span></span>
<span data-ttu-id="f55cc-182">Le stringhe Unicode possono contenere codifiche esplicite che è possibile specificare utilizzando `\u` seguito da un codice esadecimale a 16 bit o codifiche UTF-32 che è possibile specificare utilizzando `\U` seguito da un codice esadecimale a 32 bit che rappresenta un Unicode coppia di surrogati.</span><span class="sxs-lookup"><span data-stu-id="f55cc-182">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="f55cc-183">A partire da F # 3.1, è possibile utilizzare il `+` accedere per combinare i valori letterali stringa.</span><span class="sxs-lookup"><span data-stu-id="f55cc-183">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="f55cc-184">È inoltre possibile utilizzare il bit per bit o (`|||`) (operatore) per combinare i flag di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f55cc-184">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="f55cc-185">Ad esempio, il codice seguente è valido in F # 3.1:</span><span class="sxs-lookup"><span data-stu-id="f55cc-185">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="f55cc-186">Non è consentito l'uso di altri operatori bit per bit.</span><span class="sxs-lookup"><span data-stu-id="f55cc-186">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="f55cc-187">Valori letterali denominati</span><span class="sxs-lookup"><span data-stu-id="f55cc-187">Named Literals</span></span>
<span data-ttu-id="f55cc-188">I valori che devono essere costanti possono essere contrassegnati con il [letterale](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attributo.</span><span class="sxs-lookup"><span data-stu-id="f55cc-188">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="f55cc-189">Questo attributo ha l'effetto della causa di un valore essere compilata come una costante.</span><span class="sxs-lookup"><span data-stu-id="f55cc-189">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="f55cc-190">Nelle espressioni dei criteri, gli identificatori che iniziano con caratteri minuscoli vengono sempre considerati come variabili di essere vincolato, anziché come valori letterali, pertanto è in genere consigliabile utilizzare le lettere maiuscole iniziali quando si definiscono i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="f55cc-190">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="f55cc-191">Numeri interi In altra base</span><span class="sxs-lookup"><span data-stu-id="f55cc-191">Integers In Other Bases</span></span>

<span data-ttu-id="f55cc-192">È inoltre possibile specificare interi con segno a 32 bit binaria, ottale o esadecimale con un `0x`, `0o` o `0b` prefisso rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="f55cc-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="f55cc-193">Caratteri di sottolineatura nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="f55cc-193">Underscores in Numeric Literals</span></span>

<span data-ttu-id="f55cc-194">A partire da F # 4.1, è possibile separare cifre con il carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="f55cc-194">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="f55cc-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f55cc-195">See Also</span></span>

[<span data-ttu-id="f55cc-196">Classe Core. LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="f55cc-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
