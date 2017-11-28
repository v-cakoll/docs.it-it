---
title: 'Procedura: controllare lo stato di connessione in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 62361b4efff4c53156becf0cd865d262fbef1504
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="c5d6e-102">Procedura: controllare lo stato di connessione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5d6e-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="c5d6e-103">Per determinare se il computer ha una rete o una connessione Internet funzionante, è possibile usare la proprietà <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5d6e-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="c5d6e-104">Per verificare se un computer ha una connessione funzionante</span><span class="sxs-lookup"><span data-stu-id="c5d6e-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="c5d6e-105">Determinare se la proprietà `IsAvailable` è `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="c5d6e-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="c5d6e-106">Il codice seguente controlla lo stato della proprietà e lo segnala:</span><span class="sxs-lookup"><span data-stu-id="c5d6e-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]  
  
     <span data-ttu-id="c5d6e-107">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="c5d6e-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="c5d6e-108">Nella selezione del frammento di codice si trova in **Connettività e rete**.</span><span class="sxs-lookup"><span data-stu-id="c5d6e-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="c5d6e-109">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="c5d6e-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d6e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5d6e-110">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>
