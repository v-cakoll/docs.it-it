---
title: Valori letterali (F#)
description: 'Informazioni sui tipi di valore letterale in F # linguaggio di programmazione.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 961d6a10122c5d5c691d394efa8d2b7b31a80453
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="literals"></a><span data-ttu-id="db727-103">Valori letterali</span><span class="sxs-lookup"><span data-stu-id="db727-103">Literals</span></span>

> [!NOTE]
<span data-ttu-id="db727-104">I collegamenti di riferimento API in questo articolo si passerà a MSDN (per ora).</span><span class="sxs-lookup"><span data-stu-id="db727-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="db727-105">In questo argomento fornisce una tabella in cui viene illustrato come specificare il tipo di un valore letterale in F #.</span><span class="sxs-lookup"><span data-stu-id="db727-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="db727-106">Tipi di valori letterali</span><span class="sxs-lookup"><span data-stu-id="db727-106">Literal Types</span></span>
<span data-ttu-id="db727-107">La tabella seguente illustra i tipi di valore letterale in F #.</span><span class="sxs-lookup"><span data-stu-id="db727-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="db727-108">Caratteri che rappresentano cifre in notazione esadecimale non fanno distinzione; caratteri che identificano il tipo di maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="db727-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="db727-109">Tipo</span><span class="sxs-lookup"><span data-stu-id="db727-109">Type</span></span>|<span data-ttu-id="db727-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db727-110">Description</span></span>|<span data-ttu-id="db727-111">Prefisso o suffisso</span><span class="sxs-lookup"><span data-stu-id="db727-111">Suffix or prefix</span></span>|<span data-ttu-id="db727-112">Esempi</span><span class="sxs-lookup"><span data-stu-id="db727-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="db727-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="db727-113">sbyte</span></span>|<span data-ttu-id="db727-114">Intero con segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="db727-114">signed 8-bit integer</span></span>|<span data-ttu-id="db727-115">y</span><span class="sxs-lookup"><span data-stu-id="db727-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="db727-116">byte</span><span class="sxs-lookup"><span data-stu-id="db727-116">byte</span></span>|<span data-ttu-id="db727-117">Numero naturale senza segno a 8 bit</span><span class="sxs-lookup"><span data-stu-id="db727-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="db727-118">UY</span><span class="sxs-lookup"><span data-stu-id="db727-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="db727-119">int16</span><span class="sxs-lookup"><span data-stu-id="db727-119">int16</span></span>|<span data-ttu-id="db727-120">Intero con segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="db727-120">signed 16-bit integer</span></span>|<span data-ttu-id="db727-121">s</span><span class="sxs-lookup"><span data-stu-id="db727-121">s</span></span>|`86s`|
|<span data-ttu-id="db727-122">uint16</span><span class="sxs-lookup"><span data-stu-id="db727-122">uint16</span></span>|<span data-ttu-id="db727-123">numero di naturale senza segno a 16 bit</span><span class="sxs-lookup"><span data-stu-id="db727-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="db727-124">us</span><span class="sxs-lookup"><span data-stu-id="db727-124">us</span></span>|`86us`|
|<span data-ttu-id="db727-125">int</span><span class="sxs-lookup"><span data-stu-id="db727-125">int</span></span><br /><br /><span data-ttu-id="db727-126">int32</span><span class="sxs-lookup"><span data-stu-id="db727-126">int32</span></span>|<span data-ttu-id="db727-127">Intero con segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="db727-127">signed 32-bit integer</span></span>|<span data-ttu-id="db727-128">l o nessuno</span><span class="sxs-lookup"><span data-stu-id="db727-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="db727-129">uint</span><span class="sxs-lookup"><span data-stu-id="db727-129">uint</span></span><br /><br /><span data-ttu-id="db727-130">uint32</span><span class="sxs-lookup"><span data-stu-id="db727-130">uint32</span></span>|<span data-ttu-id="db727-131">Numero naturale senza segno a 32 bit</span><span class="sxs-lookup"><span data-stu-id="db727-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="db727-132">u o ul</span><span class="sxs-lookup"><span data-stu-id="db727-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="db727-133">unativeint</span><span class="sxs-lookup"><span data-stu-id="db727-133">unativeint</span></span>|<span data-ttu-id="db727-134">puntatore nativo come un numero naturale senza segno</span><span class="sxs-lookup"><span data-stu-id="db727-134">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="db727-135">Annulla</span><span class="sxs-lookup"><span data-stu-id="db727-135">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="db727-136">int64</span><span class="sxs-lookup"><span data-stu-id="db727-136">int64</span></span>|<span data-ttu-id="db727-137">Intero con segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="db727-137">signed 64-bit integer</span></span>|<span data-ttu-id="db727-138">L</span><span class="sxs-lookup"><span data-stu-id="db727-138">L</span></span>|`86L`|
|<span data-ttu-id="db727-139">uint64</span><span class="sxs-lookup"><span data-stu-id="db727-139">uint64</span></span>|<span data-ttu-id="db727-140">numero di naturale senza segno a 64 bit</span><span class="sxs-lookup"><span data-stu-id="db727-140">unsigned 64-bit natural number</span></span>|<span data-ttu-id="db727-141">UL</span><span class="sxs-lookup"><span data-stu-id="db727-141">UL</span></span>|`86UL`|
|<span data-ttu-id="db727-142">float32 singolo,</span><span class="sxs-lookup"><span data-stu-id="db727-142">single, float32</span></span>|<span data-ttu-id="db727-143">numero a virgola mobile a 32 bit</span><span class="sxs-lookup"><span data-stu-id="db727-143">32-bit floating point number</span></span>|<span data-ttu-id="db727-144">F o f</span><span class="sxs-lookup"><span data-stu-id="db727-144">F or f</span></span>|<span data-ttu-id="db727-145">`4.14F` o `4.14f`</span><span class="sxs-lookup"><span data-stu-id="db727-145">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="db727-146">LF</span><span class="sxs-lookup"><span data-stu-id="db727-146">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="db727-147">float; Double</span><span class="sxs-lookup"><span data-stu-id="db727-147">float; double</span></span>|<span data-ttu-id="db727-148">numero a virgola mobile a 64 bit</span><span class="sxs-lookup"><span data-stu-id="db727-148">64-bit floating point number</span></span>|<span data-ttu-id="db727-149">none</span><span class="sxs-lookup"><span data-stu-id="db727-149">none</span></span>|<span data-ttu-id="db727-150">`4.14` o `2.3E+32` o `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="db727-150">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="db727-151">LF</span><span class="sxs-lookup"><span data-stu-id="db727-151">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="db727-152">bigint</span><span class="sxs-lookup"><span data-stu-id="db727-152">bigint</span></span>|<span data-ttu-id="db727-153">numero intero non è limitato a una rappresentazione a 64 bit</span><span class="sxs-lookup"><span data-stu-id="db727-153">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="db727-154">I</span><span class="sxs-lookup"><span data-stu-id="db727-154">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="db727-155">decimal</span><span class="sxs-lookup"><span data-stu-id="db727-155">decimal</span></span>|<span data-ttu-id="db727-156">numero frazionario rappresentato come un punto fisso o un numero razionale</span><span class="sxs-lookup"><span data-stu-id="db727-156">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="db727-157">M o m</span><span class="sxs-lookup"><span data-stu-id="db727-157">M or m</span></span>|<span data-ttu-id="db727-158">`0.7833M` o `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="db727-158">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="db727-159">Char</span><span class="sxs-lookup"><span data-stu-id="db727-159">Char</span></span>|<span data-ttu-id="db727-160">Carattere Unicode</span><span class="sxs-lookup"><span data-stu-id="db727-160">Unicode character</span></span>|<span data-ttu-id="db727-161">none</span><span class="sxs-lookup"><span data-stu-id="db727-161">none</span></span>|`'a'`|
|<span data-ttu-id="db727-162">Stringa</span><span class="sxs-lookup"><span data-stu-id="db727-162">String</span></span>|<span data-ttu-id="db727-163">Stringa Unicode</span><span class="sxs-lookup"><span data-stu-id="db727-163">Unicode string</span></span>|<span data-ttu-id="db727-164">none</span><span class="sxs-lookup"><span data-stu-id="db727-164">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="db727-165">oppure</span><span class="sxs-lookup"><span data-stu-id="db727-165">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="db727-166">oppure</span><span class="sxs-lookup"><span data-stu-id="db727-166">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="db727-167">oppure</span><span class="sxs-lookup"><span data-stu-id="db727-167">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="db727-168">Vedere anche [stringhe](Strings.md).</span><span class="sxs-lookup"><span data-stu-id="db727-168">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="db727-169">byte</span><span class="sxs-lookup"><span data-stu-id="db727-169">byte</span></span>|<span data-ttu-id="db727-170">Carattere ASCII</span><span class="sxs-lookup"><span data-stu-id="db727-170">ASCII character</span></span>|<span data-ttu-id="db727-171">B</span><span class="sxs-lookup"><span data-stu-id="db727-171">B</span></span>|`'a'B`|
|<span data-ttu-id="db727-172">byte[]</span><span class="sxs-lookup"><span data-stu-id="db727-172">byte[]</span></span>|<span data-ttu-id="db727-173">Stringa ASCII</span><span class="sxs-lookup"><span data-stu-id="db727-173">ASCII string</span></span>|<span data-ttu-id="db727-174">B</span><span class="sxs-lookup"><span data-stu-id="db727-174">B</span></span>|`"text"B`|
|<span data-ttu-id="db727-175">String o byte]</span><span class="sxs-lookup"><span data-stu-id="db727-175">String or byte[]</span></span>|<span data-ttu-id="db727-176">stringa verbatim</span><span class="sxs-lookup"><span data-stu-id="db727-176">verbatim string</span></span>|<span data-ttu-id="db727-177">prefisso @</span><span class="sxs-lookup"><span data-stu-id="db727-177">@ prefix</span></span>|<span data-ttu-id="db727-178">`@"\\server\share"` (Unicode)</span><span class="sxs-lookup"><span data-stu-id="db727-178">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="db727-179">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="db727-179">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="remarks"></a><span data-ttu-id="db727-180">Note</span><span class="sxs-lookup"><span data-stu-id="db727-180">Remarks</span></span>
<span data-ttu-id="db727-181">Le stringhe Unicode possono contenere codifiche esplicite che è possibile specificare utilizzando `\u` seguito da un codice esadecimale a 16 bit o codifiche UTF-32 che è possibile specificare utilizzando `\U` seguito da un codice esadecimale a 32 bit che rappresenta un Unicode coppia di surrogati.</span><span class="sxs-lookup"><span data-stu-id="db727-181">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="db727-182">A partire da F # 3.1, è possibile utilizzare il `+` accedere per combinare i valori letterali stringa.</span><span class="sxs-lookup"><span data-stu-id="db727-182">As of F# 3.1, you can use the `+` sign to combine string literals.</span></span> <span data-ttu-id="db727-183">È inoltre possibile utilizzare il bit per bit o (`|||`) (operatore) per combinare i flag di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="db727-183">You can also use the bitwise or (`|||`) operator to combine enum flags.</span></span> <span data-ttu-id="db727-184">Ad esempio, il codice seguente è valido in F # 3.1:</span><span class="sxs-lookup"><span data-stu-id="db727-184">For example, the following code is legal in F# 3.1:</span></span>

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

