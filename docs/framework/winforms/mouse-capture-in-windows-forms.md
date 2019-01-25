---
title: Mouse capture in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: ca16d2fa2339f8d9110bb748a687f90e093598fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690328"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="e3bf1-102">Mouse capture in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e3bf1-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="e3bf1-103">*Passare il mouse capture* fa riferimento a quando un controllo accetta comandi del tutto l'input del mouse.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="e3bf1-104">Quando un controllo ha acquisito il mouse, riceve l'input del mouse se il puntatore si trova all'interno dei bordi.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="e3bf1-105">Impostazione stato Mouse Capture</span><span class="sxs-lookup"><span data-stu-id="e3bf1-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="e3bf1-106">In Windows Form viene acquisito il mouse dal controllo quando l'utente preme un pulsante del mouse su un controllo e il puntatore del mouse viene rilasciato dal controllo quando l'utente rilascia il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="e3bf1-107">Il <xref:System.Windows.Forms.Control.Capture%2A> proprietà del <xref:System.Windows.Forms.Control> classe specifica se un controllo ha acquisito il mouse.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="e3bf1-108">Per determinare quando un controllo perde il mouse capture, gestire il <xref:System.Windows.Forms.Control.MouseCaptureChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="e3bf1-109">Solo la finestra di primo piano può acquisire il mouse.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="e3bf1-110">Quando una finestra di sfondo tenta di acquisire il mouse, la finestra riceve i messaggi solo per gli eventi del mouse che si verificano quando il puntatore del mouse è all'interno della parte visibile della finestra.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="e3bf1-111">Inoltre, anche se la finestra di primo piano ha acquisito il mouse, l'utente può comunque fare clic su un'altra finestra del portata in primo piano.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="e3bf1-112">Quando il puntatore del mouse viene acquisito, tasti di scelta rapida non funziona.</span><span class="sxs-lookup"><span data-stu-id="e3bf1-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3bf1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3bf1-113">See also</span></span>
- [<span data-ttu-id="e3bf1-114">Input del mouse in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e3bf1-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
