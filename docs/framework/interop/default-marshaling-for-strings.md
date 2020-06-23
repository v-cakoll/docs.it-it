---
title: Marshalling predefinito per le stringhe
description: Esaminare il comportamento di marshalling predefinito per le stringhe in interfacce, platform invoke, strutture & buffer di stringhe a lunghezza fissa in .NET.
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
ms.openlocfilehash: 440a49730f351b820cd68a741e79f94434f585c8
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904117"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="c9185-103">Marshalling predefinito per le stringhe</span><span class="sxs-lookup"><span data-stu-id="c9185-103">Default Marshaling for Strings</span></span>

<span data-ttu-id="c9185-104">Le classi <xref:System.String?displayProperty=nameWithType> e <xref:System.Text.StringBuilder?displayProperty=nameWithType> presentano un comportamento del marshalling simile.</span><span class="sxs-lookup"><span data-stu-id="c9185-104">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>

<span data-ttu-id="c9185-105">Viene eseguito il marshalling delle stringhe come tipo `BSTR` di tipo COM oppure come stringa con terminazione Null (matrice di caratteri che termina con un carattere Null).</span><span class="sxs-lookup"><span data-stu-id="c9185-105">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="c9185-106">È possibile eseguire il marshalling dei caratteri all'interno della stringa come Unicode (impostazione predefinita nei sistemi Windows) o ANSI.</span><span class="sxs-lookup"><span data-stu-id="c9185-106">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="c9185-107">Stringhe usate nelle interfacce</span><span class="sxs-lookup"><span data-stu-id="c9185-107">Strings Used in Interfaces</span></span>

<span data-ttu-id="c9185-108">La tabella seguente illustra le opzioni di marshalling per il tipo di dati stringa quando il marshalling viene effettuato come argomento di metodo in codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="c9185-108">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="c9185-109">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe in interfacce COM.</span><span class="sxs-lookup"><span data-stu-id="c9185-109">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>

