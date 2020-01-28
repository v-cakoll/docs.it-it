---
title: Procedure consigliate di interoperabilità nativa - .NET
description: Informazioni sulle procedure consigliate per interfacciarsi con i componenti nativi in .NET.
ms.date: 01/18/2019
ms.openlocfilehash: 9486256b815856c0c283f5fe231be3d35d6e8f00
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742757"
---
# <a name="native-interoperability-best-practices"></a>Procedure consigliate di interoperabilità nativa

.NET offre diversi modi per personalizzare il codice di interoperabilità nativa. Questo articolo include le linee guida seguite dai team di Microsoft .NET per l'interoperabilità nativa.

## <a name="general-guidance"></a>Indicazioni generali

Le linee guida in questa sezione si applicano a tutti gli scenari di interoperabilità.

- ✔️ usare la stessa denominazione e la stessa maiuscola per i metodi e i parametri del metodo nativo che si vuole chiamare.
- ✔️ considerare la possibilità di usare lo stesso nome e la stessa maiuscola per i valori costanti.
- ✔️ usano tipi .NET che eseguono il mapping più vicino al tipo nativo. Ad esempio, in C# usare `uint` quando il tipo nativo è `unsigned int`.
- ✔️ VENGONO utilizzati solo gli attributi `[In]` e `[Out]` quando il comportamento desiderato differisce dal comportamento predefinito.
- ✔️ CONSIGLIABILE usare <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> per eseguire il pooling dei buffer di matrice nativi.
- ✔️ CONSIGLIABILE eseguire il wrapping delle dichiarazioni P/Invoke in una classe con lo stesso nome e le stesse maiuscole della libreria nativa.
  - In questo modo gli attributi `[DllImport]` possono usare la funzionalità del linguaggio `nameof` C# per passare il nome della libreria nativa e assicurarsi che il nome della libreria nativa non sia stato digitato in modo errato.

## <a name="dllimport-attribute-settings"></a>Impostazioni degli attributi DllImport

| Impostazione di | Default | Indicazione | Dettagli |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  Mantenere l'impostazione predefinita  | Con l'impostazione esplicita su false, i valori restituiti HRESULT di errore verranno convertiti in eccezioni e il valore restituito nella definizione diventa Null di conseguenza.|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | Dipende dall'API  | Impostare su true se l'API usa GetLastError e usare Marshal.GetLastWin32Error per ottenere il valore. Se l'API imposta una condizione che indica la presenza di un errore, recuperare l'errore prima di effettuare altre chiamate in modo da evitare di sovrascriverlo inavvertitamente.|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | `CharSet.None` con fallback al comportamento `CharSet.Ansi`  | Usare in modo esplicito `CharSet.Unicode` o `CharSet.Ansi` quando sono presenti stringhe o caratteri nella definizione | Specifica il comportamento di marshalling delle stringhe e il comportamento di `ExactSpelling` quando è impostato su `false`. Si noti che `CharSet.Ansi` è in effetti UTF8 su Unix. Nella _maggior parte_ dei casi Windows usa Unicode, mentre Unix usa UTF8. Vedere altre informazioni nella [documentazione sui set di caratteri](./charset.md). |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | Impostare su true e ottenere un leggero miglioramento delle prestazioni perché il runtime non cercherà nomi di funzioni alternativi con suffisso "A" o "W" in base al valore dell'impostazione `CharSet` ("A" per `CharSet.Ansi` e "W" per `CharSet.Unicode`). |

## <a name="string-parameters"></a>Parametri stringa

Quando il set di caratteri è Unicode o l'argomento viene contrassegnato in modo esplicito come `[MarshalAs(UnmanagedType.LPWSTR)]` _e_ la stringa viene passata per valore (non `ref` o `out`), la stringa verrà bloccata e utilizzata direttamente dal codice nativo (anziché copiata).

Ricordarsi di contrassegnare `[DllImport]` come `Charset.Unicode` a meno che non si voglia usare in modo esplicito il trattamento ANSI per le stringhe.

