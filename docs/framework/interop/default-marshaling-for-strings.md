---
title: Marshalling predefinito per le stringhe
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
ms.openlocfilehash: 49f2d871a42db484e20f0bfc35634a0e8b959c2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123555"
---
# <a name="default-marshaling-for-strings"></a>Marshalling predefinito per le stringhe

Le classi <xref:System.String?displayProperty=nameWithType> e <xref:System.Text.StringBuilder?displayProperty=nameWithType> presentano un comportamento del marshalling simile.

Viene eseguito il marshalling delle stringhe come tipo `BSTR` di tipo COM oppure come stringa con terminazione Null (matrice di caratteri che termina con un carattere Null). È possibile eseguire il marshalling dei caratteri all'interno della stringa come Unicode (impostazione predefinita nei sistemi Windows) o ANSI.

## <a name="strings-used-in-interfaces"></a>Stringhe usate nelle interfacce

La tabella seguente illustra le opzioni di marshalling per il tipo di dati stringa quando il marshalling viene effettuato come argomento di metodo in codice non gestito. L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe in interfacce COM.

|Tipo di enumerazione|Descrizione del formato non gestito|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr` (impostazione predefinita)|`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.|
|`UnmanagedType.LPStr`|Puntatore a matrice di caratteri ANSI con terminazione Null.|
|`UnmanagedType.LPWStr`|Puntatore a una matrice con terminazione Null di caratteri Unicode.|

Questa tabella è applicabile alla <xref:System.String>. Per <xref:System.Text.StringBuilder>, le uniche opzioni consentite sono `UnmanagedType.LPStr` e `UnmanagedType.LPWStr`.

L'esempio seguente mostra stringhe dichiarate nell'interfaccia `IStringWorker`.

```csharp
public interface IStringWorker
{
    void PassString1(string s);
    void PassString2([MarshalAs(UnmanagedType.BStr)] string s);
    void PassString3([MarshalAs(UnmanagedType.LPStr)] string s);
    void PassString4([MarshalAs(UnmanagedType.LPWStr)] string s);
    void PassStringRef1(ref string s);
    void PassStringRef2([MarshalAs(UnmanagedType.BStr)] ref string s);
    void PassStringRef3([MarshalAs(UnmanagedType.LPStr)] ref string s);
    void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)] ref string s);
}
```

```vb
Public Interface IStringWorker
    Sub PassString1(s As String)
    Sub PassString2(<MarshalAs(UnmanagedType.BStr)> s As String)
    Sub PassString3(<MarshalAs(UnmanagedType.LPStr)> s As String)
    Sub PassString4(<MarshalAs(UnmanagedType.LPWStr)> s As String)
    Sub PassStringRef1(ByRef s As String)
    Sub PassStringRef2(<MarshalAs(UnmanagedType.BStr)> ByRef s As String)
    Sub PassStringRef3(<MarshalAs(UnmanagedType.LPStr)> ByRef s As String)
    Sub PassStringRef4(<MarshalAs(UnmanagedType.LPWStr)> ByRef s As String)
End Interface
```

L'esempio seguente mostra l'interfaccia corrispondente descritta in una libreria dei tipi.

```cpp
interface IStringWorker : IDispatch
{
    HRESULT PassString1([in] BSTR s);
    HRESULT PassString2([in] BSTR s);
    HRESULT PassString3([in] LPStr s);
    HRESULT PassString4([in] LPWStr s);
    HRESULT PassStringRef1([in, out] BSTR *s);
    HRESULT PassStringRef2([in, out] BSTR *s);
    HRESULT PassStringRef3([in, out] LPStr *s);
    HRESULT PassStringRef4([in, out] LPWStr *s);
};
```

## <a name="strings-used-in-platform-invoke"></a>Stringhe usate in Platform invoke

Platform invoke copia argomenti di stringa, effettuando la conversione dal formato .NET Framework (Unicode) al formato della piattaforma non gestita. Le stringhe non sono modificabili e non vengono copiate di nuovo dalla memoria non gestita alla memoria gestita quando la chiamata restituisce un risultato.

La tabella seguente elenca le opzioni di marshalling per le stringhe quando il marshalling viene effettuato come argomento di metodo di una chiamata Platform invoke. L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe.