<span data-ttu-id="db727-185">Non è consentito l'uso di altri operatori bit per bit.</span><span class="sxs-lookup"><span data-stu-id="db727-185">The use of other bitwise operators isn't allowed.</span></span>


## <a name="named-literals"></a><span data-ttu-id="db727-186">Valori letterali denominati</span><span class="sxs-lookup"><span data-stu-id="db727-186">Named Literals</span></span>
<span data-ttu-id="db727-187">I valori che devono essere costanti possono essere contrassegnati con il [letterale](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attributo.</span><span class="sxs-lookup"><span data-stu-id="db727-187">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="db727-188">Questo attributo ha l'effetto della causa di un valore essere compilata come una costante.</span><span class="sxs-lookup"><span data-stu-id="db727-188">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="db727-189">Nelle espressioni dei criteri, gli identificatori che iniziano con caratteri minuscoli vengono sempre considerati come variabili di essere vincolato, anziché come valori letterali, pertanto è in genere consigliabile utilizzare le lettere maiuscole iniziali quando si definiscono i valori letterali.</span><span class="sxs-lookup"><span data-stu-id="db727-189">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="db727-190">Numeri interi In altra base</span><span class="sxs-lookup"><span data-stu-id="db727-190">Integers In Other Bases</span></span>

<span data-ttu-id="db727-191">È inoltre possibile specificare interi con segno a 32 bit binaria, ottale o esadecimale con un `0x`, `0o` o `0b` prefisso rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="db727-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let Numbers = (0x9F, 0o77, 0b1010)
// Result: Numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="db727-192">Caratteri di sottolineatura nei valori letterali numerici</span><span class="sxs-lookup"><span data-stu-id="db727-192">Underscores in Numeric Literals</span></span>

<span data-ttu-id="db727-193">A partire da F # 4.1, è possibile separare cifre con il carattere di sottolineatura (`_`).</span><span class="sxs-lookup"><span data-stu-id="db727-193">Starting with F# 4.1, you can separate digits with the underscore character (`_`).</span></span>

```fsharp
let DeadBeef = 0xDEAD_BEEF

let DeadBeefAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let ExampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="db727-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db727-194">See Also</span></span>

[<span data-ttu-id="db727-195">Classe Core. LiteralAttribute</span><span class="sxs-lookup"><span data-stu-id="db727-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
