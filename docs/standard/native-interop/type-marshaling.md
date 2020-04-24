---
title: Marshalling dei tipi - .NET
description: Informazioni su come .NET effettua il marshalling dei tipi in una rappresentazione nativa.
ms.date: 01/18/2019
ms.openlocfilehash: 91b8f3d6cb53fd7a0adea7ea9669e7459e81445f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706266"
---
# <a name="type-marshaling"></a><span data-ttu-id="93d53-103">Marshalling dei tipi</span><span class="sxs-lookup"><span data-stu-id="93d53-103">Type marshaling</span></span>

<span data-ttu-id="93d53-104">Il **marshalling** è il processo di trasformazione dei tipi quando questi devono attraversare codice gestito e nativo.</span><span class="sxs-lookup"><span data-stu-id="93d53-104">**Marshaling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="93d53-105">Il marshalling è necessario perché i tipi nel codice gestito e non gestito sono diversi.</span><span class="sxs-lookup"><span data-stu-id="93d53-105">Marshaling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="93d53-106">Nel codice gestito, ad esempio, si dispone di `String`un, mentre nelle stringhe internazionali non gestite può essere Unicode ("wide"), non Unicode, con terminazione null, ASCII e così via. Per impostazione predefinita, il sottosistema P/Invoke tenta di eseguire la corretta operazione in base al comportamento predefinito, descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="93d53-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="93d53-107">Tuttavia, per i casi in cui è necessario un controllo aggiuntivo, è possibile usare l'attributo [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) per specificare il tipo previsto sul lato non gestito.</span><span class="sxs-lookup"><span data-stu-id="93d53-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="93d53-108">Ad esempio, se si vuole che la stringa venga inviata come stringa ANSI con terminazione Null, è possibile usare codice simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="93d53-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a><span data-ttu-id="93d53-109">Regole predefinite per il marshalling dei tipi comuni</span><span class="sxs-lookup"><span data-stu-id="93d53-109">Default rules for marshaling common types</span></span>

<span data-ttu-id="93d53-110">Il runtime tenta in genere di eseguire le operazioni necessarie durante il marshalling in modo da richiedere un intervento minimo da parte dell'utente.</span><span class="sxs-lookup"><span data-stu-id="93d53-110">Generally, the runtime tries to do the "right thing" when marshaling to require the least amount of work from you.</span></span> <span data-ttu-id="93d53-111">Le tabelle seguenti descrivono come viene eseguito, per impostazione predefinita, il marshalling di ogni tipo quando viene usato in un parametro o campo.</span><span class="sxs-lookup"><span data-stu-id="93d53-111">The following tables describe how each type is marshaled by default when used in a parameter or field.</span></span> <span data-ttu-id="93d53-112">I tipi carattere e integer a larghezza fissa C99/C++11 vengono usati per assicurarsi che la tabella seguente sia corretta per tutte le piattaforme.</span><span class="sxs-lookup"><span data-stu-id="93d53-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="93d53-113">È possibile usare qualsiasi tipo nativo con gli stessi requisiti di allineamento e dimensioni di questi tipi.</span><span class="sxs-lookup"><span data-stu-id="93d53-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="93d53-114">La prima tabella descrive i mapping per i vari tipi per i quali il marshalling è lo stesso per P/Invoke e i campi.</span><span class="sxs-lookup"><span data-stu-id="93d53-114">This first table describes the mappings for various types for whom the marshaling is the same for both P/Invoke and field marshaling.</span></span>