|<span data-ttu-id="c9185-110">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="c9185-110">Enumeration type</span></span>|<span data-ttu-id="c9185-111">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="c9185-111">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="c9185-112">`UnmanagedType.BStr` (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c9185-112">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="c9185-113">`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9185-113">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|`UnmanagedType.LPStr`|<span data-ttu-id="c9185-114">Puntatore a matrice di caratteri ANSI con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="c9185-114">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="c9185-115">Puntatore a una matrice con terminazione Null di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9185-115">A pointer to a null-terminated array of Unicode characters.</span></span>|

<span data-ttu-id="c9185-116">Questa tabella è applicabile alla <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c9185-116">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="c9185-117">Per <xref:System.Text.StringBuilder>, le uniche opzioni consentite sono `UnmanagedType.LPStr` e `UnmanagedType.LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="c9185-117">For <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>

<span data-ttu-id="c9185-118">L'esempio seguente mostra stringhe dichiarate nell'interfaccia `IStringWorker`.</span><span class="sxs-lookup"><span data-stu-id="c9185-118">The following example shows strings declared in the `IStringWorker` interface.</span></span>

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

<span data-ttu-id="c9185-119">L'esempio seguente mostra l'interfaccia corrispondente descritta in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="c9185-119">The following example shows the corresponding interface described in a type library.</span></span>

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

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="c9185-120">Stringhe usate in Platform invoke</span><span class="sxs-lookup"><span data-stu-id="c9185-120">Strings Used in Platform Invoke</span></span>

<span data-ttu-id="c9185-121">Platform invoke copia argomenti di stringa, effettuando la conversione dal formato .NET Framework (Unicode) al formato della piattaforma non gestita.</span><span class="sxs-lookup"><span data-stu-id="c9185-121">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="c9185-122">Le stringhe non sono modificabili e non vengono copiate di nuovo dalla memoria non gestita alla memoria gestita quando la chiamata restituisce un risultato.</span><span class="sxs-lookup"><span data-stu-id="c9185-122">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>

<span data-ttu-id="c9185-123">La tabella seguente elenca le opzioni di marshalling per le stringhe quando il marshalling viene effettuato come argomento di metodo di una chiamata Platform invoke.</span><span class="sxs-lookup"><span data-stu-id="c9185-123">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="c9185-124">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe.</span><span class="sxs-lookup"><span data-stu-id="c9185-124">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>

|<span data-ttu-id="c9185-125">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="c9185-125">Enumeration type</span></span>|<span data-ttu-id="c9185-126">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="c9185-126">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="c9185-127">`BSTR` di tipo COM con lunghezza fissa e caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="c9185-127">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|
|`UnmanagedType.BStr`|<span data-ttu-id="c9185-128">`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9185-128">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="c9185-129">`UnmanagedType.LPStr` (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c9185-129">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="c9185-130">Puntatore a matrice di caratteri ANSI con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="c9185-130">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="c9185-131">Puntatore a una matrice con terminazione Null di caratteri dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c9185-131">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="c9185-132">Puntatore a una matrice con terminazione Null di caratteri UTF-8 codificati.</span><span class="sxs-lookup"><span data-stu-id="c9185-132">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="c9185-133">Puntatore a una matrice con terminazione Null di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9185-133">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.TBStr`|<span data-ttu-id="c9185-134">`BSTR` di tipo COM con lunghezza fissa e caratteri dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c9185-134">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|
|`VBByRefStr`|<span data-ttu-id="c9185-135">Valore che consente a Visual Basic .NET di modificare una stringa in codice non gestito e riflettere i risultati in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c9185-135">A value that enables Visual Basic .NET to change a string in unmanaged code and have the results reflected in managed code.</span></span> <span data-ttu-id="c9185-136">Questo valore è supportato solo per platform invoke.</span><span class="sxs-lookup"><span data-stu-id="c9185-136">This value is supported only for platform invoke.</span></span> <span data-ttu-id="c9185-137">Si tratta del valore predefinito in Visual Basic per le stringhe `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="c9185-137">This is the default value in Visual Basic for `ByVal` strings.</span></span>|

<span data-ttu-id="c9185-138">Questa tabella è applicabile alla <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c9185-138">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="c9185-139">Per <xref:System.Text.StringBuilder>, le uniche opzioni consentite sono `LPStr`, `LPTStr` e `LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="c9185-139">For <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>

<span data-ttu-id="c9185-140">La definizione del tipo seguente mostra l'uso corretto di `MarshalAsAttribute` per chiamate Platform invoke.</span><span class="sxs-lookup"><span data-stu-id="c9185-140">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>

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

## <a name="strings-used-in-structures"></a><span data-ttu-id="c9185-141">Stringhe usate nelle strutture</span><span class="sxs-lookup"><span data-stu-id="c9185-141">Strings Used in Structures</span></span>

<span data-ttu-id="c9185-142">Le stringhe sono membri validi delle strutture, ma i buffer <xref:System.Text.StringBuilder> non sono validi nelle strutture.</span><span class="sxs-lookup"><span data-stu-id="c9185-142">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="c9185-143">La tabella seguente illustra le opzioni di marshalling per il tipo di dati <xref:System.String> quando viene eseguito il marshalling del tipo come campo.</span><span class="sxs-lookup"><span data-stu-id="c9185-143">The following table shows the marshaling options for the <xref:System.String> data type when the type is marshaled as a field.</span></span> <span data-ttu-id="c9185-144">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe in un campo.</span><span class="sxs-lookup"><span data-stu-id="c9185-144">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>

|<span data-ttu-id="c9185-145">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="c9185-145">Enumeration type</span></span>|<span data-ttu-id="c9185-146">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="c9185-146">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|<span data-ttu-id="c9185-147">`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9185-147">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="c9185-148">`UnmanagedType.LPStr` (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="c9185-148">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="c9185-149">Puntatore a matrice di caratteri ANSI con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="c9185-149">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="c9185-150">Puntatore a una matrice con terminazione Null di caratteri dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c9185-150">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="c9185-151">Puntatore a una matrice con terminazione Null di caratteri UTF-8 codificati.</span><span class="sxs-lookup"><span data-stu-id="c9185-151">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="c9185-152">Puntatore a una matrice con terminazione Null di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="c9185-152">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.ByValTStr`|<span data-ttu-id="c9185-153">Matrice di caratteri a lunghezza fissa. Il tipo della matrice viene determinato dal set di carattere della struttura che la contiene.</span><span class="sxs-lookup"><span data-stu-id="c9185-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|

<span data-ttu-id="c9185-154">Il tipo `ByValTStr` viene usato per matrici di caratteri inline e di lunghezza fissa, disponibili all'interno di una struttura.</span><span class="sxs-lookup"><span data-stu-id="c9185-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="c9185-155">Altri tipi sono applicabili a riferimenti di stringa contenuti in strutture che includono puntatori ad altre stringhe.</span><span class="sxs-lookup"><span data-stu-id="c9185-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>

<span data-ttu-id="c9185-156">L'argomento `CharSet` di <xref:System.Runtime.InteropServices.StructLayoutAttribute> applicato alla struttura contenitore determina il formato dei caratteri delle stringhe nelle strutture.</span><span class="sxs-lookup"><span data-stu-id="c9185-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="c9185-157">Le strutture di esempio seguenti contengono riferimenti a stringhe e stringhe inline, oltre a caratteri ANSI, Unicode e dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="c9185-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span> <span data-ttu-id="c9185-158">La rappresentazione di tali strutture in una libreria dei tipi è illustrata nel codice C++ seguente:</span><span class="sxs-lookup"><span data-stu-id="c9185-158">The representation of these structures in a type library is shown in the following C++ code:</span></span>

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

<span data-ttu-id="c9185-159">L'esempio seguente illustra come usare <xref:System.Runtime.InteropServices.MarshalAsAttribute> per definire la stessa struttura in formati diversi.</span><span class="sxs-lookup"><span data-stu-id="c9185-159">The following example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> to define the same structure in different formats.</span></span>

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

## <a name="fixed-length-string-buffers"></a><span data-ttu-id="c9185-160">Buffer di stringhe di lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="c9185-160">Fixed-Length String Buffers</span></span>

<span data-ttu-id="c9185-161">In alcuni casi, è necessario passare un buffer di caratteri a lunghezza fissa nel codice non gestito da modificare.</span><span class="sxs-lookup"><span data-stu-id="c9185-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="c9185-162">Il semplice passaggio di una stringa non funziona in questo caso perché il chiamato non può modificare il contenuto del buffer passato.</span><span class="sxs-lookup"><span data-stu-id="c9185-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="c9185-163">Anche se la stringa viene passata per riferimento, non è possibile inizializzare il buffer su una dimensione specifica.</span><span class="sxs-lookup"><span data-stu-id="c9185-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>

<span data-ttu-id="c9185-164">La soluzione consiste nel passare come argomento un buffer <xref:System.Text.StringBuilder> invece di una <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c9185-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a <xref:System.String>.</span></span> <span data-ttu-id="c9185-165"> Il chiamato può dereferenziare e modificare un oggetto `StringBuilder`, purché non venga superata la capacità dell'oggetto `StringBuilder` stesso.</span><span class="sxs-lookup"><span data-stu-id="c9185-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="c9185-166">È anche possibile inizializzare questo oggetto in base a una lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="c9185-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="c9185-167">Se, ad esempio, si inizializza un buffer `StringBuilder` per una capacità pari a `N`, un buffer di caratteri di dimensione (`N`+1) viene fornito dal gestore di marshalling.</span><span class="sxs-lookup"><span data-stu-id="c9185-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="c9185-168">Il valore +1 tiene conto del fatto che, a differenza di `StringBuilder`, la stringa non gestita ha una terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="c9185-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>

<span data-ttu-id="c9185-169">Ad esempio, la [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) funzione API Windows (definita in *winuser. h*) richiede che il chiamante passi un buffer di caratteri a lunghezza fissa in cui la funzione scrive il testo della finestra.</span><span class="sxs-lookup"><span data-stu-id="c9185-169">For example, the Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API function (defined in *winuser.h*) requires that the caller pass a fixed-length character buffer to which the function writes the window's text.</span></span> <span data-ttu-id="c9185-170">`LpString` punta a un buffer allocato dal chiamante di dimensione `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="c9185-170">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="c9185-171">Il chiamante deve allocare il buffer e impostare l'argomento `nMaxCount` sulla dimensione del buffer allocato.</span><span class="sxs-lookup"><span data-stu-id="c9185-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="c9185-172">L'esempio seguente illustra la dichiarazione della funzione `GetWindowText` come definita in *winuser.h*.</span><span class="sxs-lookup"><span data-stu-id="c9185-172">The following example shows the `GetWindowText` function declaration as defined in *winuser.h*.</span></span>

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

<span data-ttu-id="c9185-173"> Il chiamato può dereferenziare e modificare un oggetto `StringBuilder`, purché non venga superata la capacità dell'oggetto `StringBuilder` stesso.</span><span class="sxs-lookup"><span data-stu-id="c9185-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="c9185-174">L'esempio di codice seguente illustra come inizializzare `StringBuilder` in base a una lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="c9185-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c9185-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9185-175">See also</span></span>

- [<span data-ttu-id="c9185-176">comportamento predefinito del marshalling</span><span class="sxs-lookup"><span data-stu-id="c9185-176">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="c9185-177">Marshalling di stringhe</span><span class="sxs-lookup"><span data-stu-id="c9185-177">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="c9185-178">tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="c9185-178">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="c9185-179">[Attributi direzionali](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c9185-179">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="c9185-180">copia e blocco</span><span class="sxs-lookup"><span data-stu-id="c9185-180">Copying and Pinning</span></span>](copying-and-pinning.md)
