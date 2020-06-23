---
title: Esempio di MsgBox
description: Vedere un esempio di passaggio di tipi stringa per valori come nei parametri usando MsgBox. Mostra quando usare i campi EntryPoint, CharSet e ExactSpelling in .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
ms.openlocfilehash: ccf882e1f801dd18e5b65a4279fc580d927dd29d
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904091"
---
# <a name="msgbox-sample"></a><span data-ttu-id="16f1c-104">Esempio di MsgBox</span><span class="sxs-lookup"><span data-stu-id="16f1c-104">MsgBox Sample</span></span>
<span data-ttu-id="16f1c-105">Questo esempio illustra come passare i tipi stringa per valore come parametri in e quando usare i campi <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> e <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.</span><span class="sxs-lookup"><span data-stu-id="16f1c-105">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="16f1c-106">L'esempio di MsgBox usa la seguente funzione non gestita, mostrata con la dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="16f1c-106">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
- <span data-ttu-id="16f1c-107">Versione di **MessageBox** esportata da User32. dll.</span><span class="sxs-lookup"><span data-stu-id="16f1c-107">**MessageBox** exported from User32.dll.</span></span>  
  
    ```cpp
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,
       UINT uType);  
    ```  
  
 <span data-ttu-id="16f1c-108">In questo esempio, la classe `NativeMethods` contiene un prototipo gestito per ogni funzione non gestita chiamata dalla classe `MsgBoxSample`.</span><span class="sxs-lookup"><span data-stu-id="16f1c-108">In this sample, the `NativeMethods` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="16f1c-109">I metodi del prototipo gestiti `MsgBox`, `MsgBox2` e `MsgBox3` hanno dichiarazioni diverse per la stessa funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="16f1c-109">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="16f1c-110">La dichiarazione per `MsgBox2` produce output non corretto nella finestra di messaggio perché il tipo di carattere, specificato come ANSI, non corrisponde al punto di ingresso `MessageBoxW`, ovvero il nome della funzione Unicode.</span><span class="sxs-lookup"><span data-stu-id="16f1c-110">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="16f1c-111">La dichiarazione per `MsgBox3` crea una mancata corrispondenza tra i campi **EntryPoint**, **CharSet** e **ExactSpelling**.</span><span class="sxs-lookup"><span data-stu-id="16f1c-111">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="16f1c-112">La chiamata di `MsgBox3` genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="16f1c-112">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="16f1c-113">Per informazioni dettagliate sulla denominazione delle stringhe e sul marshalling dei nomi, vedere [Specifica di un set di caratteri](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="16f1c-113">For detailed information on string naming and name marshaling, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="16f1c-114">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="16f1c-114">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="16f1c-115">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="16f1c-115">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="16f1c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16f1c-116">See also</span></span>

- [<span data-ttu-id="16f1c-117">Marshalling di stringhe</span><span class="sxs-lookup"><span data-stu-id="16f1c-117">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="16f1c-118">Marshalling predefinito per le stringhe</span><span class="sxs-lookup"><span data-stu-id="16f1c-118">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
- [<span data-ttu-id="16f1c-119">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="16f1c-119">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="16f1c-120">Specifica di un set di caratteri</span><span class="sxs-lookup"><span data-stu-id="16f1c-120">Specifying a Character Set</span></span>](specifying-a-character-set.md)
