---
title: Mouse Capture
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741028"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="83ae3-102">Mouse capture in Windows Form</span><span class="sxs-lookup"><span data-stu-id="83ae3-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="83ae3-103">Il *mouse capture* fa riferimento a quando un controllo accetta il comando di tutti gli input del mouse.</span><span class="sxs-lookup"><span data-stu-id="83ae3-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="83ae3-104">Quando un controllo ha acquisito il mouse, riceve l'input del mouse indipendentemente dal fatto che il puntatore si trovi all'interno dei bordi.</span><span class="sxs-lookup"><span data-stu-id="83ae3-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="83ae3-105">Impostazione dell'acquisizione del mouse</span><span class="sxs-lookup"><span data-stu-id="83ae3-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="83ae3-106">In Windows Forms il mouse viene acquisito dal controllo quando l'utente preme un pulsante del mouse su un controllo e il mouse viene rilasciato dal controllo quando l'utente rilascia il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="83ae3-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="83ae3-107">La proprietà <xref:System.Windows.Forms.Control.Capture%2A> della classe <xref:System.Windows.Forms.Control> specifica se un controllo ha acquisito il mouse.</span><span class="sxs-lookup"><span data-stu-id="83ae3-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="83ae3-108">Per determinare quando un controllo perde il mouse capture, gestire l'evento <xref:System.Windows.Forms.Control.MouseCaptureChanged>.</span><span class="sxs-lookup"><span data-stu-id="83ae3-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="83ae3-109">Solo la finestra in primo piano può acquisire il mouse.</span><span class="sxs-lookup"><span data-stu-id="83ae3-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="83ae3-110">Quando una finestra di sfondo tenta di acquisire il mouse, la finestra riceve i messaggi solo per gli eventi del mouse che si verificano quando il puntatore del mouse si trova all'interno della parte visibile della finestra.</span><span class="sxs-lookup"><span data-stu-id="83ae3-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="83ae3-111">Inoltre, anche se la finestra in primo piano ha acquisito il mouse, l'utente può comunque fare clic su un'altra finestra, portandola in primo piano.</span><span class="sxs-lookup"><span data-stu-id="83ae3-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="83ae3-112">Quando il mouse viene acquisito, i tasti di scelta rapida non funzionano.</span><span class="sxs-lookup"><span data-stu-id="83ae3-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ae3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83ae3-113">See also</span></span>

- [<span data-ttu-id="83ae3-114">Input del mouse in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83ae3-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
