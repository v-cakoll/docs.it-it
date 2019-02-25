---
title: Procedure consigliate di interoperabilità nativa - .NET
description: Informazioni sulle procedure consigliate per interfacciarsi con i componenti nativi in .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 90a707830049b5edf574b83e7ca03ec30527b001
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2019
ms.locfileid: "56411451"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="debb8-103">Procedure consigliate di interoperabilità nativa</span><span class="sxs-lookup"><span data-stu-id="debb8-103">Native interoperability best practices</span></span>

<span data-ttu-id="debb8-104">.NET offre diversi modi per personalizzare il codice di interoperabilità nativa.</span><span class="sxs-lookup"><span data-stu-id="debb8-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="debb8-105">Questo articolo include le linee guida seguite dai team di Microsoft .NET per l'interoperabilità nativa.</span><span class="sxs-lookup"><span data-stu-id="debb8-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="debb8-106">Indicazioni generali</span><span class="sxs-lookup"><span data-stu-id="debb8-106">General guidance</span></span>

<span data-ttu-id="debb8-107">Le linee guida in questa sezione si applicano a tutti gli scenari di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="debb8-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="debb8-108">**✔️ USARE** le stesse convenzioni di denominazione e la stessa combinazione di maiuscole/minuscole per i metodi e i parametri del metodo nativo che si vuole chiamare.</span><span class="sxs-lookup"><span data-stu-id="debb8-108">**✔️ DO** use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="debb8-109">**✔️ PRENDERE IN CONSIDERAZIONE** l'uso delle stesse convenzioni di denominazione e della stessa combinazione di maiuscole/minuscole per i valori costanti.</span><span class="sxs-lookup"><span data-stu-id="debb8-109">**✔️ CONSIDER** using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="debb8-110">**✔️ USARE** i tipi .NET più simili al tipo nativo.</span><span class="sxs-lookup"><span data-stu-id="debb8-110">**✔️ DO** use .NET types that map closest to the native type.</span></span> <span data-ttu-id="debb8-111">Ad esempio, in C# usare `uint` quando il tipo nativo è `unsigned int`.</span><span class="sxs-lookup"><span data-stu-id="debb8-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="debb8-112">**✔️ USARE** solo attributi `[In]` e `[Out]` quando il comportamento desiderato è diverso da quello predefinito.</span><span class="sxs-lookup"><span data-stu-id="debb8-112">**✔️ DO** only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="debb8-113">**✔️ PRENDERE IN CONSIDERAZIONE** l'uso di <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> per i pool di buffer di matrici nativi.</span><span class="sxs-lookup"><span data-stu-id="debb8-113">**✔️ CONSIDER** using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="debb8-114">**✔️ PRENDERE IN CONSIDERAZIONE** il wrapping delle dichiarazioni P/Invoke in una classe con lo stesso nome e combinazione di maiuscole/minuscole della libreria nativa.</span><span class="sxs-lookup"><span data-stu-id="debb8-114">**✔️ CONSIDER** wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="debb8-115">In questo modo gli attributi `[DllImport]` possono usare la funzionalità del linguaggio `nameof` C# per passare il nome della libreria nativa e assicurarsi che il nome della libreria nativa non sia stato digitato in modo errato.</span><span class="sxs-lookup"><span data-stu-id="debb8-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="debb8-116">Impostazioni degli attributi DllImport</span><span class="sxs-lookup"><span data-stu-id="debb8-116">DllImport attribute settings</span></span>