❌ non utilizzano parametri di `[Out] string`. I parametri stringa passati per valore con l'attributo `[Out]` possono destabilizzare il runtime se la stringa è una stringa centralizzata. Altre informazioni sulla centralizzazione delle stringhe sono disponibili nella documentazione relativa a <xref:System.String.Intern%2A?displayProperty=nameWithType>.

❌ evitare `StringBuilder` parametri. Il marshalling di `StringBuilder` crea *sempre* una copia del buffer nativo. Di conseguenza, può risultare estremamente inefficiente. Si consideri lo scenario tipico di chiamata di un'API di Windows che accetta una stringa:

1. Creare un SB con la capacità desiderata (alloca capacità gestita) **{1}**
2. Richiamare
   1. Alloca un buffer nativo **{2}**
   2. Copia il contenuto se `[In]` _(impostazione predefinita per un parametro `StringBuilder`)_
   3. Copia il buffer nativo in una matrice gestita appena allocata se `[Out]` **{3}** _(impostazione predefinita anche per `StringBuilder`)_
3. `ToString()` alloca ancora un'altra matrice gestita **{4}**

Vale a dire *{4}* allocazioni per ottenere una stringa dal codice nativo. Il meglio che è possibile fare per limitare le allocazioni è riutilizzare `StringBuilder` in un'altra chiamata, ma in questo modo si risparmia solo *1* allocazione. È molto meglio usare e memorizzare nella cache un buffer di caratteri da `ArrayPool`. In questo modo si può arrivare alla sola allocazione per `ToString()` nelle chiamate successive.

L'altro problema con `StringBuilder` è che copia sempre il buffer restituito fino primo valore Null. Se la stringa passata non è terminata o è una stringa con terminazione Null doppia, nel migliore dei casi P/Invoke non è corretto.

Se si *usa*`StringBuilder`, un altro aspetto da tenere presente è che la capacità **non** include un valore Null nascosto, sempre considerato per l'interoperabilità. È comune sbagliarsi, perché la maggior parte delle API vuole le dimensioni del buffer *comprensive* del valore Null. Ciò può comportare allocazioni sprecate/superflue. Questo problema impedisce inoltre al runtime di ottimizzare il marshalling di `StringBuilder` per ridurre al minimo le copie.

✔️ CONSIGLIABILE utilizzare `char[]`da un `ArrayPool`.

