---
title: Valori letterali
description: Informazioni sui tipi di valore letterali in di F# linguaggio di programmazione.
ms.date: 06/28/2019
ms.openlocfilehash: 53647d8cbc2a59527a50e122bc1abc6055c1fce5
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487778"
---
# <a name="literals"></a><span data-ttu-id="08d1f-103">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="08d1f-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="08d1f-104">I collegamenti di riferimento API in questo articolo si passerà a MSDN (per ora).</span><span class="sxs-lookup"><span data-stu-id="08d1f-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="08d1f-105">In questo argomento fornisce una tabella che mostra come specificare il tipo di un valore letterale in F#.</span><span class="sxs-lookup"><span data-stu-id="08d1f-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="08d1f-106">Tipi letterali</span><span class="sxs-lookup"><span data-stu-id="08d1f-106">Literal Types</span></span>

<span data-ttu-id="08d1f-107">La tabella seguente illustra i tipi di valore letterali in F#.</span><span class="sxs-lookup"><span data-stu-id="08d1f-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="08d1f-108">I caratteri che rappresentano cifre in notazione esadecimale non sono tra maiuscole e minuscole; caratteri che identificano il tipo di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="08d1f-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="08d1f-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="08d1f-109">Type</span></span>|<span data-ttu-id="08d1f-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08d1f-110">Description</span></span>|<span data-ttu-id="08d1f-111">Prefissi o suffissi</span><span class="sxs-lookup"><span data-stu-id="08d1f-111">Suffix or prefix</span></span>|<span data-ttu-id="08d1f-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="08d1f-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="08d1f-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="08d1f-113">sbyte</span></span>|<span data-ttu-id="08d1f-114">intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-114">signed 8-bit integer</span></span>|<span data-ttu-id="08d1f-115">y</span><span class="sxs-lookup"><span data-stu-id="08d1f-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="08d1f-116">byte</span><span class="sxs-lookup"><span data-stu-id="08d1f-116">byte</span></span>|<span data-ttu-id="08d1f-117">Numero naturale senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="08d1f-118">UY</span><span class="sxs-lookup"><span data-stu-id="08d1f-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="08d1f-119">int16</span><span class="sxs-lookup"><span data-stu-id="08d1f-119">int16</span></span>|<span data-ttu-id="08d1f-120">intero con segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-120">signed 16-bit integer</span></span>|<span data-ttu-id="08d1f-121">s</span><span class="sxs-lookup"><span data-stu-id="08d1f-121">s</span></span>|`86s`|
|<span data-ttu-id="08d1f-122">uint16</span><span class="sxs-lookup"><span data-stu-id="08d1f-122">uint16</span></span>|<span data-ttu-id="08d1f-123">Numero naturale senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="08d1f-124">us</span><span class="sxs-lookup"><span data-stu-id="08d1f-124">us</span></span>|`86us`|
|<span data-ttu-id="08d1f-125">int</span><span class="sxs-lookup"><span data-stu-id="08d1f-125">int</span></span><br /><br /><span data-ttu-id="08d1f-126">int32</span><span class="sxs-lookup"><span data-stu-id="08d1f-126">int32</span></span>|<span data-ttu-id="08d1f-127">intero con segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-127">signed 32-bit integer</span></span>|<span data-ttu-id="08d1f-128">l o nessuno</span><span class="sxs-lookup"><span data-stu-id="08d1f-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="08d1f-129">uint</span><span class="sxs-lookup"><span data-stu-id="08d1f-129">uint</span></span><br /><br /><span data-ttu-id="08d1f-130">uint32</span><span class="sxs-lookup"><span data-stu-id="08d1f-130">uint32</span></span>|<span data-ttu-id="08d1f-131">Numero naturale senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="08d1f-132">u o ul</span><span class="sxs-lookup"><span data-stu-id="08d1f-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="08d1f-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="08d1f-133">nativeint</span></span>|<span data-ttu-id="08d1f-134">puntatore nativo in un numero naturale con segno</span><span class="sxs-lookup"><span data-stu-id="08d1f-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="08d1f-135">n</span><span class="sxs-lookup"><span data-stu-id="08d1f-135">n</span></span>|`123n`|
|<span data-ttu-id="08d1f-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="08d1f-136">unativeint</span></span>|<span data-ttu-id="08d1f-137">puntatore nativo come numero naturale senza segno</span><span class="sxs-lookup"><span data-stu-id="08d1f-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="08d1f-138">Annulla la</span><span class="sxs-lookup"><span data-stu-id="08d1f-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="08d1f-139">int64</span><span class="sxs-lookup"><span data-stu-id="08d1f-139">int64</span></span>|<span data-ttu-id="08d1f-140">intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-140">signed 64-bit integer</span></span>|<span data-ttu-id="08d1f-141">L</span><span class="sxs-lookup"><span data-stu-id="08d1f-141">L</span></span>|`86L`|
|<span data-ttu-id="08d1f-142">uint64</span><span class="sxs-lookup"><span data-stu-id="08d1f-142">uint64</span></span>|<span data-ttu-id="08d1f-143">Numero naturale senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="08d1f-144">UL</span><span class="sxs-lookup"><span data-stu-id="08d1f-144">UL</span></span>|`86UL`|
|<span data-ttu-id="08d1f-145">float32 singolo,</span><span class="sxs-lookup"><span data-stu-id="08d1f-145">single, float32</span></span>|<span data-ttu-id="08d1f-146">numero a virgola mobile a 32 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-146">32-bit floating point number</span></span>|<span data-ttu-id="08d1f-147">F o f</span><span class="sxs-lookup"><span data-stu-id="08d1f-147">F or f</span></span>|<span data-ttu-id="08d1f-148">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="08d1f-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="08d1f-149">lf</span><span class="sxs-lookup"><span data-stu-id="08d1f-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="08d1f-150">float; Double</span><span class="sxs-lookup"><span data-stu-id="08d1f-150">float; double</span></span>|<span data-ttu-id="08d1f-151">numero a virgola mobile a 64 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-151">64-bit floating point number</span></span>|<span data-ttu-id="08d1f-152">none</span><span class="sxs-lookup"><span data-stu-id="08d1f-152">none</span></span>|<span data-ttu-id="08d1f-153">`4.14` o `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="08d1f-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="08d1f-154">LF</span><span class="sxs-lookup"><span data-stu-id="08d1f-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="08d1f-155">bigint</span><span class="sxs-lookup"><span data-stu-id="08d1f-155">bigint</span></span>|<span data-ttu-id="08d1f-156">Integer non limitato alla rappresentazione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="08d1f-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="08d1f-157">I</span><span class="sxs-lookup"><span data-stu-id="08d1f-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="08d1f-158">decimal</span><span class="sxs-lookup"><span data-stu-id="08d1f-158">decimal</span></span>|<span data-ttu-id="08d1f-159">numero frazionario rappresentato come un punto fisso o un numero razionale</span><span class="sxs-lookup"><span data-stu-id="08d1f-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="08d1f-160">M o m</span><span class="sxs-lookup"><span data-stu-id="08d1f-160">M or m</span></span>|<span data-ttu-id="08d1f-161">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="08d1f-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="08d1f-162">Char</span><span class="sxs-lookup"><span data-stu-id="08d1f-162">Char</span></span>|<span data-ttu-id="08d1f-163">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="08d1f-163">Unicode character</span></span>|<span data-ttu-id="08d1f-164">none</span><span class="sxs-lookup"><span data-stu-id="08d1f-164">none</span></span>|`'a'`|
|<span data-ttu-id="08d1f-165">Stringa</span><span class="sxs-lookup"><span data-stu-id="08d1f-165">String</span></span>|<span data-ttu-id="08d1f-166">Stringa Unicode</span><span class="sxs-lookup"><span data-stu-id="08d1f-166">Unicode string</span></span>|<span data-ttu-id="08d1f-167">none</span><span class="sxs-lookup"><span data-stu-id="08d1f-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="08d1f-168">oppure</span><span class="sxs-lookup"><span data-stu-id="08d1f-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="08d1f-169">oppure</span><span class="sxs-lookup"><span data-stu-id="08d1f-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="08d1f-170">oppure</span><span class="sxs-lookup"><span data-stu-id="08d1f-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="08d1f-171">Vedere anche [stringhe](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="08d1f-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="08d1f-172">byte</span><span class="sxs-lookup"><span data-stu-id="08d1f-172">byte</span></span>|<span data-ttu-id="08d1f-173">Carattere ASCII</span><span class="sxs-lookup"><span data-stu-id="08d1f-173">ASCII character</span></span>|<span data-ttu-id="08d1f-174">B</span><span class="sxs-lookup"><span data-stu-id="08d1f-174">B</span></span>|`'a'B`|
|<span data-ttu-id="08d1f-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="08d1f-175">byte[]</span></span>|<span data-ttu-id="08d1f-176">Stringa ASCII</span><span class="sxs-lookup"><span data-stu-id="08d1f-176">ASCII string</span></span>|<span data-ttu-id="08d1f-177">B</span><span class="sxs-lookup"><span data-stu-id="08d1f-177">B</span></span>|`"text"B`|
|<span data-ttu-id="08d1f-178">String o byte]</span><span class="sxs-lookup"><span data-stu-id="08d1f-178">String or byte[]</span></span>|<span data-ttu-id="08d1f-179">stringa verbatim</span><span class="sxs-lookup"><span data-stu-id="08d1f-179">verbatim string</span></span>|<span data-ttu-id="08d1f-180">prefisso @</span><span class="sxs-lookup"><span data-stu-id="08d1f-180">@ prefix</span></span>|<span data-ttu-id="08d1f-181">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="08d1f-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="08d1f-182">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="08d1f-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="08d1f-183">Valori letterali denominati</span><span class="sxs-lookup"><span data-stu-id="08d1f-183">Named literals</span></span>

<span data-ttu-id="08d1f-184">I valori che devono essere costanti possono essere contrassegnati con il [letterale](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attributo.</span><span class="sxs-lookup"><span data-stu-id="08d1f-184">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="08d1f-185">Questo attributo ha l'effetto di provocare un valore essere compilato come una costante.</span><span class="sxs-lookup"><span data-stu-id="08d1f-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="08d1f-186">Nelle espressioni dei criteri, gli identificatori che iniziano con caratteri minuscoli vengono sempre trattati come variabili da associare, anziché come valori letterali, pertanto è consigliabile in genere usare lettere maiuscole iniziali quando si definiscono i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="08d1f-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="08d1f-187">Note</span><span class="sxs-lookup"><span data-stu-id="08d1f-187">Remarks</span></span>

<span data-ttu-id="08d1f-188">Le stringhe Unicode possono contenere codifiche esplicite che è possibile specificare utilizzando `\u` seguita da un codice esadecimale a 16 bit (0000 - FFFF) o le codifiche UTF-32 che è possibile specificare utilizzando `\U` seguita da un codice esadecimale a 32 bit che rappresenta qualsiasi punto di codice Unicode (00000000 - 00010FFFF).</span><span class="sxs-lookup"><span data-stu-id="08d1f-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 00010FFFF).</span></span>

<span data-ttu-id="08d1f-189">L'uso di altri operatori bit per bit diverso da `|||` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="08d1f-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="08d1f-190">Numeri interi in altre basi</span><span class="sxs-lookup"><span data-stu-id="08d1f-190">Integers in other bases</span></span>

<span data-ttu-id="08d1f-191">È possibile anche specificare interi con segno a 32 bit binaria, ottale o esadecimale con un `0x`, `0o` o `0b` rispettivamente del prefisso.</span><span class="sxs-lookup"><span data-stu-id="08d1f-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="08d1f-192">Caratteri di sottolineatura nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="08d1f-192">Underscores in numeric literals</span></span>

<span data-ttu-id="08d1f-193">È possibile separare cifre con il carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="08d1f-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="08d1f-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08d1f-194">See also</span></span>

- [<span data-ttu-id="08d1f-195">Classe Core. LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="08d1f-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