| <span data-ttu-id="debb8-117">Impostazione</span><span class="sxs-lookup"><span data-stu-id="debb8-117">Setting</span></span> | <span data-ttu-id="debb8-118">Impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="debb8-118">Default</span></span> | <span data-ttu-id="debb8-119">Consiglio</span><span class="sxs-lookup"><span data-stu-id="debb8-119">Recommendation</span></span> | <span data-ttu-id="debb8-120">Dettagli</span><span class="sxs-lookup"><span data-stu-id="debb8-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="debb8-121">Mantenere l'impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="debb8-121">keep default</span></span>  | <span data-ttu-id="debb8-122">Con l'impostazione esplicita su false, i valori restituiti HRESULT di errore verranno convertiti in eccezioni e il valore restituito nella definizione diventa Null di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="debb8-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="debb8-123">Dipende dall'API</span><span class="sxs-lookup"><span data-stu-id="debb8-123">depends on the API</span></span>  | <span data-ttu-id="debb8-124">Impostare su true se l'API usa GetLastError e usare Marshal.GetLastWin32Error per ottenere il valore.</span><span class="sxs-lookup"><span data-stu-id="debb8-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="debb8-125">Se l'API imposta una condizione che indica la presenza di un errore, recuperare l'errore prima di effettuare altre chiamate in modo da evitare di sovrascriverlo inavvertitamente.</span><span class="sxs-lookup"><span data-stu-id="debb8-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="debb8-126">`CharSet.None` con fallback al comportamento `CharSet.Ansi`</span><span class="sxs-lookup"><span data-stu-id="debb8-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="debb8-127">Usare in modo esplicito `CharSet.Unicode` o `CharSet.Ansi` quando sono presenti stringhe o caratteri nella definizione</span><span class="sxs-lookup"><span data-stu-id="debb8-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="debb8-128">Specifica il comportamento di marshalling delle stringhe e cosa fa `ExactSpelling` quando l'impostazione è `false`.</span><span class="sxs-lookup"><span data-stu-id="debb8-128">This specifies marshalling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="debb8-129">Si noti che `CharSet.Ansi` è in effetti UTF8 su Unix.</span><span class="sxs-lookup"><span data-stu-id="debb8-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="debb8-130">Nella _maggior parte_ dei casi Windows usa Unicode, mentre Unix usa UTF8.</span><span class="sxs-lookup"><span data-stu-id="debb8-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="debb8-131">Vedere altre informazioni nella [documentazione sui set di caratteri](./charset.md).</span><span class="sxs-lookup"><span data-stu-id="debb8-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="debb8-132">Impostare su true e ottenere un leggero miglioramento delle prestazioni perché il runtime non cercherà nomi di funzioni alternativi con suffisso "A" o "W" in base al valore dell'impostazione `CharSet` ("A" per `CharSet.Ansi` e "W" per `CharSet.Unicode`).</span><span class="sxs-lookup"><span data-stu-id="debb8-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="debb8-133">Parametri stringa</span><span class="sxs-lookup"><span data-stu-id="debb8-133">String parameters</span></span>

