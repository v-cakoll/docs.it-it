---
title: Eventi nei controlli
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: c60713917b9c84aa7fad50fb1c81fc9252149ad6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745749"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="d09cc-102">Eventi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d09cc-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="d09cc-103">Un controllo Windows Forms eredita più di 60 eventi da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d09cc-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d09cc-104">Sono inclusi l'evento <xref:System.Windows.Forms.Control.Paint>, che determina la visualizzazione di un controllo, gli eventi correlati alla visualizzazione di una finestra, ad esempio gli eventi <xref:System.Windows.Forms.Control.Resize> e <xref:System.Windows.Forms.Control.Layout>, nonché gli eventi del mouse e della tastiera di basso livello.</span><span class="sxs-lookup"><span data-stu-id="d09cc-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="d09cc-105">Alcuni eventi di basso livello vengono sintetizzati da <xref:System.Windows.Forms.Control> in eventi semantici come <xref:System.Windows.Forms.Control.Click> e <xref:System.Windows.Forms.Control.DoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="d09cc-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="d09cc-106">Per informazioni dettagliate sugli eventi ereditati, vedere <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="d09cc-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="d09cc-107">Se è necessario eseguire l'override del controllo personalizzato sulle funzionalità di eventi ereditati, eseguire l'override del metodo `On`*EventName* ereditato anziché associare un delegato.</span><span class="sxs-lookup"><span data-stu-id="d09cc-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="d09cc-108">Se non si ha familiarità con il modello di eventi in .NET Framework, vedere [Generazione di eventi da un componente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="d09cc-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d09cc-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d09cc-109">See also</span></span>

- [<span data-ttu-id="d09cc-110">Override del metodo OnPaint</span><span class="sxs-lookup"><span data-stu-id="d09cc-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="d09cc-111">Gestione dell'input dell'utente</span><span class="sxs-lookup"><span data-stu-id="d09cc-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="d09cc-112">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="d09cc-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="d09cc-113">Eventi</span><span class="sxs-lookup"><span data-stu-id="d09cc-113">Events</span></span>](../../../standard/events/index.md)
