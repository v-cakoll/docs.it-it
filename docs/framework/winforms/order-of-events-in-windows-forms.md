---
title: Ordine degli eventi
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: 618ac5a6a6a32ae1a53fc60ac80700d7648c81a7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734854"
---
# <a name="order-of-events-in-windows-forms"></a><span data-ttu-id="20efa-102">Ordine degli eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="20efa-102">Order of Events in Windows Forms</span></span>
<span data-ttu-id="20efa-103">L'ordine in cui gli eventi vengono generati nelle applicazioni Windows Form è di particolare interesse per gli sviluppatori interessati alla gestione di ciascuno di questi eventi a turno.</span><span class="sxs-lookup"><span data-stu-id="20efa-103">The order in which events are raised in Windows Forms applications is of particular interest to developers concerned with handling each of these events in turn.</span></span> <span data-ttu-id="20efa-104">Quando una situazione richiede una precisa gestione degli eventi, ad esempio quando si riprogettano parti del form, è necessaria la conoscenza dell'ordine esatto in cui vengono generati gli eventi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="20efa-104">When a situation calls for meticulous handling of events, such as when you are redrawing parts of the form, an awareness of the precise order in which events are raised at run time is necessary.</span></span> <span data-ttu-id="20efa-105">Questo argomento contiene alcune informazioni dettagliate sull'ordine degli eventi durante le varie fasi importanti nella durata delle applicazioni e dei controlli.</span><span class="sxs-lookup"><span data-stu-id="20efa-105">This topic provides some details on the order of events during several important stages in the lifetime of applications and controls.</span></span> <span data-ttu-id="20efa-106">Per dettagli specifici sull'ordine degli eventi di input del mouse, vedere [eventi del mouse in Windows Forms](mouse-events-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="20efa-106">For specific details about the order of mouse input events, see [Mouse Events in Windows Forms](mouse-events-in-windows-forms.md).</span></span> <span data-ttu-id="20efa-107">Per una panoramica degli eventi in Windows Forms, vedere [Cenni preliminari sugli eventi](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="20efa-107">For an overview of events in Windows Forms, see [Events Overview](events-overview-windows-forms.md).</span></span> <span data-ttu-id="20efa-108">Per informazioni dettagliate sulla composizione dei gestori eventi, vedere [Cenni preliminari sui gestori eventi](event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="20efa-108">For details about the makeup of event handlers, see [Event Handlers Overview](event-handlers-overview-windows-forms.md).</span></span>  
  
## <a name="application-startup-and-shutdown-events"></a><span data-ttu-id="20efa-109">Eventi di arresto e avvio dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="20efa-109">Application Startup and Shutdown Events</span></span>  
 <span data-ttu-id="20efa-110">Le classi<xref:System.Windows.Forms.Form> e <xref:System.Windows.Forms.Control> espongono un set di eventi correlati all'avvio e all'arresto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="20efa-110">The <xref:System.Windows.Forms.Form> and <xref:System.Windows.Forms.Control> classes expose a set of events related to application startup and shutdown.</span></span> <span data-ttu-id="20efa-111">Quando si avvia un'applicazione Windows Forms, gli eventi di avvio del form principale vengono generati nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="20efa-111">When a Windows Forms application starts, the startup events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 <span data-ttu-id="20efa-112">Quando un'applicazione viene chiusa, gli eventi di chiusura del form principale vengono generati nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="20efa-112">When an application closes, the shutdown events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 <span data-ttu-id="20efa-113">L'evento <xref:System.Windows.Forms.Application.ApplicationExit> della classe <xref:System.Windows.Forms.Application> viene generato dopo gli eventi di chiusura del form principale.</span><span class="sxs-lookup"><span data-stu-id="20efa-113">The <xref:System.Windows.Forms.Application.ApplicationExit> event of the <xref:System.Windows.Forms.Application> class is raised after the shutdown events of the main form.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20efa-114">Visual Basic 2005 include eventi di applicazioni aggiuntivi, come <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> e <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="20efa-114">Visual Basic 2005 includes additional application events, such as <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> and <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span></span>  
  
## <a name="focus-and-validation-events"></a><span data-ttu-id="20efa-115">Eventi di convalida e relativi allo stato attivo</span><span class="sxs-lookup"><span data-stu-id="20efa-115">Focus and Validation Events</span></span>  
 <span data-ttu-id="20efa-116">Quando si modifica lo stato attivo usando la tastiera (TAB, MAIUSC + TAB e così via), chiamando i metodi <xref:System.Windows.Forms.Control.Select%2A> o <xref:System.Windows.Forms.Control.SelectNextControl%2A> oppure impostando la proprietà <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> sul form corrente, gli eventi di attivazione della classe <xref:System.Windows.Forms.Control> si verificano nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="20efa-116">When you change the focus by using the keyboard (TAB, SHIFT+TAB, and so on), by calling the <xref:System.Windows.Forms.Control.Select%2A> or <xref:System.Windows.Forms.Control.SelectNextControl%2A> methods, or by setting the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property to the current form, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
 <span data-ttu-id="20efa-117">Quando si modifica lo stato attivo usando il mouse o chiamando il metodo <xref:System.Windows.Forms.Control.Focus%2A>, gli eventi di attivazione della classe <xref:System.Windows.Forms.Control> si verificano nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="20efa-117">When you change the focus by using the mouse or by calling the <xref:System.Windows.Forms.Control.Focus%2A> method, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a><span data-ttu-id="20efa-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20efa-118">See also</span></span>

- [<span data-ttu-id="20efa-119">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="20efa-119">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
