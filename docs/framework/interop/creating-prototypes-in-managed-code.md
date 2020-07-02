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
# <a name="creating-prototypes-in-managed-code"></a>Creazione di prototipi nel codice gestito
Questo argomento descrive come accedere alle funzioni non gestite e introduce diversi campi attributo che annotano la definizione di metodo nel codice gestito. Per alcuni esempi che mostrano come costruire dichiarazioni basate su .NET da usare con platform invoke, vedere , vedere [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md).  
  
 Per accedere a una funzione DLL non gestita dal codice gestito, è necessario conoscere il nome della funzione e il nome della DLL che la esporta. Con queste informazioni, è possibile iniziare a scrivere la definizione gestita per una funzione non gestita implementata in una DLL. È anche possibile modificare il modo in cui platform invoke crea la funzione ed effettua il marshalling dei dati da e verso la funzione.  
  
> [!NOTE]
> Le funzioni API Windows che allocano una stringa consentono di liberare la stringa usando un metodo come `LocalFree`. Platform invoke gestisce tali parametri in modo diverso. Per le chiamate di platform invoke, il parametro deve essere di tipo `IntPtr` anziché di tipo `String`. Usare i metodi forniti dalla classe <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> per convertire manualmente il tipo in una stringa e liberarlo manualmente.  
  
## <a name="declaration-basics"></a>Nozioni di base sulle dichiarazioni  
 Le definizioni gestite di funzioni non gestite sono dipendenti dal linguaggio, come è possibile vedere negli esempi seguenti. Per esempi di codice più completi, vedere [Esempi di platform invoke](platform-invoke-examples.md).  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 Per applicare i campi <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> a una dichiarazione Visual Basic, è necessario usare l'attributo <xref:System.Runtime.InteropServices.DllImportAttribute> anziché l'istruzione `Declare`.  
  
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
  
## <a name="adjusting-the-definition"></a>Modifica della definizione  
 Indipendentemente dal fatto che vengano impostati in modo esplicito o meno, i campi attributo definiscono il comportamento del codice gestito. Platform invoke opera in base ai valori predefiniti impostati in diversi campi presenti come metadati in un assembly. È possibile modificare questo comportamento predefinito modificando i valori di uno o più campi. In molti casi, è possibile usare <xref:System.Runtime.InteropServices.DllImportAttribute> per impostare un valore.  
  
 La tabella seguente elenca il set completo di campi attributo relativi a platform invoke. Per ogni campo, la tabella include il valore predefinito e un collegamento a informazioni su come usare questi campi per definire le funzioni DLL non gestite.  
  
|Campo|Descrizione|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|Abilita o disabilita il mapping più appropriato.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|Specifica la convenzione di chiamata da usare per passare gli argomenti del metodo. Il valore predefinito è `WinAPI`, che corrisponde a `__stdcall` per le piattaforme Intel a 32 bit.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|Controlla la modifica dei nomi e il modo in cui deve essere effettuato il marshalling degli argomenti stringa alla funzione. Il valore predefinito è `CharSet.Ansi`.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|Specifica il punto di ingresso della DLL da chiamare.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|Controlla se un punto di ingresso deve essere modificato per corrispondere al set di caratteri. Il valore predefinito varia in base al linguaggio di programmazione.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|Controlla se la firma del metodo gestito deve essere trasformata in una firma non gestita che restituisce un oggetto HRESULT e dispone di un argomento aggiuntivo [out, retval] per il valore restituito.<br /><br /> Il valore predefinito è `true` (la firma non deve essere trasformata).|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|Consente al chiamante di usare la funzione API `Marshal.GetLastWin32Error` per determinare se si è verificato un errore durante l'esecuzione del metodo. In Visual Basic il valore predefinito è `true`, in C# e C++ il valore predefinito è `false`.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|Controlla la generazione di un'eccezione per un carattere Unicode di cui non è possibile eseguire il mapping convertito in un carattere ANSI "?".|  
  
 Per informazioni di riferimento dettagliate, vedere <xref:System.Runtime.InteropServices.DllImportAttribute>.  
  
## <a name="platform-invoke-security-considerations"></a>Considerazioni sulla sicurezza di platform invoke  
 I membri `Assert`, `Deny` e `PermitOnly` dell'enumerazione <xref:System.Security.Permissions.SecurityAction> sono detti *modificatori di percorso stack*. Questi membri vengono ignorati se vengono usati come attributi dichiarativi in dichiarazioni platform invoke e istruzioni IDL (Interface Definition Language, linguaggio di definizione dell'interfaccia) COM.  
  
### <a name="platform-invoke-examples"></a>Esempi di platform invoke  
 Gli esempi di platform invoke in questa sezione illustrano l'uso dell'attributo `RegistryPermission` con i modificatori di percorso stack.  
  
 Nell'esempio seguente i modificatori <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny` e `PermitOnly` vengono ignorati.  
  
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
  
 Il modificatore `Demand` nell'esempio seguente viene tuttavia accettato.  
  
```csharp
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 I modificatori <xref:System.Security.Permissions.SecurityAction> funzionano correttamente se vengono posizionati in una classe che contiene (esegue il wrapping) la chiamata di platform invoke.  
  
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
  
 I modificatori <xref:System.Security.Permissions.SecurityAction> funzionano correttamente anche in uno scenario annidato in cui vengono posizionati nel chiamante della chiamata di platform invoke:  
  
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
  
#### <a name="com-interop-examples"></a>Esempi di interoperabilità COM  
 Gli esempi di interoperabilità COM in questa sezione illustrano l'uso dell'attributo `RegistryPermission` con i modificatori di percorso stack.  
  
 Le dichiarazioni di interfacce di interoperabilità COM seguenti ignorano i modificatori `Assert`, `Deny` e `PermitOnly`, analogamente agli esempi di platform invoke nella sezione precedente.  
  
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
  
 Inoltre, il modificatore `Demand` non viene accettato negli scenari di dichiarazione di interfacce di interoperabilità COM, come illustrato nell'esempio seguente.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di funzioni di DLL non gestite](consuming-unmanaged-dll-functions.md)
- [Specifica di un punto di ingresso](specifying-an-entry-point.md)
- [Specifica di un set di caratteri](specifying-a-character-set.md)
- [Esempi di platform invoke](platform-invoke-examples.md)
- [Considerazioni sulla sicurezza di platform invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))
- [Identificazione delle funzioni nelle DLL](identifying-functions-in-dlls.md)
- [Creazione di una classe che contenga le funzioni di DLL](creating-a-class-to-hold-dll-functions.md)
- [Chiamata a una funzione di DLL](calling-a-dll-function.md)
