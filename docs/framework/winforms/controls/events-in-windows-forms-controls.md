---
title: Eventi nei controlli di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: d18938565c302be085b7ac51f878d83ae5ab533d
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "47027901"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="1a808-102">Eventi nei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1a808-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="1a808-103">Un controllo Windows Form eredita più di sessanta eventi da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a808-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="1a808-104">Sono inclusi i <xref:System.Windows.Forms.Control.Paint> evento, che fa sì che un controllo da disegnare, gli eventi correlati alla visualizzazione di finestre, ad esempio il <xref:System.Windows.Forms.Control.Resize> e <xref:System.Windows.Forms.Control.Layout> eventi ed eventi di mouse e tastiera a basso livello.</span><span class="sxs-lookup"><span data-stu-id="1a808-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="1a808-105">Alcuni eventi di basso livello sono sintetizzati da <xref:System.Windows.Forms.Control> in eventi semantici, ad esempio <xref:System.Windows.Forms.Control.Click> e <xref:System.Windows.Forms.Control.DoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="1a808-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="1a808-106">Per informazioni dettagliate sugli eventi ereditati, vedere <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="1a808-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="1a808-107">Se è necessario eseguire l'override del controllo personalizzato sulle funzionalità di eventi ereditati, eseguire l'override del metodo `On`*EventName* ereditato anziché associare un delegato.</span><span class="sxs-lookup"><span data-stu-id="1a808-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="1a808-108">Se non si ha familiarità con il modello di eventi in .NET Framework, vedere [Generazione di eventi da un componente](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span><span class="sxs-lookup"><span data-stu-id="1a808-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a808-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a808-109">See Also</span></span>  
 [<span data-ttu-id="1a808-110">Override del metodo OnPaint</span><span class="sxs-lookup"><span data-stu-id="1a808-110">Overriding the OnPaint Method</span></span>](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [<span data-ttu-id="1a808-111">Gestione dell'input dell'utente</span><span class="sxs-lookup"><span data-stu-id="1a808-111">Handling User Input</span></span>](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [<span data-ttu-id="1a808-112">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="1a808-112">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="1a808-113">Eventi</span><span class="sxs-lookup"><span data-stu-id="1a808-113">Events</span></span>](../../../../docs/standard/events/index.md)
