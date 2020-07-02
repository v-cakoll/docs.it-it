---
title: 'Procedura: Implementare funzioni di callback'
description: Vedere come implementare funzioni di callback. In questo esempio, un'applicazione gestita, usando platform invoke, stampa il valore dell'handle per ogni finestra in un computer.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- callback function, implementing
ms.assetid: e55b3712-b9ea-4453-bd9a-ad5cfa2f6bfa
ms.openlocfilehash: 31c657372e760c8d57f9714b20178967ad85fcd3
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619117"
---
# <a name="how-to-implement-callback-functions"></a><span data-ttu-id="8b7a7-104">Procedura: Implementare funzioni di callback</span><span class="sxs-lookup"><span data-stu-id="8b7a7-104">How to: Implement Callback Functions</span></span>
<span data-ttu-id="8b7a7-105">La procedura e l'esempio seguenti illustrano come un'applicazione gestita, usando il platform invoke, può stampare il valore di handle per ogni finestra sul computer locale.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-105">The following procedure and example demonstrate how a managed application, using platform invoke, can print the handle value for each window on the local computer.</span></span> <span data-ttu-id="8b7a7-106">In particolare, la procedura e l'esempio usano la funzione **EnumWindows** per esaminare l'elenco di finestre e una funzione di callback gestita (denominata CallBack) per visualizzare il valore di handle della finestra.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-106">Specifically, the procedure and example use the **EnumWindows** function to step through the list of windows and a managed callback function (named CallBack) to print the value of the window handle.</span></span>  
  
### <a name="to-implement-a-callback-function"></a><span data-ttu-id="8b7a7-107">Per implementare una funzione di callback</span><span class="sxs-lookup"><span data-stu-id="8b7a7-107">To implement a callback function</span></span>  
  
1. <span data-ttu-id="8b7a7-108">Esaminare la firma per la funzione **EnumWindows** prima di procedere con l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-108">Look at the signature for the **EnumWindows** function before going further with the implementation.</span></span> <span data-ttu-id="8b7a7-109">**EnumWindows** presenta in genere la firma seguente:</span><span class="sxs-lookup"><span data-stu-id="8b7a7-109">**EnumWindows** has the following signature:</span></span>  
  
    ```cpp
    BOOL EnumWindows(WNDENUMPROC lpEnumFunc, LPARAM lParam)
    ```
  
     <span data-ttu-id="8b7a7-110">Un’indicazione del fatto che questa funzione richiede un callback è la presenza dell'argomento **lpEnumFunc**.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-110">One clue that this function requires a callback is the presence of the **lpEnumFunc** argument.</span></span> <span data-ttu-id="8b7a7-111">È frequente vedere il prefisso **lp** (puntatore di tipo long) combinato con il suffisso **Func** nel nome di argomenti che accettano un puntatore a una funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-111">It is common to see the **lp** (long pointer) prefix combined with the **Func** suffix in the name of arguments that take a pointer to a callback function.</span></span> <span data-ttu-id="8b7a7-112">Per informazioni sulle funzioni Win32, vedere Microsoft Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-112">For documentation about Win32 functions, see the Microsoft Platform SDK.</span></span>  
  
2. <span data-ttu-id="8b7a7-113">Creare la funzione di callback gestita.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-113">Create the managed callback function.</span></span> <span data-ttu-id="8b7a7-114">L'esempio dichiara un tipo delegato, denominato `CallBack`, che accetta due argomenti (**hwnd** e **lparam**).</span><span class="sxs-lookup"><span data-stu-id="8b7a7-114">The example declares a delegate type, called `CallBack`, which takes two arguments (**hwnd** and **lparam**).</span></span> <span data-ttu-id="8b7a7-115">Il primo argomento è un handle alla finestra, mentre il secondo è definito dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-115">The first argument is a handle to the window; the second argument is application-defined.</span></span> <span data-ttu-id="8b7a7-116">In questa versione entrambi gli argomenti devono essere numeri interi.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-116">In this release, both arguments must be integers.</span></span>  
  
     <span data-ttu-id="8b7a7-117">Funzioni di callback restituiscono in genere valori diversi da zero per indicare l’esito positivo e zero per indicare l’esito negativo.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-117">Callback functions generally return nonzero values to indicate success and zero to indicate failure.</span></span> <span data-ttu-id="8b7a7-118">Questo esempio imposta in modo esplicito il valore restituito su **true** per continuare l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-118">This example explicitly sets the return value to **true** to continue the enumeration.</span></span>  
  