Per altre informazioni sul marshalling delle stringhe, vedere [Marshalling predefinito per le stringhe](../../framework/interop/default-marshaling-for-strings.md) e [Personalizzazione dei parametri stringa](customize-parameter-marshaling.md#customizing-string-parameters).

> __Specifiche di Windows__ Per le stringhe di `[Out]` CLR utilizzerà `CoTaskMemFree` per impostazione predefinita per liberare stringhe o `SysStringFree` per le stringhe contrassegnate come `UnmanagedType.BSTR`.
> **Per la maggior parte delle API con un buffer di stringa di output:** Il numero di caratteri passati deve includere il valore null. Se il valore restituito è minore del numero di caratteri passato, la chiamata ha avuto esito positivo e il valore è il numero di caratteri *senza* il carattere Null finale. In caso contrario, il numero corrisponde alle dimensioni richieste del buffer *incluso* il carattere Null.
>
> - Passare 5, Get 4: la stringa ha una lunghezza di 4 caratteri con un valore null finale.
> - Passare 5, Get 6: la lunghezza della stringa è di 5 caratteri, è necessario un buffer di 6 caratteri per mantenere il valore null.
> [Tipi di dati di Windows per le stringhe](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a>Parametri e campi booleani

È facile sbagliare con i valori booleani. Per impostazione predefinita, per il tipo `bool` .NET viene effettuato il marshalling nel tipo `BOOL` Windows, in cui è un valore a 4 byte. Tuttavia, i tipi `_Bool` e `bool` in C e C++ sono a byte *singolo*. A causa di questa differenza può essere difficile risolvere eventuali bug, perché metà del valore restituito verrà rimosso e il risultato verrà modificato solo *potenzialmente*. Per altre informazioni sul marshalling dei valori `bool` .NET in tipi `bool` C o C++, vedere la documentazione relativa alla [personalizzazione del marshalling di campi booleani](customize-struct-marshaling.md#customizing-boolean-field-marshaling).

## <a name="guids"></a>GUID

I GUID possono essere usati direttamente nelle firme. Molte API di Windows accettano alias del tipo `GUID&` come `REFIID`. In caso di passaggio per riferimento, possono essere passati per `ref` o con l'attributo `[MarshalAs(UnmanagedType.LPStruct)]`.

| GUID | GUID per riferimento |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

❌ non usare `[MarshalAs(UnmanagedType.LPStruct)]` per un valore diverso da `ref` parametri GUID.

## <a name="blittable-types"></a>Tipi copiabili da BLT

I tipi copiabili da BLT sono tipi che hanno la stessa rappresentazione a livello di bit nel codice gestito e nativo. Di conseguenza non è necessario convertirli in un altro formato per effettuarne il marshalling in e da codice nativo e dovrebbero essere preferiti perché le prestazioni risultano migliori.

**Tipi copiabili da BLT:**

- `byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`
- Matrici unidimensionali non annidate di tipi copiabili da BLT (ad esempio, `int[]`)
- Struct e classi con layout fisso che hanno solo tipi valore copiabili da BLT per i campi di istanza
  - Per il layout fisso è richiesto `[StructLayout(LayoutKind.Sequential)]` o `[StructLayout(LayoutKind.Explicit)]`
  - Gli struct sono `LayoutKind.Sequential` per impostazione predefinita, le classi sono `LayoutKind.Auto`

**NON copiabili da BLT:**

- `bool`

**A VOLTE copiabili da BLT:**

- `char`, `string`

Quando i tipi copiabili da BLT vengono passati per riferimento, vengono semplicemente bloccati dal gestore del marshalling invece di essere copiati in un buffer intermedio. (Le classi vengono passare in modo intrinseco per riferimento, mentre gli struct vengono passati per riferimento quando vengono usati con `ref` o `out`.)

`char` è copiabile da BLT in una matrice unidimensionale **oppure** se fa parte di un tipo che lo contiene viene contrassegnato in modo esplicito con `[StructLayout]` con `CharSet = CharSet.Unicode`.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

`string` è copiabile da BLT se non è contenuto in un altro tipo e viene passato come argomento che è contrassegnato con `[MarshalAs(UnmanagedType.LPWStr)]` o se per `[DllImport]` è impostato `CharSet = CharSet.Unicode`.

È possibile verificare se un tipo è copiabile da BLT tentando di creare un `GCHandle` bloccato. Se il tipo non è una stringa o non è considerato copiabile da BLT, `GCHandle.Alloc` genererà una `ArgumentException`.

✔️ rendere le strutture copiabili quando possibile.

Per altre informazioni, vedere:

- [Tipi copiabili e non copiabili](../../framework/interop/blittable-and-non-blittable-types.md)
- [Marshalling dei tipi](type-marshaling.md)

## <a name="keeping-managed-objects-alive"></a>Mantenere attivi gli oggetti gestiti

`GC.KeepAlive()` garantisce che un oggetto rimanga nell'ambito fino a quando non viene raggiunto il metodo KeepAlive.

[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) consente al gestore di marshalling mantenere attivo un oggetto per la durata di P/Invoke. Può essere usato al posto di `IntPtr` nelle firme dei metodi. `SafeHandle` sostituisce questa classe in modo efficace ed è consigliabile usarlo in alternativa.

[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) consente di bloccare un oggetto gestito e di ottenere il puntatore nativo a tale oggetto. Il modello di base è:

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

L'aggiunta non è il comportamento predefinito per `GCHandle`. L'altro modello principale è per il passaggio di un riferimento a un oggetto gestito tramite codice nativo per tornare poi al codice gestito, in genere con un callback. Ecco il modello:

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

Non dimenticare che `GCHandle` deve essere liberato in modo esplicito per evitare perdite di memoria.

## <a name="common-windows-data-types"></a>Tipi di dati Windows comuni

L'elenco seguente contiene i tipi di dati comunemente usati nelle API Windows e i tipi C# da usare per chiamate nel codice Windows.

I tipi seguenti hanno le stesse dimensioni in Windows a 32 e 64 bit, nonostante i nomi.

| Larghezza | Portale di          | C (Windows)          | C#       | Alternativa                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| 32    | `BOOL`           | `int`                | `int`    | `bool`                               |
| 8     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| 8     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| 8     | `CHAR`           | `char`               | `sbyte`  |                                      |
| 8     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| 16    | `SHORT`          | `short`              | `short`  |                                      |
| 16    | `CSHORT`         | `short`              | `short`  |                                      |
| 16    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| 16    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| 16    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| 32    | `INT`            | `int`                | `int`    |                                      |
| 32    | `LONG`           | `long`               | `int`    |                                      |
| 32    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| 32    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| 64    | `QWORD`          | `long long`          | `long`   |                                      |
| 64    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| 64    | `LONGLONG`       | `long long`          | `long`   |                                      |
| 64    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| 64    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| 32    | `HRESULT`        | `long`               | `int`    |                                      |
| 32    | `NTSTATUS`       | `long`               | `int`    |                                      |

I tipi seguenti, essendo puntatori, seguono la larghezza della piattaforma. Usare `IntPtr`/`UIntPtr` per questi tipi.

| Tipi di puntatore con segno (usare `IntPtr`) | Tipi di puntatore senza segno (usare `UIntPtr`) |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

Per un tipo `PVOID` Windows corrispondente al tipo `void*` C è possibile effettuare il marshalling come `IntPtr` oppure `UIntPtr`, ma preferire `void*` quando possibile.

[Tipi di dati di Windows](/windows/desktop/WinProg/windows-data-types)

[Intervalli dei tipi di dati](/cpp/cpp/data-type-ranges)

## <a name="structs"></a>Strutture

Gli struct gestiti vengono creati nello stack e non vengono rimossi fino a quando il metodo non restituisce il controllo. Per definizione vengono quindi "bloccati" (non verranno spostati dal GC). È possibile semplicemente accettare l'indirizzo nei blocchi di codice non gestito, se il codice nativo non userà il puntatore oltre la fine del metodo corrente.

Gli struct copiabili da BLT offrono prestazioni decisamente migliori perché possono essere usati direttamente dal livello di marshalling. Provare a rendere gli struct copiabili da BLT (ad esempio, evitare `bool`). Per altre informazioni, vedere la sezione [Tipi copiabili da BLT](#blittable-types).

*Se* lo struct è copiabile da BLT, usare `sizeof()` invece di `Marshal.SizeOf<MyStruct>()` per ottenere prestazioni migliori. Come indicato in precedenza, è possibile verificare che il tipo sia copiabile da BLT tentando di creare un `GCHandle` bloccato. Se il tipo non è una stringa o non è considerato copiabile da BLT, `GCHandle.Alloc` genererà una `ArgumentException`.

I puntatori agli struct nelle definizioni devono essere passati per `ref` oppure usare `unsafe` e `*`.

✔️ corrispondono allo struct gestito il più vicino possibile alla forma e ai nomi usati nella documentazione o nell'intestazione della piattaforma ufficiale.

per migliorare le prestazioni C# , ✔️ utilizzare la `sizeof()` invece di `Marshal.SizeOf<MyStruct>()` per le strutture copiabili.

Ad esempio, è necessario effettuare il marshalling di una matrice come `INT_PTR Reserved1[2]` in due campi `IntPtr`, `Reserved1a` e `Reserved1b`. Quando la matrice nativa è un tipo primitivo, è possibile usare la parola chiave `fixed` per scriverla in modo un po' più pulito. Ad esempio, `SYSTEM_PROCESS_INFORMATION` ha un aspetto simile al seguente nell'intestazione nativa:

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

In C# è possibile scriverla come segue:

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

Esistono tuttavia alcune complicazioni con i buffer fissi. I buffer fissi di tipi non copiabili da BLT non verranno correttamente sottoposti a marshalling, quindi la matrice sul posto deve essere espansa in più campi singoli. Inoltre, in .NET Framework e .NET Core precedente alla versione 3.0, se uno struct contenente un campo buffer fisso viene annidato all'interno di uno struct non copiabile da BLT, il marshalling in codice nativo del campo buffer fisso non verrà eseguito correttamente.
