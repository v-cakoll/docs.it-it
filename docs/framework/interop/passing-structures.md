---
title: Passaggio di strutture
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a30905fdcf7063f6ecdae0346c9c5ee39b450be9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="passing-structures"></a><span data-ttu-id="91249-102">Passaggio di strutture</span><span class="sxs-lookup"><span data-stu-id="91249-102">Passing Structures</span></span>
<span data-ttu-id="91249-103">Molte funzioni non gestite prevedono il passaggio, come parametro della funzione, di membri di strutture (tipi definiti dall'utente in Visual Basic) o membri di classi definiti nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="91249-103">Many unmanaged functions expect you to pass, as a parameter to the function, members of structures (user-defined types in Visual Basic) or members of classes that are defined in managed code.</span></span> <span data-ttu-id="91249-104">Quando si passano strutture o classi al codice non gestito mediante platform invoke, è necessario fornire informazioni aggiuntive per mantenere il layout e l'allineamento originali.</span><span class="sxs-lookup"><span data-stu-id="91249-104">When passing structures or classes to unmanaged code using platform invoke, you must provide additional information to preserve the original layout and alignment.</span></span> <span data-ttu-id="91249-105">In questo argomento viene presentato l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>, usato per definire i tipi formattati.</span><span class="sxs-lookup"><span data-stu-id="91249-105">This topic introduces the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute, which you use to define formatted types.</span></span> <span data-ttu-id="91249-106">Per le classi e le strutture gestite, è possibile selezionare tra diversi comportamenti di layout prevedibili forniti dall'enumerazione **LayoutKind**.</span><span class="sxs-lookup"><span data-stu-id="91249-106">For managed structures and classes, you can select from several predictable layout behaviors supplied by the **LayoutKind** enumeration.</span></span>  
  
 <span data-ttu-id="91249-107">Un aspetto fondamentale per i concetti presentati in questo argomento è l'importante differenza esistente tra i tipi di strutture e classi.</span><span class="sxs-lookup"><span data-stu-id="91249-107">Central to the concepts presented in this topic is an important difference between structure and class types.</span></span> <span data-ttu-id="91249-108">Le strutture sono tipi valore e le classi sono tipi riferimento. Le classi forniscono sempre almeno un livello di riferimento indiretto di memoria (un puntatore a un valore).</span><span class="sxs-lookup"><span data-stu-id="91249-108">Structures are value types and classes are reference types — classes always provide at least one level of memory indirection (a pointer to a value).</span></span> <span data-ttu-id="91249-109">Questa differenza è importante perché le funzioni non gestite spesso richiedono riferimenti indiretti, come illustrato dalle firme nella prima colonna della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="91249-109">This difference is important because unmanaged functions often demand indirection, as shown by the signatures in the first column of the following table.</span></span> <span data-ttu-id="91249-110">La struttura gestita e le dichiarazioni di classe nelle colonne rimanenti mostrano il grado di cui è possibile modificare il livello di riferimento indiretto nella dichiarazione. Le dichiarazioni sono disponibili sia per Visual Basic che per Visual C#.</span><span class="sxs-lookup"><span data-stu-id="91249-110">The managed structure and class declarations in the remaining columns show the degree to which you can adjust the level of indirection in your declaration.Declarations are provided for both Visual Basic and Visual C#.</span></span>  
  
|<span data-ttu-id="91249-111">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="91249-111">Unmanaged signature</span></span>|<span data-ttu-id="91249-112">Dichiarazione gestita:</span><span class="sxs-lookup"><span data-stu-id="91249-112">Managed declaration:</span></span> <br /><span data-ttu-id="91249-113">nessun riferimento indiretto</span><span class="sxs-lookup"><span data-stu-id="91249-113">no indirection</span></span><br />`Structure MyType`<br />`struct MyType;`|<span data-ttu-id="91249-114">Dichiarazione gestita:</span><span class="sxs-lookup"><span data-stu-id="91249-114">Managed declaration:</span></span> <br /><span data-ttu-id="91249-115">un livello di riferimento indiretto</span><span class="sxs-lookup"><span data-stu-id="91249-115">one level of indirection</span></span><br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> <span data-ttu-id="91249-116">Richiede zero livelli di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-116">Demands zero levels of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="91249-117">Non aggiunge alcun livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-117">Adds zero levels of indirection.</span></span>|<span data-ttu-id="91249-118">Non possibile perché esiste già un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-118">Not possible because there is already one level of indirection.</span></span>|  
|`DoWork(MyType* x);`<br /><br /> <span data-ttu-id="91249-119">Richiede un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-119">Demands one level of indirection.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="91249-120">Aggiunge un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-120">Adds one level of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="91249-121">Non aggiunge alcun livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-121">Adds zero levels of indirection.</span></span>|  
|`DoWork(MyType** x);`<br /><br /> <span data-ttu-id="91249-122">Richiede due livelli di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-122">Demands two levels of indirection.</span></span>|<span data-ttu-id="91249-123">Impossibile perché non è possibile usare **ByRef** **ByRef** o `ref` `ref`.</span><span class="sxs-lookup"><span data-stu-id="91249-123">Not possible because **ByRef** **ByRef** or `ref` `ref` cannot be used.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="91249-124">Aggiunge un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-124">Adds one level of indirection.</span></span>|  
  
 <span data-ttu-id="91249-125">La tabella descrive le linee guida seguenti per le dichiarazioni di platform invoke:</span><span class="sxs-lookup"><span data-stu-id="91249-125">The table describes the following guidelines for platform invoke declarations:</span></span>  
  
-   <span data-ttu-id="91249-126">Usare una struttura passata per valore quando la funzione non gestita non richiede alcun riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-126">Use a structure passed by value when the unmanaged function demands no indirection.</span></span>  
  
-   <span data-ttu-id="91249-127">Usare una struttura passata per riferimento o una classe passata per valore quando la funzione non gestita richiede un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-127">Use either a structure passed by reference or a class passed by value when the unmanaged function demands one level of indirection.</span></span>  
  
-   <span data-ttu-id="91249-128">Usare una classe passata per riferimento quando la funzione non gestita richiede due livelli di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-128">Use a class passed by reference when the unmanaged function demands two levels of indirection.</span></span>  
  
## <a name="declaring-and-passing-structures"></a><span data-ttu-id="91249-129">Dichiarazione e passaggio di strutture</span><span class="sxs-lookup"><span data-stu-id="91249-129">Declaring and Passing Structures</span></span>  
 <span data-ttu-id="91249-130">L'esempio seguente mostra come definire le strutture `Point` e `Rect` nel codice gestito e passare i tipi come parametro alla funzione **PtInRect** nel file User32.dll.</span><span class="sxs-lookup"><span data-stu-id="91249-130">The following example shows how to define the `Point` and `Rect` structures in managed code, and pass the types as parameter to the **PtInRect** function in the User32.dll file.</span></span> <span data-ttu-id="91249-131">**PtInRect** include la firma non gestita seguente:</span><span class="sxs-lookup"><span data-stu-id="91249-131">**PtInRect** has the following unmanaged signature:</span></span>  
  
```  
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="91249-132">Si noti che è necessario passare la struttura Rect per riferimento, perché la funzione si aspetta un puntatore a un tipo RECT.</span><span class="sxs-lookup"><span data-stu-id="91249-132">Notice that you must pass the Rect structure by reference, since the function expects a pointer to a RECT type.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Class Win32API      
    Declare Auto Function PtInRect Lib "user32.dll" _  
    (ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}     
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}     
  
class Win32API {  
    [DllImport("User32.dll")]  
    public static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a><span data-ttu-id="91249-133">Dichiarazione e passaggio di classi</span><span class="sxs-lookup"><span data-stu-id="91249-133">Declaring and Passing Classes</span></span>  
 <span data-ttu-id="91249-134">È possibile passare i membri di una classe a una funzione DLL non gestita, a condizione che la classe abbia un layout di membri fisso.</span><span class="sxs-lookup"><span data-stu-id="91249-134">You can pass members of a class to an unmanaged DLL function, as long as the class has a fixed member layout.</span></span> <span data-ttu-id="91249-135">L'esempio seguente dimostra come passare membri alla classe `MySystemTime`, definiti in ordine sequenziale, a **GetSystemTime** nel file User32.dll.</span><span class="sxs-lookup"><span data-stu-id="91249-135">The following example demonstrates how to pass members of the `MySystemTime` class, which are defined in sequential order, to the **GetSystemTime** in the User32.dll file.</span></span> <span data-ttu-id="91249-136">**GetSystemTime** include la firma non gestita seguente:</span><span class="sxs-lookup"><span data-stu-id="91249-136">**GetSystemTime** has the following unmanaged signature:</span></span>  
  
```  
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="91249-137">Diversamente dai tipi valore, le classi hanno sempre almeno un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="91249-137">Unlike value types, classes always have at least one level of indirection.</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
Imports Microsoft.VisualBasic  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short   
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Public Class Win32  
    Declare Auto Sub GetSystemTime Lib "Kernel32.dll"(sysTime _  
        As MySystemTime)  
    Declare Auto Function MessageBox Lib "User32.dll"(hWnd As IntPtr, _  
        txt As String, caption As String, Typ As Integer) As Integer  
End Class  
  
Public Class TestPlatformInvoke      
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        Win32.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        Win32.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)        
    End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;   
    public ushort wMonth;  
    public ushort wDayOfWeek;   
    public ushort wDay;   
    public ushort wHour;   
    public ushort wMinute;   
    public ushort wSecond;   
    public ushort wMilliseconds;   
}  
class Win32API {  
    [DllImport("Kernel32.dll")]  
    public static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern int MessageBox(IntPtr hWnd,  
         string text, string caption, int options);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        Win32API.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        Win32API.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="91249-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91249-138">See Also</span></span>  
 [<span data-ttu-id="91249-139">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="91249-139">Calling a DLL Function</span></span>](../../../docs/framework/interop/calling-a-dll-function.md)  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
