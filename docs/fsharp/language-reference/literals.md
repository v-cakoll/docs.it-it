---
title: Valori letterali (F#)
description: Informazioni sui tipi di valore letterali in di F# linguaggio di programmazione.
ms.date: 05/16/2016
ms.openlocfilehash: 7a531cd63c5a4dc1123834d481fc998216b0d82d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131339"
---
# <a name="literals"></a><span data-ttu-id="7107c-103">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="7107c-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="7107c-104">I collegamenti di riferimento API in questo articolo si passerà a MSDN (per ora).</span><span class="sxs-lookup"><span data-stu-id="7107c-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="7107c-105">In questo argomento fornisce una tabella che mostra come specificare il tipo di un valore letterale in F#.</span><span class="sxs-lookup"><span data-stu-id="7107c-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="7107c-106">Tipi letterali</span><span class="sxs-lookup"><span data-stu-id="7107c-106">Literal Types</span></span>

<span data-ttu-id="7107c-107">La tabella seguente illustra i tipi di valore letterali in F#.</span><span class="sxs-lookup"><span data-stu-id="7107c-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="7107c-108">I caratteri che rappresentano cifre in notazione esadecimale non sono tra maiuscole e minuscole; caratteri che identificano il tipo di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="7107c-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="7107c-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="7107c-109">Type</span></span>|<span data-ttu-id="7107c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7107c-110">Description</span></span>|<span data-ttu-id="7107c-111">Prefissi o suffissi</span><span class="sxs-lookup"><span data-stu-id="7107c-111">Suffix or prefix</span></span>|<span data-ttu-id="7107c-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="7107c-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="7107c-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="7107c-113">sbyte</span></span>|<span data-ttu-id="7107c-114">intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-114">signed 8-bit integer</span></span>|<span data-ttu-id="7107c-115">y</span><span class="sxs-lookup"><span data-stu-id="7107c-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="7107c-116">byte</span><span class="sxs-lookup"><span data-stu-id="7107c-116">byte</span></span>|<span data-ttu-id="7107c-117">Numero naturale senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="7107c-118">UY</span><span class="sxs-lookup"><span data-stu-id="7107c-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="7107c-119">int16</span><span class="sxs-lookup"><span data-stu-id="7107c-119">int16</span></span>|<span data-ttu-id="7107c-120">intero con segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-120">signed 16-bit integer</span></span>|<span data-ttu-id="7107c-121">s</span><span class="sxs-lookup"><span data-stu-id="7107c-121">s</span></span>|`86s`|
|<span data-ttu-id="7107c-122">uint16</span><span class="sxs-lookup"><span data-stu-id="7107c-122">uint16</span></span>|<span data-ttu-id="7107c-123">Numero naturale senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="7107c-124">us</span><span class="sxs-lookup"><span data-stu-id="7107c-124">us</span></span>|`86us`|
|<span data-ttu-id="7107c-125">int</span><span class="sxs-lookup"><span data-stu-id="7107c-125">int</span></span><br /><br /><span data-ttu-id="7107c-126">int32</span><span class="sxs-lookup"><span data-stu-id="7107c-126">int32</span></span>|<span data-ttu-id="7107c-127">intero con segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-127">signed 32-bit integer</span></span>|<span data-ttu-id="7107c-128">l o nessuno</span><span class="sxs-lookup"><span data-stu-id="7107c-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="7107c-129">uint</span><span class="sxs-lookup"><span data-stu-id="7107c-129">uint</span></span><br /><br /><span data-ttu-id="7107c-130">uint32</span><span class="sxs-lookup"><span data-stu-id="7107c-130">uint32</span></span>|<span data-ttu-id="7107c-131">Numero naturale senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="7107c-132">u o ul</span><span class="sxs-lookup"><span data-stu-id="7107c-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="7107c-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="7107c-133">unativeint</span></span>|<span data-ttu-id="7107c-134">puntatore nativo come numero naturale senza segno</span><span class="sxs-lookup"><span data-stu-id="7107c-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="7107c-135">Annulla la</span><span class="sxs-lookup"><span data-stu-id="7107c-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="7107c-136">int64</span><span class="sxs-lookup"><span data-stu-id="7107c-136">int64</span></span>|<span data-ttu-id="7107c-137">intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-137">signed 64-bit integer</span></span>|<span data-ttu-id="7107c-138">L</span><span class="sxs-lookup"><span data-stu-id="7107c-138">L</span></span>|`86L`|
|<span data-ttu-id="7107c-139">uint64</span><span class="sxs-lookup"><span data-stu-id="7107c-139">uint64</span></span>|<span data-ttu-id="7107c-140">Numero naturale senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="7107c-141">UL</span><span class="sxs-lookup"><span data-stu-id="7107c-141">UL</span></span>|`86UL`|
|<span data-ttu-id="7107c-142">float32 singolo,</span><span class="sxs-lookup"><span data-stu-id="7107c-142">single, float32</span></span>|<span data-ttu-id="7107c-143">numero a virgola mobile a 32 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-143">32-bit floating point number</span></span>|<span data-ttu-id="7107c-144">F o f</span><span class="sxs-lookup"><span data-stu-id="7107c-144">F or f</span></span>|<span data-ttu-id="7107c-145">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="7107c-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="7107c-146">LF</span><span class="sxs-lookup"><span data-stu-id="7107c-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="7107c-147">float; Double</span><span class="sxs-lookup"><span data-stu-id="7107c-147">float; double</span></span>|<span data-ttu-id="7107c-148">numero a virgola mobile a 64 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-148">64-bit floating point number</span></span>|<span data-ttu-id="7107c-149">none</span><span class="sxs-lookup"><span data-stu-id="7107c-149">none</span></span>|<span data-ttu-id="7107c-150">`4.14` o `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="7107c-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="7107c-151">LF</span><span class="sxs-lookup"><span data-stu-id="7107c-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="7107c-152">bigint</span><span class="sxs-lookup"><span data-stu-id="7107c-152">bigint</span></span>|<span data-ttu-id="7107c-153">Integer non limitato alla rappresentazione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="7107c-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="7107c-154">I</span><span class="sxs-lookup"><span data-stu-id="7107c-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="7107c-155">decimal</span><span class="sxs-lookup"><span data-stu-id="7107c-155">decimal</span></span>|<span data-ttu-id="7107c-156">numero frazionario rappresentato come un punto fisso o un numero razionale</span><span class="sxs-lookup"><span data-stu-id="7107c-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="7107c-157">M o m</span><span class="sxs-lookup"><span data-stu-id="7107c-157">M or m</span></span>|<span data-ttu-id="7107c-158">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="7107c-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="7107c-159">Char</span><span class="sxs-lookup"><span data-stu-id="7107c-159">Char</span></span>|<span data-ttu-id="7107c-160">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="7107c-160">Unicode character</span></span>|<span data-ttu-id="7107c-161">none</span><span class="sxs-lookup"><span data-stu-id="7107c-161">none</span></span>|`'a'`|
|<span data-ttu-id="7107c-162">Stringa</span><span class="sxs-lookup"><span data-stu-id="7107c-162">String</span></span>|<span data-ttu-id="7107c-163">Stringa Unicode</span><span class="sxs-lookup"><span data-stu-id="7107c-163">Unicode string</span></span>|<span data-ttu-id="7107c-164">none</span><span class="sxs-lookup"><span data-stu-id="7107c-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="7107c-165">oppure</span><span class="sxs-lookup"><span data-stu-id="7107c-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="7107c-166">oppure</span><span class="sxs-lookup"><span data-stu-id="7107c-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="7107c-167">oppure</span><span class="sxs-lookup"><span data-stu-id="7107c-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="7107c-168">Vedere anche [stringhe](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="7107c-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="7107c-169">byte</span><span class="sxs-lookup"><span data-stu-id="7107c-169">byte</span></span>|<span data-ttu-id="7107c-170">Carattere ASCII</span><span class="sxs-lookup"><span data-stu-id="7107c-170">ASCII character</span></span>|<span data-ttu-id="7107c-171">B</span><span class="sxs-lookup"><span data-stu-id="7107c-171">B</span></span>|`'a'B`|
|<span data-ttu-id="7107c-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="7107c-172">byte[]</span></span>|<span data-ttu-id="7107c-173">Stringa ASCII</span><span class="sxs-lookup"><span data-stu-id="7107c-173">ASCII string</span></span>|<span data-ttu-id="7107c-174">B</span><span class="sxs-lookup"><span data-stu-id="7107c-174">B</span></span>|`"text"B`|
|<span data-ttu-id="7107c-175">String o byte]</span><span class="sxs-lookup"><span data-stu-id="7107c-175">String or byte[]</span></span>|<span data-ttu-id="7107c-176">stringa verbatim</span><span class="sxs-lookup"><span data-stu-id="7107c-176">verbatim string</span></span>|<span data-ttu-id="7107c-177">prefisso @</span><span class="sxs-lookup"><span data-stu-id="7107c-177">@ prefix</span></span>|<span data-ttu-id="7107c-178">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="7107c-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="7107c-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="7107c-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="7107c-180">Note</span><span class="sxs-lookup"><span data-stu-id="7107c-180">Remarks</span></span>

<span data-ttu-id="7107c-181">Le stringhe Unicode possono contenere codifiche esplicite che è possibile specificare utilizzando `\u` seguita da un codice esadecimale a 16 bit o le codifiche UTF-32 che è possibile specificare utilizzando `\U` seguita da un codice esadecimale a 32 bit che rappresenta un Unicode coppia di surrogati.</span><span class="sxs-lookup"><span data-stu-id="7107c-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="7107c-182">A partire dal F# 3.1, è possibile usare il `+` accedere per combinare i valori letterali stringa.</span><span class="sxs-lookup"><span data-stu-id="7107c-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="7107c-183">È anche possibile usare i bit per bit o (`|||`) operatore per combinare i flag dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7107c-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="7107c-184">Ad esempio, il codice seguente è valido in F# 3.1:</span><span class="sxs-lookup"><span data-stu-id="7107c-184">For example, the following code is legal in F# 3.1:</span></span>

```fsharp
[<Literal>]
let literal1 = "a" + "b"

[<Literal>]
let fileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let literal2 = 1 ||| 64

[<Literal>]
let literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

<span data-ttu-id="7107c-185">Non è consentito l'uso di altri operatori bit per bit.</span><span class="sxs-lookup"><span data-stu-id="7107c-185">The use of other bitwise operators isn't allowed.</span></span>

## <a name="named-literals"></a><span data-ttu-id="7107c-186">Valori letterali denominati</span><span class="sxs-lookup"><span data-stu-id="7107c-186">Named Literals</span></span>

<span data-ttu-id="7107c-187">I valori che devono essere costanti possono essere contrassegnati con il [letterale](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attributo.</span><span class="sxs-lookup"><span data-stu-id="7107c-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="7107c-188">Questo attributo ha l'effetto di provocare un valore essere compilato come una costante.</span><span class="sxs-lookup"><span data-stu-id="7107c-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="7107c-189">Nelle espressioni dei criteri, gli identificatori che iniziano con caratteri minuscoli vengono sempre trattati come variabili da associare, anziché come valori letterali, pertanto è consigliabile in genere usare lettere maiuscole iniziali quando si definiscono i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="7107c-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="7107c-190">Numeri interi In altre basi</span><span class="sxs-lookup"><span data-stu-id="7107c-190">Integers In Other Bases</span></span>

<span data-ttu-id="7107c-191">È possibile anche specificare interi con segno a 32 bit binaria, ottale o esadecimale con un `0x`, `0o` o `0b` rispettivamente del prefisso.</span><span class="sxs-lookup"><span data-stu-id="7107c-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="7107c-192">Caratteri di sottolineatura nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="7107c-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="7107c-193">A partire da F# 4.1, è possibile separare cifre con il carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="7107c-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="7107c-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7107c-194">See also</span></span>

- [<span data-ttu-id="7107c-195">Classe Core. LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="7107c-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
