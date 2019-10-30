---
title: Valori letterali
description: Informazioni sui tipi letterali nel linguaggio F# di programmazione.
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041037"
---
# <a name="literals"></a><span data-ttu-id="2f5aa-103">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="2f5aa-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="2f5aa-104">I collegamenti di riferimento all'API in questo articolo ti porteranno a MSDN (per il momento).</span><span class="sxs-lookup"><span data-stu-id="2f5aa-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="2f5aa-105">In questo argomento viene fornita una tabella in cui viene illustrato come specificare il tipo di F#un valore letterale in.</span><span class="sxs-lookup"><span data-stu-id="2f5aa-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="2f5aa-106">Tipi di valori letterali</span><span class="sxs-lookup"><span data-stu-id="2f5aa-106">Literal Types</span></span>

<span data-ttu-id="2f5aa-107">Nella tabella seguente vengono illustrati i tipi F#di valore letterale in.</span><span class="sxs-lookup"><span data-stu-id="2f5aa-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="2f5aa-108">I caratteri che rappresentano le cifre nella notazione esadecimale non fanno distinzione tra maiuscole e minuscole. i caratteri che identificano il tipo fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="2f5aa-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="2f5aa-109">Digitare</span><span class="sxs-lookup"><span data-stu-id="2f5aa-109">Type</span></span>|<span data-ttu-id="2f5aa-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2f5aa-110">Description</span></span>|<span data-ttu-id="2f5aa-111">Suffisso o prefisso</span><span class="sxs-lookup"><span data-stu-id="2f5aa-111">Suffix or prefix</span></span>|<span data-ttu-id="2f5aa-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="2f5aa-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="2f5aa-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="2f5aa-113">sbyte</span></span>|<span data-ttu-id="2f5aa-114">Signed Integer a 8 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-114">signed 8-bit integer</span></span>|<span data-ttu-id="2f5aa-115">s</span><span class="sxs-lookup"><span data-stu-id="2f5aa-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="2f5aa-116">byte</span><span class="sxs-lookup"><span data-stu-id="2f5aa-116">byte</span></span>|<span data-ttu-id="2f5aa-117">numero naturale senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="2f5aa-118">uy</span><span class="sxs-lookup"><span data-stu-id="2f5aa-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="2f5aa-119">int16</span><span class="sxs-lookup"><span data-stu-id="2f5aa-119">int16</span></span>|<span data-ttu-id="2f5aa-120">Signed Integer a 16 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-120">signed 16-bit integer</span></span>|<span data-ttu-id="2f5aa-121">s</span><span class="sxs-lookup"><span data-stu-id="2f5aa-121">s</span></span>|`86s`|
|<span data-ttu-id="2f5aa-122">uint16</span><span class="sxs-lookup"><span data-stu-id="2f5aa-122">uint16</span></span>|<span data-ttu-id="2f5aa-123">numero naturale senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="2f5aa-124">us</span><span class="sxs-lookup"><span data-stu-id="2f5aa-124">us</span></span>|`86us`|
|<span data-ttu-id="2f5aa-125">int</span><span class="sxs-lookup"><span data-stu-id="2f5aa-125">int</span></span><br /><br /><span data-ttu-id="2f5aa-126">int32</span><span class="sxs-lookup"><span data-stu-id="2f5aa-126">int32</span></span>|<span data-ttu-id="2f5aa-127">Signed Integer a 32 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-127">signed 32-bit integer</span></span>|<span data-ttu-id="2f5aa-128">l o None</span><span class="sxs-lookup"><span data-stu-id="2f5aa-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="2f5aa-129">uint</span><span class="sxs-lookup"><span data-stu-id="2f5aa-129">uint</span></span><br /><br /><span data-ttu-id="2f5aa-130">uint32</span><span class="sxs-lookup"><span data-stu-id="2f5aa-130">uint32</span></span>|<span data-ttu-id="2f5aa-131">numero naturale senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="2f5aa-132">u o UL</span><span class="sxs-lookup"><span data-stu-id="2f5aa-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="2f5aa-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="2f5aa-133">nativeint</span></span>|<span data-ttu-id="2f5aa-134">puntatore nativo a un numero naturale con segno</span><span class="sxs-lookup"><span data-stu-id="2f5aa-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="2f5aa-135">n</span><span class="sxs-lookup"><span data-stu-id="2f5aa-135">n</span></span>|`123n`|
|<span data-ttu-id="2f5aa-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="2f5aa-136">unativeint</span></span>|<span data-ttu-id="2f5aa-137">puntatore nativo come numero naturale senza segno</span><span class="sxs-lookup"><span data-stu-id="2f5aa-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="2f5aa-138">non</span><span class="sxs-lookup"><span data-stu-id="2f5aa-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="2f5aa-139">int64</span><span class="sxs-lookup"><span data-stu-id="2f5aa-139">int64</span></span>|<span data-ttu-id="2f5aa-140">Signed Integer a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-140">signed 64-bit integer</span></span>|<span data-ttu-id="2f5aa-141">L</span><span class="sxs-lookup"><span data-stu-id="2f5aa-141">L</span></span>|`86L`|
|<span data-ttu-id="2f5aa-142">uint64</span><span class="sxs-lookup"><span data-stu-id="2f5aa-142">uint64</span></span>|<span data-ttu-id="2f5aa-143">numero naturale senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="2f5aa-144">UL</span><span class="sxs-lookup"><span data-stu-id="2f5aa-144">UL</span></span>|`86UL`|
|<span data-ttu-id="2f5aa-145">singolo, float32</span><span class="sxs-lookup"><span data-stu-id="2f5aa-145">single, float32</span></span>|<span data-ttu-id="2f5aa-146">numero a virgola mobile a 32 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-146">32-bit floating point number</span></span>|<span data-ttu-id="2f5aa-147">F o f</span><span class="sxs-lookup"><span data-stu-id="2f5aa-147">F or f</span></span>|<span data-ttu-id="2f5aa-148">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="2f5aa-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="2f5aa-149">Se</span><span class="sxs-lookup"><span data-stu-id="2f5aa-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="2f5aa-150">float doppio</span><span class="sxs-lookup"><span data-stu-id="2f5aa-150">float; double</span></span>|<span data-ttu-id="2f5aa-151">numero a virgola mobile a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-151">64-bit floating point number</span></span>|<span data-ttu-id="2f5aa-152">none</span><span class="sxs-lookup"><span data-stu-id="2f5aa-152">none</span></span>|<span data-ttu-id="2f5aa-153">`4.14` o `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="2f5aa-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="2f5aa-154">Se</span><span class="sxs-lookup"><span data-stu-id="2f5aa-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="2f5aa-155">bigint</span><span class="sxs-lookup"><span data-stu-id="2f5aa-155">bigint</span></span>|<span data-ttu-id="2f5aa-156">Integer non limitato alla rappresentazione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2f5aa-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="2f5aa-157">I</span><span class="sxs-lookup"><span data-stu-id="2f5aa-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="2f5aa-158">decimal</span><span class="sxs-lookup"><span data-stu-id="2f5aa-158">decimal</span></span>|<span data-ttu-id="2f5aa-159">numero frazionario rappresentato come punto fisso o numero razionale</span><span class="sxs-lookup"><span data-stu-id="2f5aa-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="2f5aa-160">M o m</span><span class="sxs-lookup"><span data-stu-id="2f5aa-160">M or m</span></span>|<span data-ttu-id="2f5aa-161">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="2f5aa-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="2f5aa-162">Char</span><span class="sxs-lookup"><span data-stu-id="2f5aa-162">Char</span></span>|<span data-ttu-id="2f5aa-163">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="2f5aa-163">Unicode character</span></span>|<span data-ttu-id="2f5aa-164">none</span><span class="sxs-lookup"><span data-stu-id="2f5aa-164">none</span></span>|<span data-ttu-id="2f5aa-165">`'a'` o `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="2f5aa-165">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="2f5aa-166">Stringa</span><span class="sxs-lookup"><span data-stu-id="2f5aa-166">String</span></span>|<span data-ttu-id="2f5aa-167">Stringa Unicode</span><span class="sxs-lookup"><span data-stu-id="2f5aa-167">Unicode string</span></span>|<span data-ttu-id="2f5aa-168">none</span><span class="sxs-lookup"><span data-stu-id="2f5aa-168">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="2f5aa-169">Oppure</span><span class="sxs-lookup"><span data-stu-id="2f5aa-169">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="2f5aa-170">Oppure</span><span class="sxs-lookup"><span data-stu-id="2f5aa-170">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="2f5aa-171">Oppure</span><span class="sxs-lookup"><span data-stu-id="2f5aa-171">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="2f5aa-172">Vedere anche [stringhe](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="2f5aa-172">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="2f5aa-173">byte</span><span class="sxs-lookup"><span data-stu-id="2f5aa-173">byte</span></span>|<span data-ttu-id="2f5aa-174">Carattere ASCII</span><span class="sxs-lookup"><span data-stu-id="2f5aa-174">ASCII character</span></span>|<span data-ttu-id="2f5aa-175">B</span><span class="sxs-lookup"><span data-stu-id="2f5aa-175">B</span></span>|`'a'B`|
|<span data-ttu-id="2f5aa-176">byte[]</span><span class="sxs-lookup"><span data-stu-id="2f5aa-176">byte[]</span></span>|<span data-ttu-id="2f5aa-177">Stringa ASCII</span><span class="sxs-lookup"><span data-stu-id="2f5aa-177">ASCII string</span></span>|<span data-ttu-id="2f5aa-178">B</span><span class="sxs-lookup"><span data-stu-id="2f5aa-178">B</span></span>|`"text"B`|
|<span data-ttu-id="2f5aa-179">String o byte []</span><span class="sxs-lookup"><span data-stu-id="2f5aa-179">String or byte[]</span></span>|<span data-ttu-id="2f5aa-180">stringa Verbatim</span><span class="sxs-lookup"><span data-stu-id="2f5aa-180">verbatim string</span></span>|<span data-ttu-id="2f5aa-181">@ prefix</span><span class="sxs-lookup"><span data-stu-id="2f5aa-181">@ prefix</span></span>|<span data-ttu-id="2f5aa-182">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="2f5aa-182">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="2f5aa-183">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="2f5aa-183">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="2f5aa-184">Valori letterali denominati</span><span class="sxs-lookup"><span data-stu-id="2f5aa-184">Named literals</span></span>

<span data-ttu-id="2f5aa-185">I valori destinati a essere costanti possono essere contrassegnati con l'attributo [letterale](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) .</span><span class="sxs-lookup"><span data-stu-id="2f5aa-185">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="2f5aa-186">Questo attributo ha l'effetto di causare la compilazione di un valore come costante.</span><span class="sxs-lookup"><span data-stu-id="2f5aa-186">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="2f5aa-187">Nelle espressioni di criteri di ricerca, gli identificatori che iniziano con caratteri minuscoli vengono sempre considerati come variabili da associare, anziché come valori letterali, pertanto è consigliabile utilizzare in genere maiuscole iniziali quando si definiscono i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="2f5aa-187">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="2f5aa-188">Note</span><span class="sxs-lookup"><span data-stu-id="2f5aa-188">Remarks</span></span>

<span data-ttu-id="2f5aa-189">Le stringhe Unicode possono contenere codifiche esplicite che è possibile specificare usando `\u` seguito da un codice esadecimale a 16 bit (0000-FFFF) o da codifiche UTF-32 che è possibile specificare usando `\U` seguito da un codice esadecimale a 32 bit che rappresenta qualsiasi Unicode punto di codice (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="2f5aa-189">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="2f5aa-190">L'utilizzo di altri operatori bit per bit diversi da `|||` non è consentito.</span><span class="sxs-lookup"><span data-stu-id="2f5aa-190">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="2f5aa-191">Numeri interi in altre basi</span><span class="sxs-lookup"><span data-stu-id="2f5aa-191">Integers in other bases</span></span>

<span data-ttu-id="2f5aa-192">Gli interi con segno a 32 bit possono essere specificati anche in formato esadecimale, ottale o binario usando rispettivamente un prefisso `0x`, `0o` o `0b`.</span><span class="sxs-lookup"><span data-stu-id="2f5aa-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="2f5aa-193">Caratteri di sottolineatura nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="2f5aa-193">Underscores in numeric literals</span></span>

<span data-ttu-id="2f5aa-194">È possibile separare le cifre con il carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="2f5aa-194">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="2f5aa-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f5aa-195">See also</span></span>

- [<span data-ttu-id="2f5aa-196">Classe Core. LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="2f5aa-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
