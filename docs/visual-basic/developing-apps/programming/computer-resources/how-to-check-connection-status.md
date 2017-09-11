---
title: 'Procedura: controllare lo stato di connessione in Visual Basic'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Web connections
- IsAvailable property, about IsAvailable
- connections, checking status
- connection status
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3654eb51bb47317c2dc7bf74979a847438b0ae8
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="a7275-102">Procedura: controllare lo stato di connessione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7275-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="a7275-103">Per determinare se il computer ha una rete o una connessione Internet funzionante, è possibile usare la proprietà <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7275-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="a7275-104">Per verificare se un computer ha una connessione funzionante</span><span class="sxs-lookup"><span data-stu-id="a7275-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="a7275-105">Determinare se la proprietà `IsAvailable` è `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="a7275-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="a7275-106">Il codice seguente controlla lo stato della proprietà e lo segnala:</span><span class="sxs-lookup"><span data-stu-id="a7275-106">The following code checks the property's status and reports it:</span></span>  
  
     <span data-ttu-id="a7275-107">[!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a7275-107">[!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-check-connection-status_1.vb)]</span></span>  
  
     <span data-ttu-id="a7275-108">Questo esempio di codice è disponibile anche come frammento di codice IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="a7275-108">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="a7275-109">Nella selezione del frammento di codice si trova in **Connettività e rete**.</span><span class="sxs-lookup"><span data-stu-id="a7275-109">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="a7275-110">Per altre informazioni, vedere [Code Snippets](/visualstudio/ide/code-snippets) (Frammenti di codice).</span><span class="sxs-lookup"><span data-stu-id="a7275-110">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7275-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7275-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>