|Tipo di enumerazione|Descrizione del formato non gestito|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|`BSTR` di tipo COM con lunghezza fissa e caratteri ANSI.|
|`UnmanagedType.BStr`|`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.|
|`UnmanagedType.LPStr` (impostazione predefinita)|Puntatore a matrice di caratteri ANSI con terminazione Null.|
|`UnmanagedType.LPTStr`|Puntatore a una matrice con terminazione Null di caratteri dipendenti dalla piattaforma.|
|`UnmanagedType.LPUTF8Str`|Puntatore a una matrice con terminazione Null di caratteri UTF-8 codificati.|
|`UnmanagedType.LPWStr`|Puntatore a una matrice con terminazione Null di caratteri Unicode.|
|`UnmanagedType.TBStr`|`BSTR` di tipo COM con lunghezza fissa e caratteri dipendenti dalla piattaforma.|
|`VBByRefStr`|Valore che consente a Visual Basic .NET di modificare una stringa in codice non gestito e riflettere i risultati in codice gestito. Questo valore è supportato solo per platform invoke. Si tratta del valore predefinito in Visual Basic per le stringhe `ByVal`.|

Questa tabella è applicabile alla <xref:System.String>. Per <xref:System.Text.StringBuilder>, le uniche opzioni consentite sono `LPStr`, `LPTStr` e `LPWStr`.

La definizione del tipo seguente mostra l'uso corretto di `MarshalAsAttribute` per chiamate Platform invoke.

```csharp
class StringLibAPI
{
    [DllImport("StringLib.dll")]
    public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPWStr([MarshalAs(UnmanagedType.LPWStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPTStr([MarshalAs(UnmanagedType.LPTStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPUTF8Str([MarshalAs(UnmanagedType.LPUTF8Str)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)] string s);
}
```

```vb
Class StringLibAPI
    Public Declare Auto Sub PassLPStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPStr)> s As String)
    Public Declare Auto Sub PassLPWStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPWStr)> s As String)
    Public Declare Auto Sub PassLPTStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPTStr)> s As String)
    Public Declare Auto Sub PassLPUTF8Str Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPUTF8Str)> s As String)
    Public Declare Auto Sub PassBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.BStr)> s As String)
    Public Declare Auto Sub PassAnsiBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.AnsiBStr)> s As String)
    Public Declare Auto Sub PassTBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.TBStr)> s As String)
End Class
```

## <a name="strings-used-in-structures"></a>Stringhe usate nelle strutture

Le stringhe sono membri validi delle strutture, ma i buffer <xref:System.Text.StringBuilder> non sono validi nelle strutture. La tabella seguente illustra le opzioni di marshalling per il tipo di dati <xref:System.String> quando viene eseguito il marshalling del tipo come campo. L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe in un campo.

|Tipo di enumerazione|Descrizione del formato non gestito|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.|
|`UnmanagedType.LPStr` (impostazione predefinita)|Puntatore a matrice di caratteri ANSI con terminazione Null.|
|`UnmanagedType.LPTStr`|Puntatore a una matrice con terminazione Null di caratteri dipendenti dalla piattaforma.|
|`UnmanagedType.LPUTF8Str`|Puntatore a una matrice con terminazione Null di caratteri UTF-8 codificati.|
|`UnmanagedType.LPWStr`|Puntatore a una matrice con terminazione Null di caratteri Unicode.|
|`UnmanagedType.ByValTStr`|Matrice di caratteri a lunghezza fissa. Il tipo della matrice viene determinato dal set di carattere della struttura che la contiene.|

Il tipo `ByValTStr` viene usato per matrici di caratteri inline e di lunghezza fissa, disponibili all'interno di una struttura. Altri tipi sono applicabili a riferimenti di stringa contenuti in strutture che includono puntatori ad altre stringhe.

L'argomento `CharSet` di <xref:System.Runtime.InteropServices.StructLayoutAttribute> applicato alla struttura contenitore determina il formato dei caratteri delle stringhe nelle strutture. Le strutture di esempio seguenti contengono riferimenti a stringhe e stringhe inline, oltre a caratteri ANSI, Unicode e dipendenti dalla piattaforma. La rappresentazione di tali strutture in una libreria dei tipi è illustrata nel codice C++ seguente:

```cpp
struct StringInfoA
{
    char *  f1;
    char    f2[256];
};

