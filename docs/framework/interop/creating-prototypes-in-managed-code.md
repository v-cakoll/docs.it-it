---
title: Creazione di prototipi nel codice gestito
description: Creare prototipi nel codice gestito .NET, in modo da poter accedere alle funzioni non gestite e usare campi attributo che annotano la definizione di metodo nel codice gestito.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- prototypes in managed code
- COM interop, DLL functions
- unmanaged functions
- platform invoke, creating prototypes
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, object fields
- DLL functions
- object fields in platform invoke
ms.assetid: ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d
ms.openlocfilehash: 76b1a87c4513fdee21c5c3d5eba533b11e022e3a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622159"
---
# <a name="creating-prototypes-in-managed-code"></a><span data-ttu-id="5032a-103">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="5032a-103">Creating Prototypes in Managed Code</span></span>
<span data-ttu-id="5032a-104">Questo argomento descrive come accedere alle funzioni non gestite e introduce diversi campi attributo che annotano la definizione di metodo nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5032a-104">This topic describes how to access unmanaged functions and introduces several attribute fields that annotate method definition in managed code.</span></span> <span data-ttu-id="5032a-105">Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="5032a-105">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
 <span data-ttu-id="5032a-106">Per accedere a una funzione DLL non gestita dal codice gestito, è necessario conoscere il nome della funzione e il nome della DLL che la esporta.</span><span class="sxs-lookup"><span data-stu-id="5032a-106">Before you can access an unmanaged DLL function from managed code, you need to know the name of the function and the name of the DLL that exports it.</span></span> <span data-ttu-id="5032a-107">Con queste informazioni, è possibile iniziare a scrivere la definizione gestita per una funzione non gestita implementata in una DLL.</span><span class="sxs-lookup"><span data-stu-id="5032a-107">With this information, you can begin to write the managed definition for an unmanaged function that is implemented in a DLL.</span></span> <span data-ttu-id="5032a-108">È anche possibile modificare il modo in cui platform invoke crea la funzione ed effettua il marshalling dei dati da e verso la funzione.</span><span class="sxs-lookup"><span data-stu-id="5032a-108">Furthermore, you can adjust the way that platform invoke creates the function and marshals data to and from the function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5032a-109">Le funzioni API Windows che allocano una stringa consentono di liberare la stringa usando un metodo come `LocalFree`.</span><span class="sxs-lookup"><span data-stu-id="5032a-109">Windows API functions that allocate a string enable you to free the string by using a method such as `LocalFree`.</span></span> <span data-ttu-id="5032a-110">Platform invoke gestisce tali parametri in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="5032a-110">Platform invoke handles such parameters differently.</span></span> <span data-ttu-id="5032a-111">Per le chiamate di platform invoke, il parametro deve essere di tipo `IntPtr` anziché di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="5032a-111">For platform invoke calls, make the parameter an `IntPtr` type instead of a `String` type.</span></span> <span data-ttu-id="5032a-112">Usare i metodi forniti dalla classe <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> per convertire manualmente il tipo in una stringa e liberarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="5032a-112">Use methods that are provided by the <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> class to convert the type to a string manually and free it manually.</span></span>  
  