<span data-ttu-id="debb8-134">Quando il set di caratteri è Unicode o l'argomento è contrassegnato in modo esplicito come `[MarshalAs(UnmanagedType.LPWSTR)]` _e_ la stringa viene passata per valore (non `ref` o `out`), la stringa verrà bloccata e usata direttamente dal codice nativo (anziché copiata).</span><span class="sxs-lookup"><span data-stu-id="debb8-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="debb8-135">Ricordarsi di contrassegnare `[DllImport]` come `Charset.Unicode` a meno che non si voglia usare in modo esplicito il trattamento ANSI per le stringhe.</span><span class="sxs-lookup"><span data-stu-id="debb8-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="debb8-136">**❌ NON** usare parametri `[Out] string`.</span><span class="sxs-lookup"><span data-stu-id="debb8-136">**❌ DO NOT** use `[Out] string` parameters.</span></span> <span data-ttu-id="debb8-137">I parametri stringa passati per valore con l'attributo `[Out]` possono destabilizzare il runtime se la stringa è una stringa centralizzata.</span><span class="sxs-lookup"><span data-stu-id="debb8-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="debb8-138">Altre informazioni sulla centralizzazione delle stringhe sono disponibili nella documentazione relativa a <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="debb8-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="debb8-139">**❌ EVITARE** parametri `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="debb8-139">**❌ AVOID** `StringBuilder` parameters.</span></span> <span data-ttu-id="debb8-140">Il marshalling di `StringBuilder` crea *sempre* una copia del buffer nativo.</span><span class="sxs-lookup"><span data-stu-id="debb8-140">`StringBuilder` marshalling *always* creates a native buffer copy.</span></span> <span data-ttu-id="debb8-141">Di conseguenza, può risultare estremamente inefficiente.</span><span class="sxs-lookup"><span data-stu-id="debb8-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="debb8-142">Si consideri lo scenario tipico di chiamata di un'API di Windows che accetta una stringa:</span><span class="sxs-lookup"><span data-stu-id="debb8-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="debb8-143">Creare un SB con la capacità desiderata (alloca capacità gestita) **{1}**</span><span class="sxs-lookup"><span data-stu-id="debb8-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="debb8-144">Invoke</span><span class="sxs-lookup"><span data-stu-id="debb8-144">Invoke</span></span>
   1. <span data-ttu-id="debb8-145">Alloca un buffer nativo **{2}**</span><span class="sxs-lookup"><span data-stu-id="debb8-145">Allocates a native buffer **{2}**</span></span>  
   2. <span data-ttu-id="debb8-146">Copia il contenuto, se `[In]`  _(valore predefinito per un parametro `StringBuilder`)_</span><span class="sxs-lookup"><span data-stu-id="debb8-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>  
   3. <span data-ttu-id="debb8-147">Copia il buffer nativo in una nuova matrice gestita allocata se `[Out]` **{3}**  _(valore predefinito anche per `StringBuilder`)_</span><span class="sxs-lookup"><span data-stu-id="debb8-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>  
3. <span data-ttu-id="debb8-148">`ToString()` alloca ancora un'altra matrice gestita **{4}**</span><span class="sxs-lookup"><span data-stu-id="debb8-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="debb8-149">Vale a dire *{4}* allocazioni per ottenere una stringa dal codice nativo.</span><span class="sxs-lookup"><span data-stu-id="debb8-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="debb8-150">Il meglio che è possibile fare per limitare le allocazioni è riutilizzare `StringBuilder` in un'altra chiamata, ma in questo modo si risparmia solo *1* allocazione.</span><span class="sxs-lookup"><span data-stu-id="debb8-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="debb8-151">È molto meglio usare e memorizzare nella cache un buffer di caratteri da `ArrayPool`. In questo modo si può arrivare alla sola allocazione per `ToString()` nelle chiamate successive.</span><span class="sxs-lookup"><span data-stu-id="debb8-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="debb8-152">L'altro problema con `StringBuilder` è che copia sempre il buffer restituito fino primo valore Null.</span><span class="sxs-lookup"><span data-stu-id="debb8-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="debb8-153">Se la stringa passata non è terminata o è una stringa con terminazione Null doppia, nel migliore dei casi P/Invoke non è corretto.</span><span class="sxs-lookup"><span data-stu-id="debb8-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="debb8-154">Se si *usa* `StringBuilder`, un altro aspetto da tenere presente è che la capacità **non** include un valore Null nascosto, sempre considerato per l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="debb8-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="debb8-155">È comune sbagliarsi, perché la maggior parte delle API vuole le dimensioni del buffer *comprensive* del valore Null.</span><span class="sxs-lookup"><span data-stu-id="debb8-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="debb8-156">Ciò può comportare allocazioni sprecate/superflue.</span><span class="sxs-lookup"><span data-stu-id="debb8-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="debb8-157">Inoltre, questo problema impedisce al runtime di ottimizzare il marshalling di `StringBuilder` per ridurre al minimo le copie.</span><span class="sxs-lookup"><span data-stu-id="debb8-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshalling to minimize copies.</span></span>

<span data-ttu-id="debb8-158">**✔️ PRENDERE IN CONSIDERAZIONE** l'uso di `char[]` da un `ArrayPool`.</span><span class="sxs-lookup"><span data-stu-id="debb8-158">**✔️ CONSIDER** using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="debb8-159">Per altre informazioni sul marshalling delle stringhe, vedere [Marshalling predefinito per le stringhe](../../framework/interop/default-marshaling-for-strings.md) e [Personalizzazione dei parametri stringa](customize-parameter-marshalling.md#customizing-string-parameters).</span><span class="sxs-lookup"><span data-stu-id="debb8-159">For more information on string marshalling, see [Default Marshalling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshalling](customize-parameter-marshalling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="debb8-160">__Informazioni specifiche per Windows__</span><span class="sxs-lookup"><span data-stu-id="debb8-160">__Windows Specific__</span></span>  
> <span data-ttu-id="debb8-161">Per le stringhe `[Out]`, CLR userà `CoTaskMemFree` per impostazione predefinita per liberare le stringhe o `SysStringFree` per le stringhe contrassegnate come `UnmanagedType.BSTR`.</span><span class="sxs-lookup"><span data-stu-id="debb8-161">For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>  
<span data-ttu-id="debb8-162">**Per la maggior parte delle API con un buffer di stringhe di output:**</span><span class="sxs-lookup"><span data-stu-id="debb8-162">**For most APIs with an output string buffer:**</span></span>  
> <span data-ttu-id="debb8-163">Il numero di caratteri passato deve includere il carattere Null.</span><span class="sxs-lookup"><span data-stu-id="debb8-163">The passed in character count must include the null.</span></span> <span data-ttu-id="debb8-164">Se il valore restituito è minore del numero di caratteri passato, la chiamata ha avuto esito positivo e il valore è il numero di caratteri *senza* il carattere Null finale.</span><span class="sxs-lookup"><span data-stu-id="debb8-164">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="debb8-165">In caso contrario, il numero corrisponde alle dimensioni richieste del buffer *incluso* il carattere Null.</span><span class="sxs-lookup"><span data-stu-id="debb8-165">Otherwise the count is the required size of the buffer *including* the null character.</span></span>  
> - <span data-ttu-id="debb8-166">Passando 5 si ottiene 4: la lunghezza della stringa è di 4 caratteri con un carattere Null finale.</span><span class="sxs-lookup"><span data-stu-id="debb8-166">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="debb8-167">Passando 5 si ottiene 6: la lunghezza della stringa è di 5 caratteri ed è necessario un buffer di 6 caratteri per contenere il carattere Null.</span><span class="sxs-lookup"><span data-stu-id="debb8-167">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>  
> [<span data-ttu-id="debb8-168">Tipi di dati di Windows per le stringhe</span><span class="sxs-lookup"><span data-stu-id="debb8-168">Windows Data Types for Strings</span></span>](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="debb8-169">Parametri e campi booleani</span><span class="sxs-lookup"><span data-stu-id="debb8-169">Boolean parameters and fields</span></span>

<span data-ttu-id="debb8-170">È facile sbagliare con i valori booleani.</span><span class="sxs-lookup"><span data-stu-id="debb8-170">Booleans are easy to mess up.</span></span> <span data-ttu-id="debb8-171">Per impostazione predefinita, per il tipo `bool` .NET viene effettuato il marshalling nel tipo `BOOL` Windows, in cui è un valore a 4 byte.</span><span class="sxs-lookup"><span data-stu-id="debb8-171">By default, a .NET `bool` is marshalled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="debb8-172">Tuttavia, i tipi `_Bool` e `bool` in C e C++ sono a byte *singolo*.</span><span class="sxs-lookup"><span data-stu-id="debb8-172">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="debb8-173">A causa di questa differenza può essere difficile risolvere eventuali bug, perché metà del valore restituito verrà rimosso e il risultato verrà modificato solo *potenzialmente*.</span><span class="sxs-lookup"><span data-stu-id="debb8-173">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="debb8-174">Per altre informazioni sul marshalling dei valori `bool` .NET nei tipi `bool` C o C++, vedere la documentazione relativa alla [personalizzazione del marshalling di campi booleani](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span><span class="sxs-lookup"><span data-stu-id="debb8-174">For more for information on marshalling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshalling](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span></span>

## <a name="guids"></a><span data-ttu-id="debb8-175">GUID</span><span class="sxs-lookup"><span data-stu-id="debb8-175">GUIDs</span></span>

<span data-ttu-id="debb8-176">I GUID possono essere usati direttamente nelle firme.</span><span class="sxs-lookup"><span data-stu-id="debb8-176">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="debb8-177">Molte API di Windows accettano alias del tipo `GUID&` come `REFIID`.</span><span class="sxs-lookup"><span data-stu-id="debb8-177">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="debb8-178">In caso di passaggio per riferimento, possono essere passati per `ref` o con l'attributo `[MarshalAs(UnmanagedType.LPStruct)]`.</span><span class="sxs-lookup"><span data-stu-id="debb8-178">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="debb8-179">GUID</span><span class="sxs-lookup"><span data-stu-id="debb8-179">GUID</span></span> | <span data-ttu-id="debb8-180">GUID per riferimento</span><span class="sxs-lookup"><span data-stu-id="debb8-180">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="debb8-181">**❌ NON** usare `[MarshalAs(UnmanagedType.LPStruct)]` se non per i parametri GUID `ref`.</span><span class="sxs-lookup"><span data-stu-id="debb8-181">**❌ DO NOT** Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="debb8-182">Tipi copiabili da BLT</span><span class="sxs-lookup"><span data-stu-id="debb8-182">Blittable types</span></span>

<span data-ttu-id="debb8-183">I tipi copiabili da BLT sono tipi che hanno la stessa rappresentazione a livello di bit nel codice gestito e nativo.</span><span class="sxs-lookup"><span data-stu-id="debb8-183">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="debb8-184">Di conseguenza non devono essere convertiti in un altro formato per effettuarne il marshalling in e da codice nativo e dovrebbero essere preferiti perché ciò migliora le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="debb8-184">As such they do not need to be converted to another format to be marshalled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="debb8-185">**Tipi copiabili da BLT:**</span><span class="sxs-lookup"><span data-stu-id="debb8-185">**Blittable types:**</span></span>

- <span data-ttu-id="debb8-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span><span class="sxs-lookup"><span data-stu-id="debb8-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="debb8-187">Matrici unidimensionali non annidate di tipi copiabili da BLT (ad esempio, `int[]`)</span><span class="sxs-lookup"><span data-stu-id="debb8-187">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="debb8-188">Struct e classi con layout fisso che hanno solo tipi valore copiabili da BLT per i campi di istanza</span><span class="sxs-lookup"><span data-stu-id="debb8-188">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="debb8-189">Per il layout fisso è richiesto `[StructLayout(LayoutKind.Sequential)]` o `[StructLayout(LayoutKind.Explicit)]`</span><span class="sxs-lookup"><span data-stu-id="debb8-189">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="debb8-190">Gli struct sono `LayoutKind.Sequential` per impostazione predefinita, le classi sono `LayoutKind.Auto`</span><span class="sxs-lookup"><span data-stu-id="debb8-190">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="debb8-191">**NON copiabili da BLT:**</span><span class="sxs-lookup"><span data-stu-id="debb8-191">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="debb8-192">**A VOLTE copiabili da BLT:**</span><span class="sxs-lookup"><span data-stu-id="debb8-192">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="debb8-193">`char`, `string`</span><span class="sxs-lookup"><span data-stu-id="debb8-193">`char`, `string`</span></span>

<span data-ttu-id="debb8-194">Quando i tipi copiabili da BLT vengono passati per riferimento, vengono semplicemente bloccati dal gestore del marshalling invece di essere copiati in un buffer intermedio.</span><span class="sxs-lookup"><span data-stu-id="debb8-194">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="debb8-195">(Le classi vengono passare in modo intrinseco per riferimento, mentre gli struct vengono passati per riferimento quando vengono usati con `ref` o `out`.)</span><span class="sxs-lookup"><span data-stu-id="debb8-195">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="debb8-196">`char` è copiabile da BLT in una matrice unidimensionale **oppure** se fa parte di un tipo che lo contiene viene contrassegnato in modo esplicito con `[StructLayout]` con `CharSet = CharSet.Unicode`.</span><span class="sxs-lookup"><span data-stu-id="debb8-196">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="debb8-197">`string` è copiabile da BLT se non è contenuto in un altro tipo e viene passato come argomento che è contrassegnato con `[MarshalAs(UnmanagedType.LPWStr)]` o se per `[DllImport]` è impostato `CharSet = CharSet.Unicode`.</span><span class="sxs-lookup"><span data-stu-id="debb8-197">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="debb8-198">È possibile verificare se un tipo è copiabile da BLT tentando di creare un `GCHandle` bloccato.</span><span class="sxs-lookup"><span data-stu-id="debb8-198">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="debb8-199">Se il tipo non è una stringa o non è considerato copiabile da BLT, `GCHandle.Alloc` genererà una `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="debb8-199">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="debb8-200">**✔️ RENDERE** le strutture copiabili da BLT quando possibile.</span><span class="sxs-lookup"><span data-stu-id="debb8-200">**✔️ DO** make your structures blittable when possible.</span></span>

