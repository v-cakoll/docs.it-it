---
title: Mouse capture in Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7cc62780579c852aaa637a3ccc13ce2929423868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="34cd4-102">Mouse capture in Windows Form</span><span class="sxs-lookup"><span data-stu-id="34cd4-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="34cd4-103">*L'input del mouse* indica quando un controllo accetta i comandi di input del mouse tutti.</span><span class="sxs-lookup"><span data-stu-id="34cd4-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="34cd4-104">Quando un controllo ha acquisito il mouse, riceve l'input del mouse o meno il puntatore si trova all'interno dei bordi.</span><span class="sxs-lookup"><span data-stu-id="34cd4-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="34cd4-105">Impostazione di Mouse Capture</span><span class="sxs-lookup"><span data-stu-id="34cd4-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="34cd4-106">In Windows Form viene acquisito il mouse dal controllo quando l'utente preme un pulsante del mouse su un controllo, mentre il puntatore del mouse viene rilasciato dal controllo quando l'utente rilascia il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="34cd4-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="34cd4-107">Il <xref:System.Windows.Forms.Control.Capture%2A> proprietà la <xref:System.Windows.Forms.Control> classe specifica se un controllo ha acquisito il mouse.</span><span class="sxs-lookup"><span data-stu-id="34cd4-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="34cd4-108">Per determinare quando un controllo perde il mouse capture, gestire il <xref:System.Windows.Forms.Control.MouseCaptureChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="34cd4-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="34cd4-109">Solo la finestra di primo piano è possibile acquisire il mouse.</span><span class="sxs-lookup"><span data-stu-id="34cd4-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="34cd4-110">Quando una finestra di sfondo tenta di acquisire il mouse, la finestra riceve i messaggi solo per gli eventi del mouse che si verificano quando il puntatore del mouse è all'interno della parte visibile della finestra.</span><span class="sxs-lookup"><span data-stu-id="34cd4-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="34cd4-111">Inoltre, anche se la finestra di primo piano ha acquisito il mouse, l'utente può comunque fare clic su un'altra finestra portarla in primo piano.</span><span class="sxs-lookup"><span data-stu-id="34cd4-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="34cd4-112">Quando viene acquisito il mouse, tasti di scelta rapida non funzionano.</span><span class="sxs-lookup"><span data-stu-id="34cd4-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34cd4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34cd4-113">See Also</span></span>  
 [<span data-ttu-id="34cd4-114">Input del mouse in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34cd4-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
