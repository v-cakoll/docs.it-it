---
title: Personalizzazione del marshalling delle strutture - .NET
description: Informazioni su come personalizzare il modo in cui .NET esegue il marshalling delle strutture a una rappresentazione nativa.
ms.date: 01/18/2019
dev_langs:
- csharp
- cpp
ms.openlocfilehash: c82e0099c44b8033cad241d69bdd284243711a50
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374533"
---
# <a name="customize-structure-marshaling"></a>Personalizzare il marshalling delle strutture

In alcuni casi le regole di marshalling predefinite per le strutture non sono esattamente quelle necessarie. I runtime .NET offrono alcuni punti di estensione per poter personalizzare il layout della struttura e la modalità di marshalling dei campi.

## <a name="customizing-structure-layout"></a>Personalizzazione del layout della struttura

.NET offre l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> e l'enumerazione <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType> per consentire di personalizzare il modo in cui i campi vengono inseriti nella memoria. Le linee guida seguenti saranno utili per evitare problemi comuni.

✔️ PRENDERE IN CONSIDERAZIONE l'uso di `LayoutKind.Sequential` laddove possibile.

✔️ utilizzare solo `LayoutKind.Explicit` nel marshalling quando lo struct nativo dispone anche di un layout esplicito, ad esempio un'Unione.

❌EVITARE `LayoutKind.Explicit` di usare quando si esegue il marshalling di strutture su piattaforme non Windows se è necessario destinare i runtime prima di .NET Core 3,0. Il runtime di .NET Core prima del 3,0 non supporta il passaggio di strutture esplicite per valore a funzioni native su sistemi non Windows Intel o AMD a 64 bit. Tuttavia, il runtime supporta il passaggio di strutture esplicite per riferimento in tutte le piattaforme.

## <a name="customizing-boolean-field-marshaling"></a>Personalizzazione del marshalling di campi booleani

Il codice nativo include molte rappresentazioni booleane diverse. Solo in Windows esistono tre modi per rappresentare valori booleani. Il runtime non conosce la definizione nativa della struttura, quindi può al massimo fare supposizioni su come effettuare il marshalling dei valori booleani. Il runtime .NET offre un modo per indicare come effettuare il marshalling del campo booleano. Gli esempi seguenti illustrano come eseguire il marshalling del tipo `bool` .NET in diversi tipi booleani nativi.

Per impostazione predefinita, i valori booleani eseguono il marshalling come valore Win32 nativo a 4 byte [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL) , come illustrato nell'esempio seguente:

