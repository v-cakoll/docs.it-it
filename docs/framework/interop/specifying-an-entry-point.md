---
title: Specifica di un punto di ingresso
description: Viene illustrato come specificare un punto di ingresso che identifica la posizione di una funzione in una DLL. È possibile rinominare la funzione eseguendo il mapping del punto di ingresso a un altro nome.
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
ms.openlocfilehash: 5628c54103410d127c2f9c4f56e1c6f897ada754
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282021"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="2f1e1-104">Specifica di un punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="2f1e1-104">Specifying an Entry Point</span></span>

<span data-ttu-id="2f1e1-105">Un punto di ingresso identifica la posizione di una funzione in una DLL.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-105">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="2f1e1-106">All'interno di un progetto gestito, il nome originale o il punto di ingresso ordinale di una funzione di destinazione identifica tale funzione attraverso il limite di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-106">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="2f1e1-107">È anche possibile mappare il punto di ingresso a un nome diverso, rinominando in effetti la funzione.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-107">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="2f1e1-108">Di seguito è riportato un elenco di possibili motivi per rinominare una funzione di DLL:</span><span class="sxs-lookup"><span data-stu-id="2f1e1-108">The following is a list of possible reasons to rename a DLL function:</span></span>  
  
- <span data-ttu-id="2f1e1-109">Evitare l'uso di nomi delle funzioni API con distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="2f1e1-109">To avoid using case-sensitive API function names</span></span>  
  
- <span data-ttu-id="2f1e1-110">Rispettare standard di denominazione esistenti</span><span class="sxs-lookup"><span data-stu-id="2f1e1-110">To comply with existing naming standards</span></span>  
  
- <span data-ttu-id="2f1e1-111">Supportare funzioni che accettano tipi di dati diversi (dichiarando più versioni della stessa funzione di DLL)</span><span class="sxs-lookup"><span data-stu-id="2f1e1-111">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
- <span data-ttu-id="2f1e1-112">Semplificare l'uso delle API che includono versioni ANSI e Unicode</span><span class="sxs-lookup"><span data-stu-id="2f1e1-112">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="2f1e1-113">Questo argomento illustra come rinominare una funzione di DLL nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-113">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="2f1e1-114">Ridenominazione di una funzione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f1e1-114">Renaming a Function in Visual Basic</span></span>  

<span data-ttu-id="2f1e1-115">Visual Basic usa la parola chiave **Function** nell'istruzione **Declare** per impostare il campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-115">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="2f1e1-116">L'esempio seguente mostra una dichiarazione di base.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-116">The following example shows a basic declaration.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
<span data-ttu-id="2f1e1-117">È possibile sostituire il punto di ingresso **MessageBox** con **MsgBox** includendo la parola chiave **Alias** nella definizione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-117">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="2f1e1-118">In entrambi gli esempi la parola chiave **Auto** elimina la necessità di specificare la versione del set di caratteri del punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-118">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="2f1e1-119">Per altre informazioni sulla selezione di un set di caratteri, vedere [Specifica di un set di caratteri](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="2f1e1-119">For more information about selecting a character set, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="2f1e1-120">Ridenominazione di una funzione in C# e C++</span><span class="sxs-lookup"><span data-stu-id="2f1e1-120">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="2f1e1-121">È possibile usare il campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> per specificare una funzione di DLL in base al nome o al numero ordinale.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-121">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="2f1e1-122">Se il nome della funzione nella definizione del metodo corrisponde al punto di ingresso nella DLL, non è necessario identificare in modo esplicito la funzione con il campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-122">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="2f1e1-123">In caso contrario, usare uno dei seguenti formati di attributo per indicare un nome o il numero ordinale:</span><span class="sxs-lookup"><span data-stu-id="2f1e1-123">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 <span data-ttu-id="2f1e1-124">Si noti che è necessario anteporre il segno di cancelletto (#) a un numero ordinale.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-124">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="2f1e1-125">L'esempio seguente dimostra come sostituire **MessageBoxA** con **MsgBox** nel codice usando il campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="2f1e1-125">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="2f1e1-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f1e1-126">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="2f1e1-127">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="2f1e1-127">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="2f1e1-128">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="2f1e1-128">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="2f1e1-129">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="2f1e1-129">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