| <span data-ttu-id="93d53-115">Tipo di .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-115">.NET Type</span></span> | <span data-ttu-id="93d53-116">Tipo nativo</span><span class="sxs-lookup"><span data-stu-id="93d53-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="93d53-117">`char` oppure `char16_t` a seconda del `CharSet` di P/Invoke o della struttura.</span><span class="sxs-lookup"><span data-stu-id="93d53-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="93d53-118">Vedere la [documentazione sui set di caratteri](charset.md).</span><span class="sxs-lookup"><span data-stu-id="93d53-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="93d53-119">`char*` oppure `char16_t*` a seconda del `CharSet` di P/Invoke o della struttura.</span><span class="sxs-lookup"><span data-stu-id="93d53-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="93d53-120">Vedere la [documentazione sui set di caratteri](charset.md).</span><span class="sxs-lookup"><span data-stu-id="93d53-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="93d53-121">Tipi di puntatore .NET (ad esempio</span><span class="sxs-lookup"><span data-stu-id="93d53-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="93d53-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="93d53-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="93d53-123">Tipo derivato da `System.Runtime.InteropServices.SafeHandle`</span><span class="sxs-lookup"><span data-stu-id="93d53-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="93d53-124">Tipo derivato da `System.Runtime.InteropServices.CriticalHandle`</span><span class="sxs-lookup"><span data-stu-id="93d53-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="93d53-125">Tipo `BOOL` Win32</span><span class="sxs-lookup"><span data-stu-id="93d53-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="93d53-126">Struct `DECIMAL` COM</span><span class="sxs-lookup"><span data-stu-id="93d53-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="93d53-127">Delegato .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-127">.NET Delegate</span></span> | <span data-ttu-id="93d53-128">Puntatore di funzione nativo</span><span class="sxs-lookup"><span data-stu-id="93d53-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="93d53-129">Tipo `DATE` Win32</span><span class="sxs-lookup"><span data-stu-id="93d53-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="93d53-130">Tipo `GUID` Win32</span><span class="sxs-lookup"><span data-stu-id="93d53-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="93d53-131">Alcune categorie di marshalling hanno impostazioni predefinite diverse a seconda che si stia eseguendo il marshalling come parametro o struttura.</span><span class="sxs-lookup"><span data-stu-id="93d53-131">A few categories of marshaling have different defaults if you're marshaling as a parameter or structure.</span></span>

| <span data-ttu-id="93d53-132">Tipo di .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-132">.NET Type</span></span> | <span data-ttu-id="93d53-133">Tipo nativo (parametro)</span><span class="sxs-lookup"><span data-stu-id="93d53-133">Native Type (Parameter)</span></span> | <span data-ttu-id="93d53-134">Tipo nativo (campo)</span><span class="sxs-lookup"><span data-stu-id="93d53-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="93d53-135">Matrice .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-135">.NET array</span></span> | <span data-ttu-id="93d53-136">Un puntatore all'inizio della matrice delle rappresentazioni native degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="93d53-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="93d53-137">Non consentito senza un attributo `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="93d53-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="93d53-138">Una classe con `LayoutKind``Sequential` o `Explicit`</span><span class="sxs-lookup"><span data-stu-id="93d53-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="93d53-139">Un puntatore alla rappresentazione nativa della classe</span><span class="sxs-lookup"><span data-stu-id="93d53-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="93d53-140">La rappresentazione nativa della classe</span><span class="sxs-lookup"><span data-stu-id="93d53-140">The native representation of the class</span></span> |

<span data-ttu-id="93d53-141">La tabella seguente include regole di marshalling predefinite valide solo per Windows.</span><span class="sxs-lookup"><span data-stu-id="93d53-141">The following table includes the default marshaling rules that are Windows-only.</span></span> <span data-ttu-id="93d53-142">Nelle piattaforme non Windows non è possibile effettuare il marshalling di questi tipi.</span><span class="sxs-lookup"><span data-stu-id="93d53-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="93d53-143">Tipo di .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-143">.NET Type</span></span> | <span data-ttu-id="93d53-144">Tipo nativo (parametro)</span><span class="sxs-lookup"><span data-stu-id="93d53-144">Native Type (Parameter)</span></span> | <span data-ttu-id="93d53-145">Tipo nativo (campo)</span><span class="sxs-lookup"><span data-stu-id="93d53-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="93d53-146">Interfaccia COM</span><span class="sxs-lookup"><span data-stu-id="93d53-146">COM interface</span></span> | <span data-ttu-id="93d53-147">Non consentito senza un attributo `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="93d53-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="93d53-148">Non consentito</span><span class="sxs-lookup"><span data-stu-id="93d53-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="93d53-149">Non consentito</span><span class="sxs-lookup"><span data-stu-id="93d53-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="93d53-150">Non consentito</span><span class="sxs-lookup"><span data-stu-id="93d53-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="93d53-151">`int64_t` che rappresenta il numero di tick dalla mezzanotte del 1° gennaio 1601</span><span class="sxs-lookup"><span data-stu-id="93d53-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="93d53-152">`int64_t` che rappresenta il numero di tick dalla mezzanotte del 1° gennaio 1601</span><span class="sxs-lookup"><span data-stu-id="93d53-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="93d53-153">Di alcuni tipi è possibile eseguire il marshalling solo come parametri e non come campi.</span><span class="sxs-lookup"><span data-stu-id="93d53-153">Some types can only be marshaled as parameters and not as fields.</span></span> <span data-ttu-id="93d53-154">Questi tipi sono elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="93d53-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="93d53-155">Tipo di .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-155">.NET Type</span></span> | <span data-ttu-id="93d53-156">Tipo nativo (solo parametro)</span><span class="sxs-lookup"><span data-stu-id="93d53-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="93d53-157">`char*` oppure `char16_t*` a seconda del `CharSet` di P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="93d53-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="93d53-158">Vedere la [documentazione sui set di caratteri](charset.md).</span><span class="sxs-lookup"><span data-stu-id="93d53-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="93d53-159">`va_list` (solo in Windows x86/x64/arm64)</span><span class="sxs-lookup"><span data-stu-id="93d53-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="93d53-160">Se queste impostazioni predefinite non producono esattamente il risultato desiderato, è possibile personalizzare la modalità di marshalling dei parametri.</span><span class="sxs-lookup"><span data-stu-id="93d53-160">If these defaults don't do exactly what you want, you can customize how parameters are marshaled.</span></span> <span data-ttu-id="93d53-161">L'articolo sul [marshalling dei parametri](customize-parameter-marshaling.md) illustra come personalizzare la modalità di marshalling dei diversi tipi di parametri.</span><span class="sxs-lookup"><span data-stu-id="93d53-161">The [parameter marshaling](customize-parameter-marshaling.md) article walks you through how to customize how different parameter types are marshaled.</span></span>

## <a name="default-marshaling-in-com-scenarios"></a><span data-ttu-id="93d53-162">Marshalling predefinito in scenari COM</span><span class="sxs-lookup"><span data-stu-id="93d53-162">Default marshaling in COM scenarios</span></span>

<span data-ttu-id="93d53-163">Quando si chiama un metodo su oggetti COM in .NET, il runtime di .NET cambia le regole del marshalling predefinito in modo da rispettare la semantica COM.</span><span class="sxs-lookup"><span data-stu-id="93d53-163">When you are calling methods on COM objects in .NET, the .NET runtime changes the default marshaling rules to match common COM semantics.</span></span> <span data-ttu-id="93d53-164">Nella tabella seguente sono elencate le regole che i runtime .NET usano negli scenari COM:</span><span class="sxs-lookup"><span data-stu-id="93d53-164">The following table lists the rules that .NET runtimes uses in COM scenarios:</span></span>

| <span data-ttu-id="93d53-165">Tipo di .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-165">.NET Type</span></span> | <span data-ttu-id="93d53-166">Tipo nativo (chiamate al metodo COM)</span><span class="sxs-lookup"><span data-stu-id="93d53-166">Native Type (COM method calls)</span></span> |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| <span data-ttu-id="93d53-167">Tipi delegato</span><span class="sxs-lookup"><span data-stu-id="93d53-167">Delegate types</span></span> | <span data-ttu-id="93d53-168">`_Delegate*` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="93d53-168">`_Delegate*` in .NET Framework.</span></span> <span data-ttu-id="93d53-169">Non consentito in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="93d53-169">Disallowed in .NET Core.</span></span> |
| `System.Drawing.Color` | `OLECOLOR`        |
| <span data-ttu-id="93d53-170">Matrice .NET</span><span class="sxs-lookup"><span data-stu-id="93d53-170">.NET array</span></span> | `SAFEARRAY`                   |
| `string[]` | <span data-ttu-id="93d53-171">`SAFEARRAY` di `BSTR`</span><span class="sxs-lookup"><span data-stu-id="93d53-171">`SAFEARRAY` of `BSTR`s</span></span>        |

## <a name="marshaling-classes-and-structs"></a><span data-ttu-id="93d53-172">Marshalling di classi e struct</span><span class="sxs-lookup"><span data-stu-id="93d53-172">Marshaling classes and structs</span></span>

<span data-ttu-id="93d53-173">Un altro aspetto del marshalling dei tipi riguarda il modo in cui uno struct viene passato a un metodo non gestito.</span><span class="sxs-lookup"><span data-stu-id="93d53-173">Another aspect of type marshaling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="93d53-174">Ad esempio, alcuni dei metodi non gestiti richiedono una struttura come parametro.</span><span class="sxs-lookup"><span data-stu-id="93d53-174">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="93d53-175">In questi casi, è necessario creare una classe o uno struct corrispondente nella parte gestita per usarlo come parametro.</span><span class="sxs-lookup"><span data-stu-id="93d53-175">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="93d53-176">La semplice definizione della classe, tuttavia, non è sufficiente. È necessario anche indicare al gestore di marshalling come eseguire il mapping dei campi della classe allo struct non gestito.</span><span class="sxs-lookup"><span data-stu-id="93d53-176">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="93d53-177">In questo caso diventa utile l'attributo `StructLayout`.</span><span class="sxs-lookup"><span data-stu-id="93d53-177">Here the `StructLayout` attribute becomes useful.</span></span>

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

<span data-ttu-id="93d53-178">Il codice precedente illustra un semplice esempio di chiamata della funzione `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="93d53-178">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="93d53-179">La parte interessante è alla riga 4.</span><span class="sxs-lookup"><span data-stu-id="93d53-179">The interesting bit is on line 4.</span></span> <span data-ttu-id="93d53-180">L'attributo specifica che i campi della classe devono essere mappati in modo sequenziale allo struct sull'altro lato (non gestito).</span><span class="sxs-lookup"><span data-stu-id="93d53-180">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="93d53-181">Questo significa che i nomi dei campi non sono rilevanti, ma che è importante solo l'ordine. È infatti necessario che i campi corrispondano allo struct non gestito, come mostrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="93d53-181">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

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
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="93d53-182">In alcuni casi il marshalling predefinito per la struttura non produce i risultati previsti.</span><span class="sxs-lookup"><span data-stu-id="93d53-182">Sometimes the default marshaling for your structure doesn't do what you need.</span></span> <span data-ttu-id="93d53-183">L'articolo [Personalizzazione del marshalling delle strutture](./customize-struct-marshaling.md) illustra come personalizzare la modalità di marshalling della struttura.</span><span class="sxs-lookup"><span data-stu-id="93d53-183">The [Customizing structure marshaling](./customize-struct-marshaling.md) article teaches you how to customize how your structure is marshaled.</span></span>
