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
# <a name="type-marshaling"></a>Marshalling dei tipi

Il **marshalling** è il processo di trasformazione dei tipi quando questi devono attraversare codice gestito e nativo.

Il marshalling è necessario perché i tipi nel codice gestito e non gestito sono diversi. Nel codice gestito, ad esempio, si dispone di un `String`, mentre nelle stringhe internazionali non gestite possono essere Unicode ("wide"), non Unicode, con terminazione null, ASCII e così via. Per impostazione predefinita, il sottosistema P/Invoke tenta di eseguire la corretta operazione in base al comportamento predefinito, descritto in questo articolo. Tuttavia, per i casi in cui è necessario un controllo aggiuntivo, è possibile usare l'attributo [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) per specificare il tipo previsto sul lato non gestito. Ad esempio, se si vuole che la stringa venga inviata come stringa ANSI con terminazione Null, è possibile usare codice simile al seguente:

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a>Regole predefinite per il marshalling dei tipi comuni

Il runtime tenta in genere di eseguire le operazioni necessarie durante il marshalling in modo da richiedere un intervento minimo da parte dell'utente. Le tabelle seguenti descrivono come viene eseguito, per impostazione predefinita, il marshalling di ogni tipo quando viene usato in un parametro o campo. I tipi carattere e integer a larghezza fissa C99/C++11 vengono usati per assicurarsi che la tabella seguente sia corretta per tutte le piattaforme. È possibile usare qualsiasi tipo nativo con gli stessi requisiti di allineamento e dimensioni di questi tipi.

La prima tabella descrive i mapping per i vari tipi per i quali il marshalling è lo stesso per P/Invoke e i campi.

| Tipo .NET | Tipo nativo  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | `char` oppure `char16_t` a seconda del `CharSet` di P/Invoke o della struttura. Vedere la [documentazione sui set di caratteri](charset.md). |
| `string`  | `char*` oppure `char16_t*` a seconda del `CharSet` di P/Invoke o della struttura. Vedere la [documentazione sui set di caratteri](charset.md). |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| Tipi di puntatore .NET (ad esempio `void*`)  | `void*` |
| Tipo derivato da `System.Runtime.InteropServices.SafeHandle` | `void*` |
| Tipo derivato da `System.Runtime.InteropServices.CriticalHandle` | `void*`          |
| `bool`    | Tipo `BOOL` Win32       |
| `decimal` | Struct `DECIMAL` COM |
| Delegato .NET | Puntatore di funzione nativo |
| `System.DateTime` | Tipo `DATE` Win32 |
| `System.Guid` | Tipo `GUID` Win32 |

Alcune categorie di marshalling hanno impostazioni predefinite diverse a seconda che si stia eseguendo il marshalling come parametro o struttura.

| Tipo .NET | Tipo nativo (parametro) | Tipo nativo (campo) |
|-----------|-------------------------|---------------------|
| Matrice .NET | Un puntatore all'inizio della matrice delle rappresentazioni native degli elementi della matrice. | Non consentito senza un attributo `[MarshalAs]`|
| Una classe con `LayoutKind``Sequential` o `Explicit` | Un puntatore alla rappresentazione nativa della classe | La rappresentazione nativa della classe |

La tabella seguente include regole di marshalling predefinite valide solo per Windows. Nelle piattaforme non Windows non è possibile effettuare il marshalling di questi tipi.

| Tipo .NET | Tipo nativo (parametro) | Tipo nativo (campo) |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | Interfaccia COM | Non consentito senza un attributo `[MarshalAs]` |
| `System.ArgIterator` | `va_list` | Non consentito |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | Non consentito |
| `System.Collections.IEnumerable` | `IDispatch*` | Non consentito |
| `System.DateTimeOffset` | `int64_t` che rappresenta il numero di tick dalla mezzanotte del 1° gennaio 1601 || `int64_t` che rappresenta il numero di tick dalla mezzanotte del 1° gennaio 1601 |

Di alcuni tipi è possibile eseguire il marshalling solo come parametri e non come campi. Questi tipi sono elencati nella tabella seguente:

| Tipo .NET | Tipo nativo (solo parametro) |
|-----------|------------------------------|
| `System.Text.StringBuilder` | `char*` oppure `char16_t*` a seconda del `CharSet` di P/Invoke.  Vedere la [documentazione sui set di caratteri](charset.md). |
| `System.ArgIterator` | `va_list` (solo in Windows x86/x64/arm64) |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

Se queste impostazioni predefinite non producono esattamente il risultato desiderato, è possibile personalizzare la modalità di marshalling dei parametri. L'articolo sul [marshalling dei parametri](customize-parameter-marshaling.md) illustra come personalizzare la modalità di marshalling dei diversi tipi di parametri.

## <a name="default-marshaling-in-com-scenarios"></a>Marshalling predefinito in scenari COM

Quando si chiama un metodo su oggetti COM in .NET, il runtime di .NET cambia le regole del marshalling predefinito in modo da rispettare la semantica COM. Nella tabella seguente sono elencate le regole che i runtime .NET usano negli scenari COM:

| Tipo .NET | Tipo nativo (chiamate al metodo COM) |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| Tipi delegato | `_Delegate*` in .NET Framework. Non consentito in .NET Core. |
| `System.Drawing.Color` | `OLECOLOR`        |
| Matrice .NET | `SAFEARRAY`                   |
| `string[]` | `SAFEARRAY` di `BSTR`        |

## <a name="marshaling-classes-and-structs"></a>Marshalling di classi e struct

Un altro aspetto del marshalling dei tipi riguarda il modo in cui uno struct viene passato a un metodo non gestito. Ad esempio, alcuni dei metodi non gestiti richiedono una struttura come parametro. In questi casi, è necessario creare una classe o uno struct corrispondente nella parte gestita per usarlo come parametro. La semplice definizione della classe, tuttavia, non è sufficiente. È necessario anche indicare al gestore di marshalling come eseguire il mapping dei campi della classe allo struct non gestito. In questo caso diventa utile l'attributo `StructLayout`.

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

Il codice precedente illustra un semplice esempio di chiamata della funzione `GetSystemTime()`. La parte interessante è alla riga 4. L'attributo specifica che i campi della classe devono essere mappati in modo sequenziale allo struct sull'altro lato (non gestito). Questo significa che i nomi dei campi non sono rilevanti, ma che è importante solo l'ordine. È infatti necessario che i campi corrispondano allo struct non gestito, come mostrato nell'esempio seguente:

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

In alcuni casi il marshalling predefinito per la struttura non produce i risultati previsti. L'articolo [Personalizzazione del marshalling delle strutture](./customize-struct-marshaling.md) illustra come personalizzare la modalità di marshalling della struttura.
