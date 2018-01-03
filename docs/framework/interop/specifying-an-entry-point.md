---
title: Specifica di un punto di ingresso
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7486820d78d767b8eb79397d6179ac81efc27968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="fc8fa-102">Specifica di un punto di ingresso</span><span class="sxs-lookup"><span data-stu-id="fc8fa-102">Specifying an Entry Point</span></span>
<span data-ttu-id="fc8fa-103">Un punto di ingresso identifica la posizione di una funzione in una DLL.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="fc8fa-104">All'interno di un progetto gestito, il nome originale o il punto di ingresso ordinale di una funzione di destinazione identifica tale funzione attraverso il limite di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="fc8fa-105">È anche possibile mappare il punto di ingresso a un nome diverso, rinominando in effetti la funzione.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="fc8fa-106">L'elenco seguente include i motivi possibili per cui rinominare una funzione di DLL:</span><span class="sxs-lookup"><span data-stu-id="fc8fa-106">Following is a list of possible reasons to rename a DLL function:</span></span>  
  
-   <span data-ttu-id="fc8fa-107">Evitare l'uso di nomi delle funzioni API con distinzione tra maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="fc8fa-107">To avoid using case-sensitive API function names</span></span>  
  
-   <span data-ttu-id="fc8fa-108">Rispettare standard di denominazione esistenti</span><span class="sxs-lookup"><span data-stu-id="fc8fa-108">To comply with existing naming standards</span></span>  
  
-   <span data-ttu-id="fc8fa-109">Supportare funzioni che accettano tipi di dati diversi (dichiarando più versioni della stessa funzione di DLL)</span><span class="sxs-lookup"><span data-stu-id="fc8fa-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
-   <span data-ttu-id="fc8fa-110">Semplificare l'uso delle API che includono versioni ANSI e Unicode</span><span class="sxs-lookup"><span data-stu-id="fc8fa-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="fc8fa-111">Questo argomento illustra come rinominare una funzione di DLL nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="fc8fa-112">Ridenominazione di una funzione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc8fa-112">Renaming a Function in Visual Basic</span></span>  
 <span data-ttu-id="fc8fa-113">Visual Basic usa la parola chiave **Function** nell'istruzione **Declare** per impostare il campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="fc8fa-114">L'esempio seguente mostra una dichiarazione di base.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-114">The following example shows a basic declaration.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 <span data-ttu-id="fc8fa-115">È possibile sostituire il punto di ingresso **MessageBox** con **MsgBox** includendo la parola chiave **Alias** nella definizione, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="fc8fa-116">In entrambi gli esempi la parola chiave **Auto** elimina la necessità di specificare la versione del set di caratteri del punto di ingresso.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="fc8fa-117">Per altre informazioni sulla selezione di un set di caratteri, vedere [Specifica di un set di caratteri](../../../docs/framework/interop/specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="fc8fa-117">For more information about selecting a character set, see [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md).</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="fc8fa-118">Ridenominazione di una funzione in C# e C++</span><span class="sxs-lookup"><span data-stu-id="fc8fa-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="fc8fa-119">È possibile usare il campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> per specificare una funzione di DLL in base al nome o al numero ordinale.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="fc8fa-120">Se il nome della funzione nella definizione del metodo corrisponde al punto di ingresso nella DLL, non è necessario identificare in modo esplicito la funzione con il campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="fc8fa-121">In caso contrario, usare uno dei seguenti formati di attributo per indicare un nome o il numero ordinale:</span><span class="sxs-lookup"><span data-stu-id="fc8fa-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 <span data-ttu-id="fc8fa-122">Si noti che è necessario anteporre il segno di cancelletto (#) a un numero ordinale.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="fc8fa-123">L'esempio seguente dimostra come sostituire **MessageBoxA** con **MsgBox** nel codice usando il campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="fc8fa-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc8fa-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc8fa-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="fc8fa-125">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="fc8fa-125">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="fc8fa-126">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="fc8fa-126">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="fc8fa-127">Marshalling dei dati con platform invoke</span><span class="sxs-lookup"><span data-stu-id="fc8fa-127">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
