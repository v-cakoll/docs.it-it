---
title: Marshalling predefinito per le stringhe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47543056eaa538b008db3332dda776c0f300108d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078473"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="234db-102">Marshalling predefinito per le stringhe</span><span class="sxs-lookup"><span data-stu-id="234db-102">Default Marshaling for Strings</span></span>
<span data-ttu-id="234db-103">Le classi <xref:System.String?displayProperty=nameWithType> e <xref:System.Text.StringBuilder?displayProperty=nameWithType> presentano un comportamento del marshalling simile.</span><span class="sxs-lookup"><span data-stu-id="234db-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>  
  
 <span data-ttu-id="234db-104">Viene eseguito il marshalling delle stringhe come tipo `BSTR` di tipo COM oppure come stringa con terminazione Null (matrice di caratteri che termina con un carattere Null).</span><span class="sxs-lookup"><span data-stu-id="234db-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="234db-105">È possibile eseguire il marshalling dei caratteri all'interno della stringa come Unicode (impostazione predefinita nei sistemi Windows) o ANSI.</span><span class="sxs-lookup"><span data-stu-id="234db-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>  
  
 <span data-ttu-id="234db-106">Questo argomento fornisce le informazioni seguenti sul marshalling dei tipi di stringa:</span><span class="sxs-lookup"><span data-stu-id="234db-106">This topic provides the following information on marshaling string types:</span></span>  
  
