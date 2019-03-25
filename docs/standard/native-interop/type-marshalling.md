---
title: Marshalling dei tipi - .NET
description: Informazioni su come .NET effettua il marshalling dei tipi in una rappresentazione nativa.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: b4846f2e6cd945a25ec6a747c9038d48fe115559
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185415"
---
# <a name="type-marshalling"></a><span data-ttu-id="8e5c1-103">Marshalling dei tipi</span><span class="sxs-lookup"><span data-stu-id="8e5c1-103">Type marshalling</span></span>

<span data-ttu-id="8e5c1-104">Il termine **marshalling** indica il processo di trasformazione dei tipi quando questi devono passare dal codice gestito a quello nativo e viceversa.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-104">**Marshalling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="8e5c1-105">Il marshalling è necessario perché i tipi presenti nel codice gestito e quelli presenti nel codice non gestito sono differenti.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-105">Marshalling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="8e5c1-106">Nel codice gestito, ad esempio, si ha un elemento `String`, mentre nell'ambiente non gestito le stringhe possono essere Unicode ("wide"), non Unicode, con terminazione null, ASCII, e così via. Per impostazione predefinita, il sottosistema di P/Invoke tenta di eseguire le operazioni necessarie in base al comportamento predefinito, descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="8e5c1-107">Tuttavia, per i casi in cui è necessario un controllo aggiuntivo, è possibile usare l'attributo [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) per specificare il tipo previsto sul lato non gestito.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="8e5c1-108">Ad esempio, se si vuole che la stringa venga inviata come stringa ANSI con terminazione Null, è possibile usare codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8e5c1-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshalling-common-types"></a><span data-ttu-id="8e5c1-109">Regole predefinite per il marshalling dei tipi comuni</span><span class="sxs-lookup"><span data-stu-id="8e5c1-109">Default rules for marshalling common types</span></span>

<span data-ttu-id="8e5c1-110">In genere, il runtime tenta di eseguire la "cosa giusta" quando effettua il marshalling, in modo da richiedere un intervento minimo da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-110">Generally, the runtime tries to do the "right thing" when marshalling to require the least amount of work from you.</span></span> <span data-ttu-id="8e5c1-111">Le tabelle seguenti descrivono come viene effettuato il marshalling di ogni tipo per impostazione predefinita, quando viene usato in un parametro o un campo.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-111">The following tables describe how each type is marshalled by default when used in a parameter or field.</span></span> <span data-ttu-id="8e5c1-112">I tipi carattere e integer a larghezza fissa C99/C++11 vengono usati per assicurarsi che la tabella seguente sia corretta per tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="8e5c1-113">È possibile usare qualsiasi tipo nativo con gli stessi requisiti di allineamento e dimensioni di questi tipi.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="8e5c1-114">La prima tabella descrive i mapping per i vari tipi per i quali il marshalling è lo stesso sia per P/Invoke che per i campi.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-114">This first table describes the mappings for various types for whom the marshalling is the same for both P/Invoke and field marshalling.</span></span>