<span data-ttu-id="debb8-201">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="debb8-201">For more information, see:</span></span>

- [<span data-ttu-id="debb8-202">Tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="debb8-202">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)  
- [<span data-ttu-id="debb8-203">Marshalling dei tipi</span><span class="sxs-lookup"><span data-stu-id="debb8-203">Type Marshalling</span></span>](type-marshalling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="debb8-204">Mantenere attivi gli oggetti gestiti</span><span class="sxs-lookup"><span data-stu-id="debb8-204">Keeping managed objects alive</span></span>

<span data-ttu-id="debb8-205">`GC.KeepAlive()` garantisce che un oggetto rimanga nell'ambito fino a quando non viene raggiunto il metodo KeepAlive.</span><span class="sxs-lookup"><span data-stu-id="debb8-205">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="debb8-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) consente al gestore di marshalling mantenere attivo un oggetto per la durata di P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="debb8-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="debb8-207">Può essere usato al posto di `IntPtr` nelle firme dei metodi.</span><span class="sxs-lookup"><span data-stu-id="debb8-207">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="debb8-208">`SafeHandle` sostituisce questa classe in modo efficace ed è consigliabile usarlo in alternativa.</span><span class="sxs-lookup"><span data-stu-id="debb8-208">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="debb8-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) consente di bloccare un oggetto gestito e di ottenere il puntatore nativo a tale oggetto.</span><span class="sxs-lookup"><span data-stu-id="debb8-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="debb8-210">Il modello di base è:</span><span class="sxs-lookup"><span data-stu-id="debb8-210">The basic pattern is:</span></span>  

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="debb8-211">L'aggiunta non è il comportamento predefinito per `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="debb8-211">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="debb8-212">L'altro modello principale è per il passaggio di un riferimento a un oggetto gestito tramite codice nativo per tornare poi al codice gestito, in genere con un callback.</span><span class="sxs-lookup"><span data-stu-id="debb8-212">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="debb8-213">Ecco il modello:</span><span class="sxs-lookup"><span data-stu-id="debb8-213">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="debb8-214">Non dimenticare che `GCHandle` deve essere liberato in modo esplicito per evitare perdite di memoria.</span><span class="sxs-lookup"><span data-stu-id="debb8-214">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="debb8-215">Tipi di dati Windows comuni</span><span class="sxs-lookup"><span data-stu-id="debb8-215">Common Windows data types</span></span>

<span data-ttu-id="debb8-216">Ecco un elenco dei tipi di dati comunemente usati nelle API Win32 e dei tipi C# da usare per chiamate nel codice Win32.</span><span class="sxs-lookup"><span data-stu-id="debb8-216">Here is a list of data types commonly used in Win32 APIs and which C# types to use when calling into the Win32 code.</span></span>

<span data-ttu-id="debb8-217">I tipi seguenti hanno le stesse dimensioni in Windows a 32 e 64 bit, nonostante i nomi.</span><span class="sxs-lookup"><span data-stu-id="debb8-217">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="debb8-218">Larghezza</span><span class="sxs-lookup"><span data-stu-id="debb8-218">Width</span></span> | <span data-ttu-id="debb8-219">WINDOWS</span><span class="sxs-lookup"><span data-stu-id="debb8-219">Windows</span></span>          | <span data-ttu-id="debb8-220">C (Windows)</span><span class="sxs-lookup"><span data-stu-id="debb8-220">C (Windows)</span></span>          | <span data-ttu-id="debb8-221">C#</span><span class="sxs-lookup"><span data-stu-id="debb8-221">C#</span></span>       | <span data-ttu-id="debb8-222">Alternativa</span><span class="sxs-lookup"><span data-stu-id="debb8-222">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="debb8-223">32</span><span class="sxs-lookup"><span data-stu-id="debb8-223">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="debb8-224">8</span><span class="sxs-lookup"><span data-stu-id="debb8-224">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="debb8-225">8</span><span class="sxs-lookup"><span data-stu-id="debb8-225">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="debb8-226">8</span><span class="sxs-lookup"><span data-stu-id="debb8-226">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="debb8-227">8</span><span class="sxs-lookup"><span data-stu-id="debb8-227">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="debb8-228">16</span><span class="sxs-lookup"><span data-stu-id="debb8-228">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="debb8-229">16</span><span class="sxs-lookup"><span data-stu-id="debb8-229">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="debb8-230">16</span><span class="sxs-lookup"><span data-stu-id="debb8-230">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="debb8-231">16</span><span class="sxs-lookup"><span data-stu-id="debb8-231">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="debb8-232">16</span><span class="sxs-lookup"><span data-stu-id="debb8-232">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="debb8-233">32</span><span class="sxs-lookup"><span data-stu-id="debb8-233">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="debb8-234">32</span><span class="sxs-lookup"><span data-stu-id="debb8-234">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="debb8-235">32</span><span class="sxs-lookup"><span data-stu-id="debb8-235">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="debb8-236">32</span><span class="sxs-lookup"><span data-stu-id="debb8-236">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="debb8-237">64</span><span class="sxs-lookup"><span data-stu-id="debb8-237">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="debb8-238">64</span><span class="sxs-lookup"><span data-stu-id="debb8-238">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="debb8-239">64</span><span class="sxs-lookup"><span data-stu-id="debb8-239">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="debb8-240">64</span><span class="sxs-lookup"><span data-stu-id="debb8-240">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="debb8-241">64</span><span class="sxs-lookup"><span data-stu-id="debb8-241">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="debb8-242">32</span><span class="sxs-lookup"><span data-stu-id="debb8-242">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="debb8-243">32</span><span class="sxs-lookup"><span data-stu-id="debb8-243">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |


<span data-ttu-id="debb8-244">I tipi seguenti, essendo puntatori, seguono la larghezza della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="debb8-244">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="debb8-245">Usare `IntPtr`/`UIntPtr` per questi tipi.</span><span class="sxs-lookup"><span data-stu-id="debb8-245">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="debb8-246">Tipi di puntatore con segno (usare `IntPtr`)</span><span class="sxs-lookup"><span data-stu-id="debb8-246">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="debb8-247">Tipi di puntatore senza segno (usare `UIntPtr`)</span><span class="sxs-lookup"><span data-stu-id="debb8-247">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="debb8-248">Per un tipo `PVOID` Windows corrispondente al tipo `void*` C è possibile effettuare il marshalling come `IntPtr` oppure `UIntPtr`, ma preferire `void*` quando possibile.</span><span class="sxs-lookup"><span data-stu-id="debb8-248">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="debb8-249">Tipi di dati di Windows</span><span class="sxs-lookup"><span data-stu-id="debb8-249">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="debb8-250">Intervalli dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="debb8-250">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="debb8-251">Struct</span><span class="sxs-lookup"><span data-stu-id="debb8-251">Structs</span></span>

<span data-ttu-id="debb8-252">Gli struct gestiti vengono creati nello stack e non vengono rimossi fino a quando il metodo non restituisce il controllo.</span><span class="sxs-lookup"><span data-stu-id="debb8-252">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="debb8-253">Per definizione vengono quindi "bloccati" (non verranno spostati dal GC).</span><span class="sxs-lookup"><span data-stu-id="debb8-253">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="debb8-254">È possibile semplicemente accettare l'indirizzo nei blocchi di codice non gestito, se il codice nativo non userà il puntatore oltre la fine del metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="debb8-254">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="debb8-255">Gli struct copiabili da BLT offrono prestazioni molto migliori, perché possono essere semplicemente usati direttamente dal livello di marshalling.</span><span class="sxs-lookup"><span data-stu-id="debb8-255">Blittable structs are much more performant as they can simply be used directly by the marshalling layer.</span></span> <span data-ttu-id="debb8-256">Provare a rendere gli struct copiabili da BLT (ad esempio, evitare `bool`).</span><span class="sxs-lookup"><span data-stu-id="debb8-256">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="debb8-257">Per altre informazioni, vedere la sezione [Tipi copiabili da BLT](#blittable-types).</span><span class="sxs-lookup"><span data-stu-id="debb8-257">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="debb8-258">*Se* lo struct è copiabile da BLT, usare `sizeof()` invece di `Marshal.SizeOf<MyStruct>()` per ottenere prestazioni migliori.</span><span class="sxs-lookup"><span data-stu-id="debb8-258">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="debb8-259">Come indicato in precedenza, è possibile verificare che il tipo sia copiabile da BLT tentando di creare un `GCHandle` bloccato.</span><span class="sxs-lookup"><span data-stu-id="debb8-259">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="debb8-260">Se il tipo non è una stringa o non è considerato copiabile da BLT, `GCHandle.Alloc` genererà una `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="debb8-260">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="debb8-261">I puntatori agli struct nelle definizioni devono essere passati per `ref` oppure usare `unsafe` e `*`.</span><span class="sxs-lookup"><span data-stu-id="debb8-261">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="debb8-262">**✔️ DEFINIRE** lo struct gestito nel modo più possibile corrispondente alla forma e ai nomi usati nella documentazione o nell'intestazione ufficiale della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="debb8-262">**✔️ DO** match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="debb8-263">**✔️ USARE** `sizeof()` di C# invece di `Marshal.SizeOf<MyStruct>()` per le strutture copiabili da BLT per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="debb8-263">**✔️ DO** use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="debb8-264">Ad esempio, è necessario effettuare il marshalling di una matrice come `INT_PTR Reserved1[2]` in due campi `IntPtr`, `Reserved1a` e `Reserved1b`.</span><span class="sxs-lookup"><span data-stu-id="debb8-264">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="debb8-265">Quando la matrice nativa è un tipo primitivo, è possibile usare la parola chiave `fixed` per scriverla in modo un po' più pulito.</span><span class="sxs-lookup"><span data-stu-id="debb8-265">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="debb8-266">Ad esempio, `SYSTEM_PROCESS_INFORMATION` ha un aspetto simile al seguente nell'intestazione nativa:</span><span class="sxs-lookup"><span data-stu-id="debb8-266">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="debb8-267">In C# è possibile scriverla come segue:</span><span class="sxs-lookup"><span data-stu-id="debb8-267">In C#, we can write it like this:</span></span>

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

<span data-ttu-id="debb8-268">Esistono tuttavia alcune complicazioni con i buffer fissi.</span><span class="sxs-lookup"><span data-stu-id="debb8-268">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="debb8-269">I buffer fissi di tipi non copiabili da BLT non verranno correttamente sottoposti a marshalling, quindi la matrice sul posto deve essere espansa in più campi singoli.</span><span class="sxs-lookup"><span data-stu-id="debb8-269">Fixed buffers of non-blittable types won't be correctly marshalled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="debb8-270">Inoltre, in .NET Framework e .NET Core prima della versione 3.0, se uno struct contenente un campo buffer fisso viene annidato all'interno di uno struct non copiabili da BLT, il campo buffer fisso non verrà correttamente sottoposto a marshalling in codice nativo.</span><span class="sxs-lookup"><span data-stu-id="debb8-270">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshalled to native code.</span></span>