3. <span data-ttu-id="8b7a7-119">Creare un delegato e passarlo come argomento alla funzione **EnumWindows**.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-119">Create a delegate and pass it as an argument to the **EnumWindows** function.</span></span> <span data-ttu-id="8b7a7-120">Platform invoke converte automaticamente il delegato in un formato di callback conosciuto.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-120">Platform invoke converts the delegate to a familiar callback format automatically.</span></span>  
  
4. <span data-ttu-id="8b7a7-121">Assicurarsi che il garbage collector non recuperi il delegato prima che venga completata la funzione di callback.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-121">Ensure that the garbage collector does not reclaim the delegate before the callback function completes its work.</span></span> <span data-ttu-id="8b7a7-122">Quando si passa un delegato come parametro o si passa un delegato contenuto come campo in una struttura, questo non viene interessato per la durata della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-122">When you pass a delegate as a parameter, or pass a delegate contained as a field in a structure, it remains uncollected for the duration of the call.</span></span> <span data-ttu-id="8b7a7-123">Quindi, come nel seguente esempio di enumerazione, la funzione di callback viene completata prima che venga restituita la chiamata e non richiede operazioni aggiuntive dal chiamante gestito.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-123">So, as is the case in the following enumeration example, the callback function completes its work before the call returns and requires no additional action by the managed caller.</span></span>  
  
     <span data-ttu-id="8b7a7-124">Se, tuttavia, la funzione di callback può essere richiamata dopo che viene restituita la chiamata, il chiamante gestito deve provvedere a garantire che il delegato non venga interessato fino al completamento della funzione di richiamata.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-124">If, however, the callback function can be invoked after the call returns, the managed caller must take steps to ensure that the delegate remains uncollected until the callback function finishes.</span></span> <span data-ttu-id="8b7a7-125">Per informazioni dettagliate su come evitare operazioni di Garbage Collection, vedere [Marshalling di interoperabilità](interop-marshaling.md) con platform invoke.</span><span class="sxs-lookup"><span data-stu-id="8b7a7-125">For detailed information about preventing garbage collection, see [Interop Marshaling](interop-marshaling.md) with Platform Invoke.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b7a7-126">Esempio</span><span class="sxs-lookup"><span data-stu-id="8b7a7-126">Example</span></span>  
  
```vb  
Imports System  
Imports System.Runtime.InteropServices  
  
Public Delegate Function CallBack( _  
hwnd As Integer, lParam As Integer) As Boolean  
  
Public Class EnumReportApp  
  
    Declare Function EnumWindows Lib "user32" ( _  
       x As CallBack, y As Integer) As Integer  
  
    Public Shared Sub Main()  
        EnumWindows(AddressOf EnumReportApp.Report, 0)  
    End Sub 'Main  
  
    Public Shared Function Report(hwnd As Integer, lParam As Integer) _  
    As Boolean  
        Console.Write("Window handle is ")  
        Console.WriteLine(hwnd)  
        Return True  
    End Function 'Report  
End Class 'EnumReportApp  
```  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
  
public delegate bool CallBack(int hwnd, int lParam);  
  
public class EnumReportApp  
{  
    [DllImport("user32")]  
    public static extern int EnumWindows(CallBack x, int y);
  
    public static void Main()
    {  
        CallBack myCallBack = new CallBack(EnumReportApp.Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    public static bool Report(int hwnd, int lParam)  
    {
        Console.Write("Window handle is ");  
        Console.WriteLine(hwnd);  
        return true;  
    }  
}  
```  
  
```cpp  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
// A delegate type.  
delegate bool CallBack(int hwnd, int lParam);  
  
// Managed type with the method to call.  
ref class EnumReport  
{  
// Report the window handle.  
public:  
    [DllImport("user32")]  
    static int EnumWindows(CallBack^ x, int y);  
  
    static void Main()  
    {  
        EnumReport^ er = gcnew EnumReport;  
        CallBack^ myCallBack = gcnew CallBack(&EnumReport::Report);  
        EnumWindows(myCallBack, 0);  
    }  
  
    static bool Report(int hwnd, int lParam)  
    {  
       Console::Write(L"Window handle is ");  
       Console::WriteLine(hwnd);  
       return true;  
    }  
};  
  
int main()  
{  
    EnumReport::Main();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b7a7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b7a7-127">See also</span></span>

- [<span data-ttu-id="8b7a7-128">Funzioni di callback</span><span class="sxs-lookup"><span data-stu-id="8b7a7-128">Callback Functions</span></span>](callback-functions.md)
- [<span data-ttu-id="8b7a7-129">Chiamata a una funzione di DLL</span><span class="sxs-lookup"><span data-stu-id="8b7a7-129">Calling a DLL Function</span></span>](calling-a-dll-function.md)