| <span data-ttu-id="8e5c1-115">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="8e5c1-115">.NET Type</span></span> | <span data-ttu-id="8e5c1-116">Tipo nativo</span><span class="sxs-lookup"><span data-stu-id="8e5c1-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="8e5c1-117">`char` oppure `char16_t` a seconda del `CharSet` di P/Invoke o della struttura.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="8e5c1-118">Vedere la [documentazione sui set di caratteri](charset.md).</span><span class="sxs-lookup"><span data-stu-id="8e5c1-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="8e5c1-119">`char*` oppure `char16_t*` a seconda del `CharSet` di P/Invoke o della struttura.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="8e5c1-120">Vedere la [documentazione sui set di caratteri](charset.md).</span><span class="sxs-lookup"><span data-stu-id="8e5c1-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="8e5c1-121">Tipi di puntatore .NET (ad esempio</span><span class="sxs-lookup"><span data-stu-id="8e5c1-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="8e5c1-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="8e5c1-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="8e5c1-123">Tipo derivato da `System.Runtime.InteropServices.SafeHandle`</span><span class="sxs-lookup"><span data-stu-id="8e5c1-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="8e5c1-124">Tipo derivato da `System.Runtime.InteropServices.CriticalHandle`</span><span class="sxs-lookup"><span data-stu-id="8e5c1-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="8e5c1-125">Tipo `BOOL` Win32</span><span class="sxs-lookup"><span data-stu-id="8e5c1-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="8e5c1-126">Struct `DECIMAL` COM</span><span class="sxs-lookup"><span data-stu-id="8e5c1-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="8e5c1-127">Delegato .NET</span><span class="sxs-lookup"><span data-stu-id="8e5c1-127">.NET Delegate</span></span> | <span data-ttu-id="8e5c1-128">Puntatore di funzione nativo</span><span class="sxs-lookup"><span data-stu-id="8e5c1-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="8e5c1-129">Tipo `DATE` Win32</span><span class="sxs-lookup"><span data-stu-id="8e5c1-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="8e5c1-130">Tipo `GUID` Win32</span><span class="sxs-lookup"><span data-stu-id="8e5c1-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="8e5c1-131">Alcune categorie di marshalling hanno impostazioni predefinite diverse se si effettua il marshalling come parametro o come struttura.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-131">A few categories of marshalling have different defaults if you're marshalling as a parameter or structure.</span></span>

| <span data-ttu-id="8e5c1-132">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="8e5c1-132">.NET Type</span></span> | <span data-ttu-id="8e5c1-133">Tipo nativo (parametro)</span><span class="sxs-lookup"><span data-stu-id="8e5c1-133">Native Type (Parameter)</span></span> | <span data-ttu-id="8e5c1-134">Tipo nativo (campo)</span><span class="sxs-lookup"><span data-stu-id="8e5c1-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="8e5c1-135">Matrice .NET</span><span class="sxs-lookup"><span data-stu-id="8e5c1-135">.NET array</span></span> | <span data-ttu-id="8e5c1-136">Un puntatore all'inizio della matrice delle rappresentazioni native degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="8e5c1-137">Non consentito senza un attributo `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="8e5c1-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="8e5c1-138">Una classe con `LayoutKind` `Sequential` o `Explicit`</span><span class="sxs-lookup"><span data-stu-id="8e5c1-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="8e5c1-139">Un puntatore alla rappresentazione nativa della classe</span><span class="sxs-lookup"><span data-stu-id="8e5c1-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="8e5c1-140">La rappresentazione nativa della classe</span><span class="sxs-lookup"><span data-stu-id="8e5c1-140">The native representation of the class</span></span> |

