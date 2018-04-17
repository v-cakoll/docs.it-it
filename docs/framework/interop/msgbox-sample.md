---
title: Esempio di MsgBox
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26c72ee918db48bcbdf0ce912e12d20a0719f85b
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2018
---
# <a name="msgbox-sample"></a><span data-ttu-id="53381-102">Esempio di MsgBox</span><span class="sxs-lookup"><span data-stu-id="53381-102">MsgBox Sample</span></span>
<span data-ttu-id="53381-103">Questo esempio illustra come passare i tipi stringa per valore come parametri in e quando usare i campi <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> e <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>.</span><span class="sxs-lookup"><span data-stu-id="53381-103">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="53381-104">L'esempio di MsgBox usa la seguente funzione non gestita, mostrata con la dichiarazione di funzione originale:</span><span class="sxs-lookup"><span data-stu-id="53381-104">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="53381-105">Versione di **MessageBox** esportata da User32. dll.</span><span class="sxs-lookup"><span data-stu-id="53381-105">**MessageBox** exported from User32.dll.</span></span>  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 <span data-ttu-id="53381-106">In questo esempio, la classe `LibWrap` contiene un prototipo gestito per ogni funzione non gestita chiamata dalla classe `MsgBoxSample`.</span><span class="sxs-lookup"><span data-stu-id="53381-106">In this sample, the `LibWrap` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="53381-107">I metodi del prototipo gestiti `MsgBox`, `MsgBox2` e `MsgBox3` hanno dichiarazioni diverse per la stessa funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="53381-107">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="53381-108">La dichiarazione per `MsgBox2` produce output non corretto nella finestra di messaggio perché il tipo di carattere, specificato come ANSI, non corrisponde al punto di ingresso `MessageBoxW`, ovvero il nome della funzione Unicode.</span><span class="sxs-lookup"><span data-stu-id="53381-108">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="53381-109">La dichiarazione per `MsgBox3` crea una mancata corrispondenza tra i campi **EntryPoint**, **CharSet** e **ExactSpelling**.</span><span class="sxs-lookup"><span data-stu-id="53381-109">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="53381-110">La chiamata di `MsgBox3` genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="53381-110">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="53381-111">Per informazioni dettagliate sulla denominazione delle stringhe e sul marshalling dei nomi, vedere [Specifica di un set di caratteri](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="53381-111">For detailed information on string naming and name marshaling, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="53381-112">Dichiarazione dei prototipi</span><span class="sxs-lookup"><span data-stu-id="53381-112">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="53381-113">Chiamata delle funzioni</span><span class="sxs-lookup"><span data-stu-id="53381-113">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="53381-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53381-114">See Also</span></span>  
 [<span data-ttu-id="53381-115">Marshalling di stringhe</span><span class="sxs-lookup"><span data-stu-id="53381-115">Marshaling Strings</span></span>](marshaling-strings.md)  
 <span data-ttu-id="53381-116">[Tipi di dati di Platform Invoke](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="53381-116">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="53381-117">Marshalling predefinito per le stringhe</span><span class="sxs-lookup"><span data-stu-id="53381-117">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)  
 [<span data-ttu-id="53381-118">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="53381-118">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="53381-119">Specifica di un set di caratteri</span><span class="sxs-lookup"><span data-stu-id="53381-119">Specifying a Character Set</span></span>](specifying-a-character-set.md)