```csharp
public struct WinBool
{
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

Se si vuole essere espliciti, è possibile usare il valore <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> per ottenere lo stesso comportamento illustrato in precedenza:

```csharp
public struct WinBool
{
    [MarshalAs(UnmanagedType.Bool)]
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

Usando i valori `UnmanagedType.U1` o `UnmanagedType.I1` di seguito, è possibile indicare al runtime di effettuare il marshalling del campo `b` come tipo `bool` nativo a 1 byte.

```csharp
public struct CBool
{
    [MarshalAs(UnmanagedType.U1)]
    public bool b;
}
```

```cpp
struct CBool
{
    public bool b;
};
```

In Windows, è possibile usare il valore <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> per indicare al runtime di effettuare il marshalling del valore booleano in un valore `VARIANT_BOOL` a 2 byte:

```csharp
public struct VariantBool
{
    [MarshalAs(UnmanagedType.VariantBool)]
    public bool b;
}
```

```cpp
struct VariantBool
{
    public VARIANT_BOOL b;
};
```

> [!NOTE]
> `VARIANT_BOOL` è diverso dalla maggior parte dei tipi bool in quanto `VARIANT_TRUE = -1` e `VARIANT_FALSE = 0`. Inoltre, tutti i valori che non sono uguali a `VARIANT_TRUE` sono considerati false.

## <a name="customizing-array-field-marshaling"></a>Personalizzazione del marshalling delle matrici

.NET include anche alcuni modi per personalizzare il marshalling delle matrici.

Per impostazione predefinita, .NET effettua il marshalling delle matrici come puntatore a un elenco di elementi contigui:

```csharp
public struct DefaultArray
{
    public int[] values;
}
```

```cpp
struct DefaultArray
{
    int* values;
};
```

Per interfacciarsi con le API COM, potrebbe essere necessario effettuare il marshalling delle matrici come oggetti `SAFEARRAY*`. È possibile usare <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> e il valore <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> per indicare al runtime di effettuare il marshalling di una matrice come `SAFEARRAY*`:

```csharp
public struct SafeArrayExample
{
    [MarshalAs(UnmanagedType.SafeArray)]
    public int[] values;
}
```

```cpp
struct SafeArrayExample
{
    SAFEARRAY* values;
};
```

Se è necessario personalizzare il tipo di elemento presente in `SAFEARRAY`, è possibile usare i campi <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> e <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> per personalizzare il tipo di elemento esatto di `SAFEARRAY`.

Se è necessario effettuare il marshalling della matrice sul posto, è possibile usare il valore <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> per indicare al gestore di marshalling di effettuare il marshalling della matrice sul posto. Quando si usa questo tipo di marshalling, è anche necessario fornire un valore al campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> per il numero di elementi nella matrice, in modo che il runtime possa allocare correttamente spazio per la struttura.

```csharp
public struct InPlaceArray
{
    [MarshalAs(UnmanagedType.ByValArray, SizeConst = 4)]
    public int[] values;
}
```

```cpp
struct InPlaceArray
{
    int values[4];
};
```

> [!NOTE]
> .NET non supporta il marshalling di un campo di matrice di lunghezza variabile come membro di matrice flessibile C99.

## <a name="customizing-string-field-marshaling"></a>Personalizzazione del marshalling dei campi stringa

.NET offre anche un'ampia gamma di personalizzazioni per il marshalling dei campi stringa.

Per impostazione predefinita, .NET effettua il marshalling di una stringa come un puntatore a una stringa con terminazione Null. La codifica dipende dal valore del campo <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> in <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>. Se non viene specificato alcun attributo, viene usata la codifica predefinita ANSI.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char* str;
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

Se è necessario usare codifiche differenti per campi diversi oppure semplicemente si preferisce essere più espliciti nella definizione dello struct, è possibile usare i valori <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> per un attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>.

```csharp
public struct AnsiString
{
    [MarshalAs(UnmanagedType.LPStr)]
    public string str;
}
```

```cpp
struct AnsiString
{
    char* str;
};
```

```csharp
public struct UnicodeString
{
    [MarshalAs(UnmanagedType.LPWStr)]
    public string str;
}
```

```cpp
struct UnicodeString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

Se si vuole effettuare il marshalling delle stringhe con la codifica UTF-8, è possibile usare il valore <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> in <xref:System.Runtime.InteropServices.MarshalAsAttribute>.

```csharp
public struct UTF8String
{
    [MarshalAs(UnmanagedType.LPUTF8Str)]
    public string str;
}
```

```cpp
struct UTF8String
{
    char* str;
};
```

> [!NOTE]
> L'uso di <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> richiede .NET Framework 4.7 (o versioni successive) o .NET Core 1.1 (o versioni successive). Non è disponibile in .NET Standard 2.0.

Se si utilizzano API COM, potrebbe essere necessario effettuare il marshalling di una stringa come `BSTR`. Usando il valore <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> è possibile effettuare il marshalling di una stringa come `BSTR`.

```csharp
public struct BString
{
    [MarshalAs(UnmanagedType.BStr)]
    public string str;
}
```

```cpp
struct BString
{
    BSTR str;
};
```

Quando si usa un'API basata su WinRT, potrebbe essere necessario effettuare il marshalling di una stringa come `HSTRING`. Usando il valore <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> è possibile effettuare il marshalling di una stringa come `HSTRING`.

```csharp
public struct HString
{
    [MarshalAs(UnmanagedType.HString)]
    public string str;
}
```

```cpp
struct BString
{
    HSTRING str;
};
```

Se l'API richiede di passare la stringa sul posto nella struttura, è possibile usare il valore <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType>. Si noti che la codifica per una stringa sottoposta a marshalling con `ByValTStr` è determinata dall'attributo `CharSet`. È inoltre richiesto il passaggio della lunghezza della stringa con il campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType>.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char str[4];
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t str[4]; // Could also be wchar_t[4] on Windows.
};
```

## <a name="customizing-decimal-field-marshaling"></a>Personalizzazione del marshalling dei campi decimali

Se si lavora su Windows, è possibile che si verifichino alcune API che usano il nativo [ `CY` o `CURRENCY` ](/windows/win32/api/wtypes/ns-wtypes-cy-r1) la struttura. Per impostazione predefinita, il tipo .NET esegue il `decimal` marshalling sulla [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal-r1) struttura nativa. Tuttavia, è possibile usare un <xref:System.Runtime.InteropServices.MarshalAsAttribute> con il valore <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> per indicare al gestore di marshalling di convertire un valore `decimal` in un valore `CY` nativo.

```csharp
public struct Currency
{
    [MarshalAs(UnmanagedType.Currency)]
    public decimal dec;
}
```

```cpp
struct Currency
{
    CY dec;
};
```

## <a name="marshal-systemobject"></a>Marshal`System.Object`

In Windows è possibile effettuare il marshalling di campi di tipo `object` in codice nativo. È possibile effettuare il marshalling di questi campi in uno di tre tipi:

- [`VARIANT`](/windows/win32/api/oaidl/ns-oaidl-variant)
- [`IUnknown*`](/windows/desktop/api/unknwn/nn-unknwn-iunknown)
- [`IDispatch*`](/windows/desktop/api/oaidl/nn-oaidl-idispatch)

Per impostazione predefinita, un campo di tipo `object` verrà sottoposto a marshalling come `IUnknown*` che esegue il wrapping dell'oggetto.

```csharp
public struct ObjectDefault
{
    public object obj;
}
```

```cpp
struct ObjectDefault
{
    IUnknown* obj;
};
```

Se si vuole effettuare il marshalling di un campo oggetto come `IDispatch*`, aggiungere un <xref:System.Runtime.InteropServices.MarshalAsAttribute> con il valore <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>.

```csharp
public struct ObjectDispatch
{
    [MarshalAs(UnmanagedType.IDispatch)]
    public object obj;
}
```

```cpp
struct ObjectDispatch
{
    IDispatch* obj;
};
```

Se si vuole effettuare il marshalling come `VARIANT`, aggiungere un <xref:System.Runtime.InteropServices.MarshalAsAttribute> con il valore <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>.

```csharp
public struct ObjectVariant
{
    [MarshalAs(UnmanagedType.Struct)]
    public object obj;
}
```

```cpp
struct ObjectVariant
{
    VARIANT obj;
};
```

La tabella seguente descrive i mapping tra i diversi tipi di runtime del campo `obj` e i vari tipi archiviati in un `VARIANT`:

| Tipo di .NET | Tipo VARIANT | | Tipo di .NET | Tipo VARIANT |
|------------|--------------|-|----------|--------------|
|  `byte`  | `VT_UI1` |     | `System.Runtime.InteropServices.BStrWrapper` | `VT_BSTR` |
| `sbyte`  | `VT_I1`  |     | `object`  | `VT_DISPATCH` |
| `short`  | `VT_I2`  |     | `System.Runtime.InteropServices.UnknownWrapper` | `VT_UNKNOWN` |
| `ushort` | `VT_UI2` |     | `System.Runtime.InteropServices.DispatchWrapper` | `VT_DISPATCH` |
| `int`    | `VT_I4`  |     | `System.Reflection.Missing` | `VT_ERROR` |
| `uint`   | `VT_UI4` |     | `(object)null` | `VT_EMPTY` |
| `long`   | `VT_I8`  |     | `bool` | `VT_BOOL` |
| `ulong`  | `VT_UI8` |     | `System.DateTime` | `VT_DATE` |
| `float`  | `VT_R4`  |     | `decimal` | `VT_DECIMAL` |
| `double` | `VT_R8`  |     | `System.Runtime.InteropServices.CurrencyWrapper` | `VT_CURRENCY` |
| `char`   | `VT_UI2` |     | `System.DBNull` | `VT_NULL` |
| `string` | `VT_BSTR`|