-   [<span data-ttu-id="234db-107">Stringhe usate nelle interfacce</span><span class="sxs-lookup"><span data-stu-id="234db-107">Strings Used in Interfaces</span></span>](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [<span data-ttu-id="234db-108">Stringhe usate in Platform invoke</span><span class="sxs-lookup"><span data-stu-id="234db-108">Strings Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [<span data-ttu-id="234db-109">Stringhe usate nelle strutture</span><span class="sxs-lookup"><span data-stu-id="234db-109">Strings Used in Structures</span></span>](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [<span data-ttu-id="234db-110">Buffer di stringhe di lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="234db-110">Fixed-Length String Buffers</span></span>](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="234db-111">Stringhe usate nelle interfacce</span><span class="sxs-lookup"><span data-stu-id="234db-111">Strings Used in Interfaces</span></span>  
 <span data-ttu-id="234db-112">La tabella seguente illustra le opzioni di marshalling per il tipo di dati stringa quando il marshalling viene effettuato come argomento di metodo in codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="234db-112">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="234db-113">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe in interfacce COM.</span><span class="sxs-lookup"><span data-stu-id="234db-113">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>  
  
|<span data-ttu-id="234db-114">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="234db-114">Enumeration type</span></span>|<span data-ttu-id="234db-115">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="234db-115">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr` <span data-ttu-id="234db-116">(predefinito)</span><span class="sxs-lookup"><span data-stu-id="234db-116">(default)</span></span>|<span data-ttu-id="234db-117">`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="234db-117">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="234db-118">Puntatore a matrice di caratteri ANSI con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="234db-118">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="234db-119">Puntatore a una matrice con terminazione Null di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="234db-119">A pointer to a null-terminated array of Unicode characters.</span></span>|  
  
 <span data-ttu-id="234db-120">Questa tabella è applicabile alle stringhe.</span><span class="sxs-lookup"><span data-stu-id="234db-120">This table applies to strings.</span></span> <span data-ttu-id="234db-121">Per <xref:System.Text.StringBuilder>, tuttavia, le uniche opzioni consentite sono `UnmanagedType.LPStr` e `UnmanagedType.LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="234db-121">However, for <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>  
  
 <span data-ttu-id="234db-122">L'esempio seguente mostra stringhe dichiarate nell'interfaccia `IStringWorker`.</span><span class="sxs-lookup"><span data-stu-id="234db-122">The following example shows strings declared in the `IStringWorker` interface.</span></span>  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);
```

<span data-ttu-id="234db-123">L'esempio seguente mostra l'interfaccia corrispondente descritta in una libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="234db-123">The following example shows the corresponding interface described in a type library.</span></span>

```
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);
```

<a name="cpcondefaultmarshalingforstringsanchor5"></a>

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="234db-124">Stringhe usate in Platform invoke</span><span class="sxs-lookup"><span data-stu-id="234db-124">Strings Used in Platform Invoke</span></span>  
 <span data-ttu-id="234db-125">Platform invoke copia argomenti di stringa, effettuando la conversione dal formato .NET Framework (Unicode) al formato della piattaforma non gestita.</span><span class="sxs-lookup"><span data-stu-id="234db-125">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="234db-126">Le stringhe non sono modificabili e non vengono copiate di nuovo dalla memoria non gestita alla memoria gestita quando la chiamata restituisce un risultato.</span><span class="sxs-lookup"><span data-stu-id="234db-126">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>  
  
 <span data-ttu-id="234db-127">La tabella seguente elenca le opzioni di marshalling per le stringhe quando il marshalling viene effettuato come argomento di metodo di una chiamata Platform invoke.</span><span class="sxs-lookup"><span data-stu-id="234db-127">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="234db-128">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe.</span><span class="sxs-lookup"><span data-stu-id="234db-128">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>  
  
|<span data-ttu-id="234db-129">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="234db-129">Enumeration type</span></span>|<span data-ttu-id="234db-130">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="234db-130">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="234db-131">`BSTR` di tipo COM con lunghezza fissa e caratteri ANSI.</span><span class="sxs-lookup"><span data-stu-id="234db-131">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|  
|`UnmanagedType.BStr`|<span data-ttu-id="234db-132">`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="234db-132">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="234db-133">Puntatore a matrice di caratteri ANSI con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="234db-133">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="234db-134">Puntatore a una matrice con terminazione Null di caratteri dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="234db-134">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="234db-135">Puntatore a una matrice con terminazione Null di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="234db-135">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.TBStr`|<span data-ttu-id="234db-136">`BSTR` di tipo COM con lunghezza fissa e caratteri dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="234db-136">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|  
|`VBByRefStr`|<span data-ttu-id="234db-137">Valore che consente a Visual Basic .NET di modificare una stringa in codice non gestito e riflettere i risultati in codice gestito.</span><span class="sxs-lookup"><span data-stu-id="234db-137">A value that enables Visual Basic .NET to change a string in unmanaged code, and have the results reflected in managed code.</span></span> <span data-ttu-id="234db-138">Questo valore è supportato solo per platform invoke.</span><span class="sxs-lookup"><span data-stu-id="234db-138">This value is supported only for platform invoke.</span></span> <span data-ttu-id="234db-139">Si tratta del valore predefinito in Visual Basic per le stringhe `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="234db-139">This is default value in Visual Basic for `ByVal` strings.</span></span>|  
  
 <span data-ttu-id="234db-140">Questa tabella è applicabile alle stringhe.</span><span class="sxs-lookup"><span data-stu-id="234db-140">This table applies to strings.</span></span> <span data-ttu-id="234db-141">Per <xref:System.Text.StringBuilder>, tuttavia, le uniche opzioni consentite sono `LPStr`, `LPTStr` e `LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="234db-141">However, for <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>  
  
 <span data-ttu-id="234db-142">La definizione del tipo seguente mostra l'uso corretto di `MarshalAsAttribute` per chiamate Platform invoke.</span><span class="sxs-lookup"><span data-stu-id="234db-142">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```

```csharp
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a><span data-ttu-id="234db-143">Stringhe usate nelle strutture</span><span class="sxs-lookup"><span data-stu-id="234db-143">Strings Used in Structures</span></span>  
 <span data-ttu-id="234db-144">Le stringhe sono membri validi delle strutture, ma i buffer <xref:System.Text.StringBuilder> non sono validi nelle strutture.</span><span class="sxs-lookup"><span data-stu-id="234db-144">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="234db-145">La tabella seguente illustra le opzioni di marshalling per il tipo di dati stringa quando viene eseguito il marshalling del tipo come campo.</span><span class="sxs-lookup"><span data-stu-id="234db-145">The following table shows the marshaling options for the string data type when the type is marshaled as a field.</span></span> <span data-ttu-id="234db-146">L'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> fornisce alcuni valori di enumerazione <xref:System.Runtime.InteropServices.UnmanagedType> per il marshalling di stringhe in un campo.</span><span class="sxs-lookup"><span data-stu-id="234db-146">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>  
  
|<span data-ttu-id="234db-147">Tipo di enumerazione</span><span class="sxs-lookup"><span data-stu-id="234db-147">Enumeration type</span></span>|<span data-ttu-id="234db-148">Descrizione del formato non gestito</span><span class="sxs-lookup"><span data-stu-id="234db-148">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|<span data-ttu-id="234db-149">`BSTR` di tipo COM con lunghezza fissa e caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="234db-149">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="234db-150">Puntatore a matrice di caratteri ANSI con terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="234db-150">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="234db-151">Puntatore a una matrice con terminazione Null di caratteri dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="234db-151">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="234db-152">Puntatore a una matrice con terminazione Null di caratteri Unicode.</span><span class="sxs-lookup"><span data-stu-id="234db-152">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.ByValTStr`|<span data-ttu-id="234db-153">Matrice di caratteri a lunghezza fissa. Il tipo della matrice viene determinato dal set di carattere della struttura che la contiene.</span><span class="sxs-lookup"><span data-stu-id="234db-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|  
  
 <span data-ttu-id="234db-154">Il tipo `ByValTStr` viene usato per matrici di caratteri inline e di lunghezza fissa, disponibili all'interno di una struttura.</span><span class="sxs-lookup"><span data-stu-id="234db-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="234db-155">Altri tipi sono applicabili a riferimenti di stringa contenuti in strutture che includono puntatori ad altre stringhe.</span><span class="sxs-lookup"><span data-stu-id="234db-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>  
  
 <span data-ttu-id="234db-156">L'argomento `CharSet` dell'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> applicato alla struttura contenitore determina il formato dei caratteri delle stringhe nelle strutture.</span><span class="sxs-lookup"><span data-stu-id="234db-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="234db-157">Le strutture di esempio seguenti contengono riferimenti a stringhe e stringhe inline, oltre a caratteri ANSI, Unicode e dipendenti dalla piattaforma.</span><span class="sxs-lookup"><span data-stu-id="234db-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span>  
  
### <a name="type-library-representation"></a><span data-ttu-id="234db-158">Rappresentazione di libreria dei tipi</span><span class="sxs-lookup"><span data-stu-id="234db-158">Type Library Representation</span></span>  
  
```
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 <span data-ttu-id="234db-159">L'esempio di codice seguente illustra come usare l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> per definire la stessa struttura in formati diversi.</span><span class="sxs-lookup"><span data-stu-id="234db-159">The following code example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to define the same structure in different formats.</span></span>  
  
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
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a><span data-ttu-id="234db-160">Buffer di stringhe di lunghezza fissa</span><span class="sxs-lookup"><span data-stu-id="234db-160">Fixed-Length String Buffers</span></span>  
 <span data-ttu-id="234db-161">In alcuni casi, è necessario passare un buffer di caratteri a lunghezza fissa nel codice non gestito da modificare.</span><span class="sxs-lookup"><span data-stu-id="234db-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="234db-162">Il semplice passaggio di una stringa non funziona in questo caso perché il chiamato non può modificare il contenuto del buffer passato.</span><span class="sxs-lookup"><span data-stu-id="234db-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="234db-163">Anche se la stringa viene passata per riferimento, non è possibile inizializzare il buffer su una dimensione specifica.</span><span class="sxs-lookup"><span data-stu-id="234db-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>  
  
 <span data-ttu-id="234db-164">La soluzione consiste nel passare come argomento un buffer <xref:System.Text.StringBuilder> invece di una stringa.</span><span class="sxs-lookup"><span data-stu-id="234db-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a string.</span></span> <span data-ttu-id="234db-165">Il chiamato può dereferenziare e modificare un oggetto `StringBuilder`, purché non venga superata la capacità dell'oggetto `StringBuilder` stesso.</span><span class="sxs-lookup"><span data-stu-id="234db-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="234db-166">È anche possibile inizializzare questo oggetto in base a una lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="234db-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="234db-167">Se, ad esempio, si inizializza un buffer `StringBuilder` per una capacità pari a `N`, un buffer di caratteri di dimensione (`N`+1) viene fornito dal gestore di marshalling.</span><span class="sxs-lookup"><span data-stu-id="234db-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="234db-168">Il valore +1 tiene conto del fatto che, a differenza di `StringBuilder`, la stringa non gestita ha una terminazione Null.</span><span class="sxs-lookup"><span data-stu-id="234db-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>  
  
 <span data-ttu-id="234db-169">La funzione `GetWindowText` dell'API Microsoft Windows (definita in Windows.h) rappresenta ad esempio un buffer di caratteri a lunghezza fissa che deve essere passato nel codice non gestito per essere modificato.</span><span class="sxs-lookup"><span data-stu-id="234db-169">For example, the Microsoft Windows API `GetWindowText` function (defined in Windows.h) is a fixed-length character buffer that must be passed into unmanaged code to be manipulated.</span></span> `LpString` <span data-ttu-id="234db-170">punta a un buffer allocato dal chiamante di dimensione `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="234db-170">points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="234db-171">Il chiamante deve allocare il buffer e impostare l'argomento `nMaxCount` sulla dimensione del buffer allocato.</span><span class="sxs-lookup"><span data-stu-id="234db-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="234db-172">Il codice seguente illustra la dichiarazione della funzione `GetWindowText` come definita in Windows.h.</span><span class="sxs-lookup"><span data-stu-id="234db-172">The following code shows the `GetWindowText` function declaration as defined in Windows.h.</span></span>  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 <span data-ttu-id="234db-173">Il chiamato può dereferenziare e modificare un oggetto `StringBuilder`, purché non venga superata la capacità dell'oggetto `StringBuilder` stesso.</span><span class="sxs-lookup"><span data-stu-id="234db-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="234db-174">L'esempio di codice seguente illustra come inizializzare `StringBuilder` in base a una lunghezza fissa.</span><span class="sxs-lookup"><span data-stu-id="234db-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="234db-175">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="234db-175">See also</span></span>

- [<span data-ttu-id="234db-176">comportamento predefinito del marshalling</span><span class="sxs-lookup"><span data-stu-id="234db-176">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="234db-177">tipi copiabili e non copiabili</span><span class="sxs-lookup"><span data-stu-id="234db-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- [<span data-ttu-id="234db-178">Attributi direzionali</span><span class="sxs-lookup"><span data-stu-id="234db-178">Directional Attributes</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [<span data-ttu-id="234db-179">copia e blocco</span><span class="sxs-lookup"><span data-stu-id="234db-179">Copying and Pinning</span></span>](copying-and-pinning.md)
