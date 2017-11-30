---
title: Mouse capture in Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8004b05ea25341a142bfcfd9ae812ee3bebd6d5b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="00136-102">Mouse capture in Windows Form</span><span class="sxs-lookup"><span data-stu-id="00136-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="00136-103">*L'input del mouse* indica quando un controllo accetta i comandi di input del mouse tutti.</span><span class="sxs-lookup"><span data-stu-id="00136-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="00136-104">Quando un controllo ha acquisito il mouse, riceve l'input del mouse o meno il puntatore si trova all'interno dei bordi.</span><span class="sxs-lookup"><span data-stu-id="00136-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="00136-105">Impostazione di Mouse Capture</span><span class="sxs-lookup"><span data-stu-id="00136-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="00136-106">In Windows Form viene acquisito il mouse dal controllo quando l'utente preme un pulsante del mouse su un controllo, mentre il puntatore del mouse viene rilasciato dal controllo quando l'utente rilascia il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="00136-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="00136-107">Il <xref:System.Windows.Forms.Control.Capture%2A> proprietà la <xref:System.Windows.Forms.Control> classe specifica se un controllo ha acquisito il mouse.</span><span class="sxs-lookup"><span data-stu-id="00136-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="00136-108">Per determinare quando un controllo perde il mouse capture, gestire il <xref:System.Windows.Forms.Control.MouseCaptureChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="00136-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="00136-109">Solo la finestra di primo piano è possibile acquisire il mouse.</span><span class="sxs-lookup"><span data-stu-id="00136-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="00136-110">Quando una finestra di sfondo tenta di acquisire il mouse, la finestra riceve i messaggi solo per gli eventi del mouse che si verificano quando il puntatore del mouse è all'interno della parte visibile della finestra.</span><span class="sxs-lookup"><span data-stu-id="00136-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="00136-111">Inoltre, anche se la finestra di primo piano ha acquisito il mouse, l'utente può comunque fare clic su un'altra finestra portarla in primo piano.</span><span class="sxs-lookup"><span data-stu-id="00136-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="00136-112">Quando viene acquisito il mouse, tasti di scelta rapida non funzionano.</span><span class="sxs-lookup"><span data-stu-id="00136-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00136-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00136-113">See Also</span></span>  
 [<span data-ttu-id="00136-114">Input del mouse in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="00136-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