struct StringInfoW
{
    WCHAR * f1;
    WCHAR   f2[256];
    BSTR    f3;
};

struct StringInfoT
{
    TCHAR * f1;
    TCHAR   f2[256];
};
```

L'esempio seguente illustra come usare <xref:System.Runtime.InteropServices.MarshalAsAttribute> per definire la stessa struttura in formati diversi.

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
struct StringInfoA
{
    [MarshalAs(UnmanagedType.LPStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
struct StringInfoW
{
    [MarshalAs(UnmanagedType.LPWStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
    [MarshalAs(UnmanagedType.BStr)] public string f3;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Auto)]
struct StringInfoT
{
    [MarshalAs(UnmanagedType.LPTStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}
```

```vb
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _
Structure StringInfoA
    <MarshalAs(UnmanagedType.LPStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _
Structure StringInfoW
    <MarshalAs(UnmanagedType.LPWStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
<MarshalAs(UnmanagedType.BStr)> Public f3 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _
Structure StringInfoT
    <MarshalAs(UnmanagedType.LPTStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure
```

## <a name="fixed-length-string-buffers"></a>Buffer di stringhe di lunghezza fissa

In alcuni casi, è necessario passare un buffer di caratteri a lunghezza fissa nel codice non gestito da modificare. Il semplice passaggio di una stringa non funziona in questo caso perché il chiamato non può modificare il contenuto del buffer passato. Anche se la stringa viene passata per riferimento, non è possibile inizializzare il buffer su una dimensione specifica.

La soluzione consiste nel passare come argomento un buffer <xref:System.Text.StringBuilder> invece di una <xref:System.String>.  Il chiamato può dereferenziare e modificare un oggetto `StringBuilder`, purché non venga superata la capacità dell'oggetto `StringBuilder` stesso. È anche possibile inizializzare questo oggetto in base a una lunghezza fissa. Se, ad esempio, si inizializza un buffer `StringBuilder` per una capacità pari a `N`, un buffer di caratteri di dimensione (`N`+1) viene fornito dal gestore di marshalling. Il valore +1 tiene conto del fatto che, a differenza di `StringBuilder`, la stringa non gestita ha una terminazione Null.

Ad esempio, la funzione [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API Windows (definita in *winuser. h*) richiede che il chiamante passi un buffer di caratteri a lunghezza fissa in cui la funzione scrive il testo della finestra. `LpString` punta a un buffer allocato dal chiamante di dimensione `nMaxCount`. Il chiamante deve allocare il buffer e impostare l'argomento `nMaxCount` sulla dimensione del buffer allocato. L'esempio seguente illustra la dichiarazione della funzione `GetWindowText` come definita in *winuser.h*.

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

 Il chiamato può dereferenziare e modificare un oggetto `StringBuilder`, purché non venga superata la capacità dell'oggetto `StringBuilder` stesso. L'esempio di codice seguente illustra come inizializzare `StringBuilder` in base a una lunghezza fissa.

```csharp
using System;
using System.Runtime.InteropServices;
using System.Text;

internal static class NativeMethods
{
    [DllImport("User32.dll")]
    internal static extern void GetWindowText(IntPtr hWnd, StringBuilder lpString, int nMaxCount);
}

public class Window
{
    internal IntPtr h;        // Internal handle to Window.
    public String GetText()
    {
        StringBuilder sb = new StringBuilder(256);
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1);
        return sb.ToString();
    }
}
```

```vb
Imports System.Text

Friend Class NativeMethods
    Friend Declare Auto Sub GetWindowText Lib "User32.dll" _
        (hWnd As IntPtr, lpString As StringBuilder, nMaxCount As Integer)
End Class

Public Class Window
    Friend h As IntPtr ' Friend handle to Window.
    Public Function GetText() As String
        Dim sb As New StringBuilder(256)
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1)
        Return sb.ToString()
   End Function
End Class
```

## <a name="see-also"></a>Vedere anche

- [Comportamento di marshalling predefinito](default-marshaling-behavior.md)
- [Marshalling di stringhe](marshaling-strings.md)
- [Tipi copiabili e non copiabili](blittable-and-non-blittable-types.md)
- [Attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [copia e blocco](copying-and-pinning.md)
