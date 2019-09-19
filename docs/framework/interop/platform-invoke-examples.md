---
title: Esempi di platform invoke
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89c2043570b9e2798ef41984b889791ddfe1d526
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71051655"
---
# <a name="platform-invoke-examples"></a><span data-ttu-id="4bccb-102">Esempi di platform invoke</span><span class="sxs-lookup"><span data-stu-id="4bccb-102">Platform Invoke Examples</span></span>
<span data-ttu-id="4bccb-103">Gli esempi seguenti dimostrano come definire e chiamare la funzione **MessageBox** in User32.dll, passando una stringa semplice come argomento.</span><span class="sxs-lookup"><span data-stu-id="4bccb-103">The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument.</span></span> <span data-ttu-id="4bccb-104">Negli esempi, il campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> è impostato su **Auto** per consentire alla piattaforma di destinazione di determinare la larghezza del carattere e il marshalling delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="4bccb-104">In the examples, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field is set to **Auto** to let the target platform determine the character width and string marshaling.</span></span>  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] 
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] 
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 <span data-ttu-id="4bccb-105">Per ulteriori esempi, vedere [Marshalling dei dati con platform invoke](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="4bccb-105">For additional examples, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bccb-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bccb-106">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="4bccb-107">Creazione di prototipi nel codice gestito</span><span class="sxs-lookup"><span data-stu-id="4bccb-107">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="4bccb-108">Specifica di un set di caratteri</span><span class="sxs-lookup"><span data-stu-id="4bccb-108">Specifying a Character Set</span></span>](specifying-a-character-set.md)