<span data-ttu-id="8e5c1-141">La tabella seguente include le regole di marshalling predefinite solo per Windows.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-141">The following table includes the default marshalling rules that are Windows-only.</span></span> <span data-ttu-id="8e5c1-142">Nelle piattaforme non Windows non è possibile effettuare il marshalling di questi tipi.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="8e5c1-143">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="8e5c1-143">.NET Type</span></span> | <span data-ttu-id="8e5c1-144">Tipo nativo (parametro)</span><span class="sxs-lookup"><span data-stu-id="8e5c1-144">Native Type (Parameter)</span></span> | <span data-ttu-id="8e5c1-145">Tipo nativo (campo)</span><span class="sxs-lookup"><span data-stu-id="8e5c1-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="8e5c1-146">Interfaccia COM</span><span class="sxs-lookup"><span data-stu-id="8e5c1-146">COM interface</span></span> | <span data-ttu-id="8e5c1-147">Non consentito senza un attributo `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="8e5c1-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="8e5c1-148">Non consentito</span><span class="sxs-lookup"><span data-stu-id="8e5c1-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="8e5c1-149">Non consentito</span><span class="sxs-lookup"><span data-stu-id="8e5c1-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="8e5c1-150">Non consentito</span><span class="sxs-lookup"><span data-stu-id="8e5c1-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="8e5c1-151">`int64_t` che rappresenta il numero di tick dalla mezzanotte del 1° gennaio 1601</span><span class="sxs-lookup"><span data-stu-id="8e5c1-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="8e5c1-152">`int64_t` che rappresenta il numero di tick dalla mezzanotte del 1° gennaio 1601</span><span class="sxs-lookup"><span data-stu-id="8e5c1-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="8e5c1-153">Per alcuni tipi è possibile effettuare il marshalling solo come parametri e non come campi.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-153">Some types can only be marshalled as parameters and not as fields.</span></span> <span data-ttu-id="8e5c1-154">Questi tipi sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="8e5c1-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="8e5c1-155">Tipo .NET</span><span class="sxs-lookup"><span data-stu-id="8e5c1-155">.NET Type</span></span> | <span data-ttu-id="8e5c1-156">Tipo nativo (solo parametro)</span><span class="sxs-lookup"><span data-stu-id="8e5c1-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="8e5c1-157">`char*` oppure `char16_t*` a seconda del `CharSet` di P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="8e5c1-158">Vedere la [documentazione sui set di caratteri](charset.md).</span><span class="sxs-lookup"><span data-stu-id="8e5c1-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="8e5c1-159">`va_list` (solo in Windows x86/x64/arm64)</span><span class="sxs-lookup"><span data-stu-id="8e5c1-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="8e5c1-160">Se queste impostazioni predefinite non producono esattamente il risultato desiderato, è possibile personalizzare la modalità di marshalling dei parametri.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-160">If these defaults don't do exactly what you want, you can customize how parameters are marshalled.</span></span> <span data-ttu-id="8e5c1-161">L'articolo dedicato al [marshalling dei parametri](customize-parameter-marshalling.md) illustra in modo dettagliato come personalizzare la modalità di marshalling dei diversi tipi di parametri.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-161">The [parameter marshalling](customize-parameter-marshalling.md) article walks you through how to customize how different parameter types are marshalled.</span></span>

## <a name="marshalling-classes-and-structs"></a><span data-ttu-id="8e5c1-162">Marshalling di classi e strutture</span><span class="sxs-lookup"><span data-stu-id="8e5c1-162">Marshalling classes and structs</span></span>

<span data-ttu-id="8e5c1-163">Un altro aspetto del marshalling dei tipi è il modo in cui è possibile passare una struttura a un metodo non gestito.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-163">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="8e5c1-164">Ad esempio, alcuni dei metodi non gestiti richiedono una struttura come parametro.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-164">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="8e5c1-165">In questi casi, è necessario creare una classe o uno struct corrispondente nella parte gestita per usarlo come parametro.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-165">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="8e5c1-166">La semplice definizione della classe, tuttavia, non è sufficiente. È necessario anche indicare al gestore di marshalling come eseguire il mapping dei campi della classe allo struct non gestito.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-166">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="8e5c1-167">In questo caso diventa utile l'attributo `StructLayout`.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-167">Here the `StructLayout` attribute becomes useful.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="8e5c1-168">Il codice precedente illustra un semplice esempio di chiamata della funzione `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-168">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="8e5c1-169">La parte interessante è alla riga 4.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-169">The interesting bit is on line 4.</span></span> <span data-ttu-id="8e5c1-170">L'attributo specifica che i campi della classe devono essere mappati in modo sequenziale allo struct sull'altro lato (non gestito).</span><span class="sxs-lookup"><span data-stu-id="8e5c1-170">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="8e5c1-171">Questo significa che i nomi dei campi non sono rilevanti, ma che è importante solo l'ordine. È infatti necessario che i campi corrispondano allo struct non gestito, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="8e5c1-171">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

<span data-ttu-id="8e5c1-172">In alcuni casi il marshalling predefinito per la struttura non produce i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-172">Sometimes the default marshalling for your structure doesn't do what you need.</span></span> <span data-ttu-id="8e5c1-173">L'articolo [Personalizzazione del marshalling delle strutture](./customize-struct-marshalling.md) illustra come personalizzare la modalità di marshalling della struttura.</span><span class="sxs-lookup"><span data-stu-id="8e5c1-173">The [Customizing structure marshalling](./customize-struct-marshalling.md) article teaches you how to customize how your structure is marshaled.</span></span>