## <a name="declaration-basics"></a><span data-ttu-id="5032a-113">Nozioni di base sulle dichiarazioni</span><span class="sxs-lookup"><span data-stu-id="5032a-113">Declaration Basics</span></span>  
 <span data-ttu-id="5032a-114">Le definizioni gestite di funzioni non gestite sono dipendenti dal linguaggio, come è possibile vedere negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="5032a-114">Managed definitions to unmanaged functions are language-dependent, as you can see in the following examples.</span></span> <span data-ttu-id="5032a-115">Per esempi di codice più completi, vedere [Esempi di platform invoke](platform-invoke-examples.md).</span><span class="sxs-lookup"><span data-stu-id="5032a-115">For more complete code examples, see [Platform Invoke Examples](platform-invoke-examples.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 <span data-ttu-id="5032a-116">Per applicare i campi <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> a una dichiarazione Visual Basic, è necessario usare l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> anziché l'istruzione `Declare`.</span><span class="sxs-lookup"><span data-stu-id="5032a-116">To apply the <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType>, or <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> fields to a Visual Basic declaration, you must use the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute instead of the `Declare` statement.</span></span>  
  
```vb
Imports System.Runtime.InteropServices

Friend Class NativeMethods
    <DllImport("user32.dll", CharSet:=CharSet.Auto)>
    Friend Shared Function MessageBox(
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
    End Function
End Class
```
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("user32.dll")]
extern "C" int MessageBox(
    IntPtr hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="adjusting-the-definition"></a><span data-ttu-id="5032a-117">Modifica della definizione</span><span class="sxs-lookup"><span data-stu-id="5032a-117">Adjusting the Definition</span></span>  
 <span data-ttu-id="5032a-118">Indipendentemente dal fatto che vengano impostati in modo esplicito o meno, i campi attributo definiscono il comportamento del codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5032a-118">Whether you set them explicitly or not, attribute fields are at work defining the behavior of managed code.</span></span> <span data-ttu-id="5032a-119">Platform invoke opera in base ai valori predefiniti impostati in diversi campi presenti come metadati in un assembly.</span><span class="sxs-lookup"><span data-stu-id="5032a-119">Platform invoke operates according to the default values set on various fields that exist as metadata in an assembly.</span></span> <span data-ttu-id="5032a-120">È possibile modificare questo comportamento predefinito modificando i valori di uno o più campi.</span><span class="sxs-lookup"><span data-stu-id="5032a-120">You can alter this default behavior by adjusting the values of one or more fields.</span></span> <span data-ttu-id="5032a-121">In molti casi, è possibile usare <xref:System.Runtime.InteropServices.DllImportAttribute> per impostare un valore.</span><span class="sxs-lookup"><span data-stu-id="5032a-121">In many cases, you use the <xref:System.Runtime.InteropServices.DllImportAttribute> to set a value.</span></span>  
  
 <span data-ttu-id="5032a-122">La tabella seguente elenca il set completo di campi attributo relativi a platform invoke.</span><span class="sxs-lookup"><span data-stu-id="5032a-122">The following table lists the complete set of attribute fields that pertain to platform invoke.</span></span> <span data-ttu-id="5032a-123">Per ogni campo, la tabella include il valore predefinito e un collegamento a informazioni su come usare questi campi per definire le funzioni DLL non gestite.</span><span class="sxs-lookup"><span data-stu-id="5032a-123">For each field, the table includes the default value and a link to information on how to use these fields to define unmanaged DLL functions.</span></span>  
  
|<span data-ttu-id="5032a-124">Campo</span><span class="sxs-lookup"><span data-stu-id="5032a-124">Field</span></span>|<span data-ttu-id="5032a-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5032a-125">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|<span data-ttu-id="5032a-126">Abilita o disabilita il mapping più appropriato.</span><span class="sxs-lookup"><span data-stu-id="5032a-126">Enables or disables best-fit mapping.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|<span data-ttu-id="5032a-127">Specifica la convenzione di chiamata da usare per passare gli argomenti del metodo.</span><span class="sxs-lookup"><span data-stu-id="5032a-127">Specifies the calling convention to use in passing method arguments.</span></span> <span data-ttu-id="5032a-128">Il valore predefinito è `WinAPI`, che corrisponde a `__stdcall` per le piattaforme Intel a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="5032a-128">The default is `WinAPI`, which corresponds to `__stdcall` for the 32-bit Intel-based platforms.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|<span data-ttu-id="5032a-129">Controlla la modifica dei nomi e il modo in cui deve essere effettuato il marshalling degli argomenti stringa alla funzione.</span><span class="sxs-lookup"><span data-stu-id="5032a-129">Controls name mangling and the way that string arguments should be marshaled to the function.</span></span> <span data-ttu-id="5032a-130">Il valore predefinito è `CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="5032a-130">The default is `CharSet.Ansi`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|<span data-ttu-id="5032a-131">Specifica il punto di ingresso della DLL da chiamare.</span><span class="sxs-lookup"><span data-stu-id="5032a-131">Specifies the DLL entry point to be called.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|<span data-ttu-id="5032a-132">Controlla se un punto di ingresso deve essere modificato per corrispondere al set di caratteri.</span><span class="sxs-lookup"><span data-stu-id="5032a-132">Controls whether an entry point should be modified to correspond to the character set.</span></span> <span data-ttu-id="5032a-133">Il valore predefinito varia in base al linguaggio di programmazione.</span><span class="sxs-lookup"><span data-stu-id="5032a-133">The default value varies by programming language.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|<span data-ttu-id="5032a-134">Controlla se la firma del metodo gestito deve essere trasformata in una firma non gestita che restituisce un oggetto HRESULT e dispone di un argomento aggiuntivo [out, retval] per il valore restituito.</span><span class="sxs-lookup"><span data-stu-id="5032a-134">Controls whether the managed method signature should be transformed into an unmanaged signature that returns an HRESULT and has an additional [out, retval] argument for the return value.</span></span><br /><br /> <span data-ttu-id="5032a-135">Il valore predefinito è `true` (la firma non deve essere trasformata).</span><span class="sxs-lookup"><span data-stu-id="5032a-135">The default is `true` (the signature should not be transformed).</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|<span data-ttu-id="5032a-136">Consente al chiamante di usare la funzione API `Marshal.GetLastWin32Error` per determinare se si è verificato un errore durante l'esecuzione del metodo.</span><span class="sxs-lookup"><span data-stu-id="5032a-136">Enables the caller to use the `Marshal.GetLastWin32Error` API function to determine whether an error occurred while executing the method.</span></span> <span data-ttu-id="5032a-137">In Visual Basic il valore predefinito è `true`, in C# e C++ il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="5032a-137">In Visual Basic, the default is `true`; in C# and C++, the default is `false`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|<span data-ttu-id="5032a-138">Controlla la generazione di un'eccezione per un carattere Unicode di cui non è possibile eseguire il mapping convertito in un carattere ANSI "?".</span><span class="sxs-lookup"><span data-stu-id="5032a-138">Controls throwing of an exception on an unmappable Unicode character that is converted to an ANSI "?" character.</span></span>|  
  
 <span data-ttu-id="5032a-139">Per informazioni di riferimento dettagliate, vedere <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5032a-139">For detailed reference information, see <xref:System.Runtime.InteropServices.DllImportAttribute>.</span></span>  
  
## <a name="platform-invoke-security-considerations"></a><span data-ttu-id="5032a-140">Considerazioni sulla sicurezza di platform invoke</span><span class="sxs-lookup"><span data-stu-id="5032a-140">Platform invoke security considerations</span></span>  
 <span data-ttu-id="5032a-141">I membri `Assert`, `Deny` e `PermitOnly` dell'enumerazione <xref:System.Security.Permissions.SecurityAction> sono detti *modificatori di percorso stack*.</span><span class="sxs-lookup"><span data-stu-id="5032a-141">The `Assert`, `Deny`, and `PermitOnly` members of the <xref:System.Security.Permissions.SecurityAction> enumeration are referred to as *stack walk modifiers*.</span></span> <span data-ttu-id="5032a-142">Questi membri vengono ignorati se vengono usati come attributi dichiarativi in dichiarazioni platform invoke e istruzioni IDL (Interface Definition Language, linguaggio di definizione dell'interfaccia) COM.</span><span class="sxs-lookup"><span data-stu-id="5032a-142">These members are ignored if they are used as declarative attributes on platform invoke declarations and COM Interface Definition Language (IDL) statements.</span></span>  
  
### <a name="platform-invoke-examples"></a><span data-ttu-id="5032a-143">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="5032a-143">Platform Invoke Examples</span></span>  
 <span data-ttu-id="5032a-144">Gli esempi di platform invoke in questa sezione illustrano l'uso dell'attributo `RegistryPermission` con i modificatori di percorso stack.</span><span class="sxs-lookup"><span data-stu-id="5032a-144">The platform invoke samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="5032a-145">Nell'esempio seguente i modificatori <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny` e `PermitOnly` vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="5032a-145">In the following example, the <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny`, and `PermitOnly` modifiers are ignored.</span></span>  
  
```csharp  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionAssert();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="5032a-146">Il modificatore `Demand` nell'esempio seguente viene tuttavia accettato.</span><span class="sxs-lookup"><span data-stu-id="5032a-146">However, the `Demand` modifier in the following example is accepted.</span></span>  
  
```csharp
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="5032a-147">I modificatori <xref:System.Security.Permissions.SecurityAction> funzionano correttamente se vengono posizionati in una classe che contiene (esegue il wrapping) la chiamata di platform invoke.</span><span class="sxs-lookup"><span data-stu-id="5032a-147"><xref:System.Security.Permissions.SecurityAction> modifiers do work correctly if they are placed on a class that contains (wraps) the platform invoke call.</span></span>  
  
```cpp  
      [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
public ref class PInvokeWrapper  
{  
public:  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
};  
```  
  
```csharp  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
class PInvokeWrapper  
{  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
}  
```  
  
 <span data-ttu-id="5032a-148">I modificatori <xref:System.Security.Permissions.SecurityAction> funzionano correttamente anche in uno scenario annidato in cui vengono posizionati nel chiamante della chiamata di platform invoke:</span><span class="sxs-lookup"><span data-stu-id="5032a-148"><xref:System.Security.Permissions.SecurityAction> modifiers also work correctly in a nested scenario where they are placed on the caller of the platform invoke call:</span></span>  
  
```cpp  
      {  
public ref class PInvokeWrapper  
public:  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
  
    [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
};  
```  
  
```csharp  
class PInvokeScenario  
{  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionInternal();  
  
    [RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
}  
```  
  
#### <a name="com-interop-examples"></a><span data-ttu-id="5032a-149">Esempi di interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="5032a-149">COM Interop Examples</span></span>  
 <span data-ttu-id="5032a-150">Gli esempi di interoperabilità COM in questa sezione illustrano l'uso dell'attributo `RegistryPermission` con i modificatori di percorso stack.</span><span class="sxs-lookup"><span data-stu-id="5032a-150">The COM interop samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="5032a-151">Le dichiarazioni di interfacce di interoperabilità COM seguenti ignorano i modificatori `Assert`, `Deny` e `PermitOnly`, analogamente agli esempi di platform invoke nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="5032a-151">The following COM interop interface declarations ignore the `Assert`, `Deny`, and `PermitOnly` modifiers, similarly to the platform invoke examples in the previous section.</span></span>  
  
```csharp
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDenyStubsItf  
{  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
 <span data-ttu-id="5032a-152">Inoltre, il modificatore `Demand` non viene accettato negli scenari di dichiarazione di interfacce di interoperabilità COM, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5032a-152">Additionally, the `Demand` modifier is not accepted in COM interop interface declaration scenarios, as shown in the following example.</span></span>  
  
```csharp  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDemandStubsItf  
{  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="5032a-153">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5032a-153">See also</span></span>

- [<span data-ttu-id="5032a-154">Utilizzo di funzioni di DLL non gestite</span><span class="sxs-lookup"><span data-stu-id="5032a-154">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="5032a-155">Specifica di un punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="5032a-155">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="5032a-156">Specifica di un set di caratteri</span><span class="sxs-lookup"><span data-stu-id="5032a-156">Specifying a Character Set</span></span>](specifying-a-character-set.md)
- [<span data-ttu-id="5032a-157">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="5032a-157">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- <span data-ttu-id="5032a-158">[Considerazioni sulla sicurezza di platform invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5032a-158">[Platform Invoke Security Considerations](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span></span>
- [<span data-ttu-id="5032a-159">Identificazione delle funzioni nelle DLL</span><span class="sxs-lookup"><span data-stu-id="5032a-159">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="5032a-160">Creazione di una classe che contenga le funzioni di DLL</span><span class="sxs-lookup"><span data-stu-id="5032a-160">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="5032a-161">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="5032a-161">Calling a DLL Function</span></span>](calling-a-dll-function.md)
