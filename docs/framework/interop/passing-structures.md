---
title: Passaggio di strutture
description: Informazioni su come passare le strutture e le classi alle funzioni non gestite. Informazioni sull'attributo StructLayoutAttribute, che è possibile usare per definire i tipi formattati.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
ms.openlocfilehash: eae28d6746cd89d98b659b9eb957f158e1319190
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620820"
---
# <a name="passing-structures"></a><span data-ttu-id="1667a-104">Passaggio di strutture</span><span class="sxs-lookup"><span data-stu-id="1667a-104">Passing Structures</span></span>
<span data-ttu-id="1667a-105">Molte funzioni non gestite prevedono il passaggio, come parametro della funzione, di membri di strutture (tipi definiti dall'utente in Visual Basic) o membri di classi definiti nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1667a-105">Many unmanaged functions expect you to pass, as a parameter to the function, members of structures (user-defined types in Visual Basic) or members of classes that are defined in managed code.</span></span> <span data-ttu-id="1667a-106">Quando si passano strutture o classi al codice non gestito mediante platform invoke, è necessario fornire informazioni aggiuntive per mantenere il layout e l'allineamento originali.</span><span class="sxs-lookup"><span data-stu-id="1667a-106">When passing structures or classes to unmanaged code using platform invoke, you must provide additional information to preserve the original layout and alignment.</span></span> <span data-ttu-id="1667a-107">In questo argomento viene presentato l'attributo <xref:System.Runtime.InteropServices.StructLayoutAttribute>, usato per definire i tipi formattati.</span><span class="sxs-lookup"><span data-stu-id="1667a-107">This topic introduces the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute, which you use to define formatted types.</span></span> <span data-ttu-id="1667a-108">Per le classi e le strutture gestite, è possibile selezionare tra diversi comportamenti di layout prevedibili forniti dall'enumerazione **LayoutKind**.</span><span class="sxs-lookup"><span data-stu-id="1667a-108">For managed structures and classes, you can select from several predictable layout behaviors supplied by the **LayoutKind** enumeration.</span></span>  
  
 <span data-ttu-id="1667a-109">Un aspetto fondamentale per i concetti presentati in questo argomento è l'importante differenza esistente tra i tipi di strutture e classi.</span><span class="sxs-lookup"><span data-stu-id="1667a-109">Central to the concepts presented in this topic is an important difference between structure and class types.</span></span> <span data-ttu-id="1667a-110">Le strutture sono tipi valore e le classi sono tipi riferimento. Le classi forniscono sempre almeno un livello di riferimento indiretto di memoria (un puntatore a un valore).</span><span class="sxs-lookup"><span data-stu-id="1667a-110">Structures are value types and classes are reference types — classes always provide at least one level of memory indirection (a pointer to a value).</span></span> <span data-ttu-id="1667a-111">Questa differenza è importante perché le funzioni non gestite spesso richiedono riferimenti indiretti, come illustrato dalle firme nella prima colonna della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1667a-111">This difference is important because unmanaged functions often demand indirection, as shown by the signatures in the first column of the following table.</span></span> <span data-ttu-id="1667a-112">La struttura gestita e le dichiarazioni di classe nelle colonne rimanenti mostrano il grado di cui è possibile modificare il livello di riferimento indiretto nella dichiarazione. Le dichiarazioni sono disponibili sia per Visual Basic che per Visual C#.</span><span class="sxs-lookup"><span data-stu-id="1667a-112">The managed structure and class declarations in the remaining columns show the degree to which you can adjust the level of indirection in your declaration.Declarations are provided for both Visual Basic and Visual C#.</span></span>  
  
|<span data-ttu-id="1667a-113">Firma non gestita</span><span class="sxs-lookup"><span data-stu-id="1667a-113">Unmanaged signature</span></span>|<span data-ttu-id="1667a-114">Dichiarazione gestita:</span><span class="sxs-lookup"><span data-stu-id="1667a-114">Managed declaration:</span></span> <br /><span data-ttu-id="1667a-115">nessun riferimento indiretto</span><span class="sxs-lookup"><span data-stu-id="1667a-115">no indirection</span></span><br />`Structure MyType`<br />`struct MyType;`|<span data-ttu-id="1667a-116">Dichiarazione gestita:</span><span class="sxs-lookup"><span data-stu-id="1667a-116">Managed declaration:</span></span> <br /><span data-ttu-id="1667a-117">un livello di riferimento indiretto</span><span class="sxs-lookup"><span data-stu-id="1667a-117">one level of indirection</span></span><br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> <span data-ttu-id="1667a-118">Richiede zero livelli di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-118">Demands zero levels of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="1667a-119">Non aggiunge alcun livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-119">Adds zero levels of indirection.</span></span>|<span data-ttu-id="1667a-120">Non possibile perché esiste già un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-120">Not possible because there is already one level of indirection.</span></span>|  
|`DoWork(MyType* x);`<br /><br /> <span data-ttu-id="1667a-121">Richiede un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-121">Demands one level of indirection.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="1667a-122">Aggiunge un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-122">Adds one level of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="1667a-123">Non aggiunge alcun livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-123">Adds zero levels of indirection.</span></span>|  
|`DoWork(MyType** x);`<br /><br /> <span data-ttu-id="1667a-124">Richiede due livelli di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-124">Demands two levels of indirection.</span></span>|<span data-ttu-id="1667a-125">Impossibile perché non è possibile usare **ByRef** **ByRef** o `ref` `ref`.</span><span class="sxs-lookup"><span data-stu-id="1667a-125">Not possible because **ByRef** **ByRef** or `ref` `ref` cannot be used.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="1667a-126">Aggiunge un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-126">Adds one level of indirection.</span></span>|  
  
 <span data-ttu-id="1667a-127">La tabella descrive le linee guida seguenti per le dichiarazioni di platform invoke:</span><span class="sxs-lookup"><span data-stu-id="1667a-127">The table describes the following guidelines for platform invoke declarations:</span></span>  
  
- <span data-ttu-id="1667a-128">Usare una struttura passata per valore quando la funzione non gestita non richiede alcun riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-128">Use a structure passed by value when the unmanaged function demands no indirection.</span></span>  
  
- <span data-ttu-id="1667a-129">Usare una struttura passata per riferimento o una classe passata per valore quando la funzione non gestita richiede un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-129">Use either a structure passed by reference or a class passed by value when the unmanaged function demands one level of indirection.</span></span>  
  
- <span data-ttu-id="1667a-130">Usare una classe passata per riferimento quando la funzione non gestita richiede due livelli di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-130">Use a class passed by reference when the unmanaged function demands two levels of indirection.</span></span>  
  
## <a name="declaring-and-passing-structures"></a><span data-ttu-id="1667a-131">Dichiarazione e passaggio di strutture</span><span class="sxs-lookup"><span data-stu-id="1667a-131">Declaring and Passing Structures</span></span>  
 <span data-ttu-id="1667a-132">L'esempio seguente mostra come definire le strutture `Point` e `Rect` nel codice gestito e passare i tipi come parametro alla funzione **PtInRect** nel file User32.dll.</span><span class="sxs-lookup"><span data-stu-id="1667a-132">The following example shows how to define the `Point` and `Rect` structures in managed code, and pass the types as parameter to the **PtInRect** function in the User32.dll file.</span></span> <span data-ttu-id="1667a-133">**PtInRect** include la firma non gestita seguente:</span><span class="sxs-lookup"><span data-stu-id="1667a-133">**PtInRect** has the following unmanaged signature:</span></span>  
  
```cpp
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="1667a-134">Si noti che è necessario passare la struttura Rect per riferimento, perché la funzione si aspetta un puntatore a un tipo RECT.</span><span class="sxs-lookup"><span data-stu-id="1667a-134">Notice that you must pass the Rect structure by reference, since the function expects a pointer to a RECT type.</span></span>  
  
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
  
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "user32.dll" (
        ByRef r As Rect, p As Point) As Boolean  
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
  
internal static class NativeMethods
{  
    [DllImport("User32.dll")]  
    internal static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a><span data-ttu-id="1667a-135">Dichiarazione e passaggio di classi</span><span class="sxs-lookup"><span data-stu-id="1667a-135">Declaring and Passing Classes</span></span>  
 <span data-ttu-id="1667a-136">È possibile passare i membri di una classe a una funzione DLL non gestita, a condizione che la classe abbia un layout di membri fisso.</span><span class="sxs-lookup"><span data-stu-id="1667a-136">You can pass members of a class to an unmanaged DLL function, as long as the class has a fixed member layout.</span></span> <span data-ttu-id="1667a-137">L'esempio seguente dimostra come passare membri alla classe `MySystemTime`, definiti in ordine sequenziale, a **GetSystemTime** nel file User32.dll.</span><span class="sxs-lookup"><span data-stu-id="1667a-137">The following example demonstrates how to pass members of the `MySystemTime` class, which are defined in sequential order, to the **GetSystemTime** in the User32.dll file.</span></span> <span data-ttu-id="1667a-138">**GetSystemTime** include la firma non gestita seguente:</span><span class="sxs-lookup"><span data-stu-id="1667a-138">**GetSystemTime** has the following unmanaged signature:</span></span>  
  
```cpp
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="1667a-139">Diversamente dai tipi valore, le classi hanno sempre almeno un livello di riferimento indiretto.</span><span class="sxs-lookup"><span data-stu-id="1667a-139">Unlike value types, classes always have at least one level of indirection.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
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
  
Friend Class NativeMethods  
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        sysTime As MySystemTime)  
    Friend Declare Auto Function MessageBox Lib "User32.dll" (
        hWnd As IntPtr, lpText As String, lpCaption As String, uType As UInteger) As Integer  
End Class  
  
Public Class TestPlatformInvoke
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        NativeMethods.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)
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
internal static class NativeMethods
{  
    [DllImport("Kernel32.dll")]  
    internal static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet = CharSet.Auto)]  
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        NativeMethods.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1667a-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1667a-140">See also</span></span>

- [<span data-ttu-id="1667a-141">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="1667a-141">Calling a DLL Function</span></span>](calling-a-dll-function.md)
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
