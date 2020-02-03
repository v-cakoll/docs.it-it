---
title: Eventi del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- MouseLeave event [Windows Forms]
- events [Windows Forms], mouse
- Click event [Windows Forms], raising order
- Windows Forms controls, click events
- MouseDoubleClick event [Windows Forms]
- MouseEnter event [Windows Forms]
- MouseHover event [Windows Forms]
- MouseDown event [Windows Forms]
- MouseClick event [Windows Forms]
- MouseMove event [Windows Forms]
- mouse [Windows Forms], events
- MouseUp event
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
ms.openlocfilehash: 4909f56fc3935848fd18bc35c1cb56b5407a24c8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740970"
---
# <a name="mouse-events-in-windows-forms"></a><span data-ttu-id="56cb6-102">Eventi mouse in Windows Form</span><span class="sxs-lookup"><span data-stu-id="56cb6-102">Mouse Events in Windows Forms</span></span>

<span data-ttu-id="56cb6-103">Quando si gestisce l'input del mouse, in genere si vogliono conoscere la posizione del puntatore del mouse e lo stato dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="56cb6-103">When you handle mouse input, you usually want to know the location of the mouse pointer and the state of the mouse buttons.</span></span> <span data-ttu-id="56cb6-104">Questo argomento descrive in dettaglio come reperire tali informazioni da eventi del mouse e illustra l'ordine in cui gli eventi Click del mouse vengono generati nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="56cb6-104">This topic provides details on how to get this information from mouse events, and explains the order in which mouse click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="56cb6-105">Per un elenco e una descrizione di tutti gli eventi del mouse, vedere funzionamento dell' [input del mouse in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="56cb6-105">For a list and description of all of the mouse events, see [How Mouse Input Works in Windows Forms](how-mouse-input-works-in-windows-forms.md).</span></span>  <span data-ttu-id="56cb6-106">Vedere anche [Cenni preliminari sui gestori eventi (Windows Forms)](event-handlers-overview-windows-forms.md) e [Cenni preliminari sugli eventi (Windows Forms)](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="56cb6-106">Also see [Event Handlers Overview (Windows Forms)](event-handlers-overview-windows-forms.md) and [Events Overview (Windows Forms)](events-overview-windows-forms.md).</span></span>

## <a name="mouse-information"></a><span data-ttu-id="56cb6-107">Informazioni sul mouse</span><span class="sxs-lookup"><span data-stu-id="56cb6-107">Mouse Information</span></span>

<span data-ttu-id="56cb6-108">Un oggetto <xref:System.Windows.Forms.MouseEventArgs> viene inviato ai gestori degli eventi del mouse correlati alla pressione di un pulsante e alla registrazione dei movimenti del mouse.</span><span class="sxs-lookup"><span data-stu-id="56cb6-108">A <xref:System.Windows.Forms.MouseEventArgs> is sent to the handlers of mouse events related to clicking a mouse button and tracking mouse movements.</span></span> <span data-ttu-id="56cb6-109"><xref:System.Windows.Forms.MouseEventArgs> fornisce informazioni sullo stato corrente del mouse, fra cui la posizione del puntatore nelle coordinate del client, i pulsanti del mouse premuti e se la rotellina del mouse è stata fatta scorrere.</span><span class="sxs-lookup"><span data-stu-id="56cb6-109"><xref:System.Windows.Forms.MouseEventArgs> provides information about the current state of the mouse, including the location of the mouse pointer in client coordinates, which mouse buttons are pressed, and whether the mouse wheel has scrolled.</span></span> <span data-ttu-id="56cb6-110">Numerosi eventi del mouse, ad esempio quelli che notificano semplicemente il momento in cui il puntatore del mouse entra o esce dai limiti di un controllo, inviano un oggetto <xref:System.EventArgs> al gestore eventi senza altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="56cb6-110">Several mouse events, such as those that simply notify when the mouse pointer has entered or left the bounds of a control, send an <xref:System.EventArgs> to the event handler with no further information.</span></span>

<span data-ttu-id="56cb6-111">Se si desidera conoscere lo stato corrente dei pulsanti del mouse o la posizione del puntatore ed evitare la gestione di un evento del mouse, è anche possibile usare le proprietà <xref:System.Windows.Forms.Control.MouseButtons%2A> e <xref:System.Windows.Forms.Control.MousePosition%2A> della classe <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-111">If you want to know the current state of the mouse buttons or the location of the mouse pointer, and you want to avoid handling a mouse event, you can also use the <xref:System.Windows.Forms.Control.MouseButtons%2A> and <xref:System.Windows.Forms.Control.MousePosition%2A> properties of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="56cb6-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> restituisce informazioni sui pulsanti del mouse attualmente premuti.</span><span class="sxs-lookup"><span data-stu-id="56cb6-112"><xref:System.Windows.Forms.Control.MouseButtons%2A> returns information about which mouse buttons are currently pressed.</span></span> <span data-ttu-id="56cb6-113"><xref:System.Windows.Forms.Control.MousePosition%2A> restituisce le coordinate dello schermo del puntatore del mouse e coincide con il valore restituito dalla proprietà <xref:System.Windows.Forms.Cursor.Position%2A>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-113">The <xref:System.Windows.Forms.Control.MousePosition%2A> returns the screen coordinates of the mouse pointer and is equivalent to the value returned by <xref:System.Windows.Forms.Cursor.Position%2A>.</span></span>

## <a name="converting-between-screen-and-client-coordinates"></a><span data-ttu-id="56cb6-114">Conversione tra coordinate dello schermo e del client</span><span class="sxs-lookup"><span data-stu-id="56cb6-114">Converting Between Screen and Client Coordinates</span></span>

<span data-ttu-id="56cb6-115">Poiché alcune informazioni sulla posizione del mouse sono espresse con le coordinate del client e altre con le coordinate dello schermo, può essere necessario eseguire una conversione da un sistema di coordinate all'altro.</span><span class="sxs-lookup"><span data-stu-id="56cb6-115">Because some mouse location information is in client coordinates and some is in screen coordinates, you may need to convert a point from one coordinate system to the other.</span></span> <span data-ttu-id="56cb6-116">Questa operazione può essere eseguita facilmente usando i metodi <xref:System.Windows.Forms.Control.PointToClient%2A> e <xref:System.Windows.Forms.Control.PointToScreen%2A> disponibili nella classe <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-116">You can do this easily by using the <xref:System.Windows.Forms.Control.PointToClient%2A> and <xref:System.Windows.Forms.Control.PointToScreen%2A> methods available on the <xref:System.Windows.Forms.Control> class.</span></span>

## <a name="standard-click-event-behavior"></a><span data-ttu-id="56cb6-117">Comportamento dell'evento Click standard</span><span class="sxs-lookup"><span data-stu-id="56cb6-117">Standard Click Event Behavior</span></span>

<span data-ttu-id="56cb6-118">Se si vogliono gestire gli eventi Click del mouse nell'ordine corretto, è necessario conoscere l'ordine in cui gli eventi Click vengono generati nei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="56cb6-118">If you want to handle mouse click events in the proper order, you need to know the order in which click events are raised in Windows Forms controls.</span></span> <span data-ttu-id="56cb6-119">Tutti i controlli Windows Form generano eventi Click nello stesso ordine quando viene premuto e rilasciato un pulsante del mouse (indipendentemente dal pulsante), fatta eccezione per i singoli controlli segnalati nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="56cb6-119">All Windows Forms controls raise click events in the same order when a mouse button is pressed and released (regardless of which mouse button), except where noted in the following list for individual controls.</span></span> <span data-ttu-id="56cb6-120">L'ordine degli eventi generati per un singolo clic del pulsante del mouse è il seguente:</span><span class="sxs-lookup"><span data-stu-id="56cb6-120">The following list shows the order of events raised for a single mouse-button click:</span></span>

1. <span data-ttu-id="56cb6-121">Evento<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-121"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="56cb6-122">Evento<xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-122"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="56cb6-123">Evento<xref:System.Windows.Forms.Control.MouseClick> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-123"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="56cb6-124">Evento<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-124"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="56cb6-125">Di seguito è riportato l'ordine degli eventi generati per un doppio clic del pulsante del mouse:</span><span class="sxs-lookup"><span data-stu-id="56cb6-125">The following is the order of events raised for a double mouse-button click:</span></span>

1. <span data-ttu-id="56cb6-126">Evento<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-126"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

2. <span data-ttu-id="56cb6-127">Evento<xref:System.Windows.Forms.Control.Click> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-127"><xref:System.Windows.Forms.Control.Click> event.</span></span>

3. <span data-ttu-id="56cb6-128">Evento<xref:System.Windows.Forms.Control.MouseClick> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-128"><xref:System.Windows.Forms.Control.MouseClick> event.</span></span>

4. <span data-ttu-id="56cb6-129">Evento<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-129"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

5. <span data-ttu-id="56cb6-130">Evento<xref:System.Windows.Forms.Control.MouseDown> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-130"><xref:System.Windows.Forms.Control.MouseDown> event.</span></span>

6. <span data-ttu-id="56cb6-131">Evento<xref:System.Windows.Forms.Control.DoubleClick> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-131"><xref:System.Windows.Forms.Control.DoubleClick> event.</span></span> <span data-ttu-id="56cb6-132">Può variare se il controllo in questione ha il bit di stile <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="56cb6-132">(This can vary, depending on whether the control in question has the <xref:System.Windows.Forms.ControlStyles.StandardDoubleClick> style bit set to `true`.</span></span> <span data-ttu-id="56cb6-133">Per altre informazioni sulla modalità di impostazione di un bit <xref:System.Windows.Forms.ControlStyles>, vedere il metodo <xref:System.Windows.Forms.Control.SetStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-133">For more information about how to set a <xref:System.Windows.Forms.ControlStyles> bit, see the <xref:System.Windows.Forms.Control.SetStyle%2A> method.)</span></span>

7. <span data-ttu-id="56cb6-134">Evento<xref:System.Windows.Forms.Control.MouseDoubleClick> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-134"><xref:System.Windows.Forms.Control.MouseDoubleClick> event.</span></span>

8. <span data-ttu-id="56cb6-135">Evento<xref:System.Windows.Forms.Control.MouseUp> .</span><span class="sxs-lookup"><span data-stu-id="56cb6-135"><xref:System.Windows.Forms.Control.MouseUp> event.</span></span>

<span data-ttu-id="56cb6-136">Per un esempio di codice che illustra l'ordine degli eventi click del mouse, vedere [procedura: gestire eventi di input utente nei controlli Windows Forms](how-to-handle-user-input-events-in-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="56cb6-136">For a code example that demonstrates the order of the mouse click events, see [How to: Handle User Input Events in Windows Forms Controls](how-to-handle-user-input-events-in-windows-forms-controls.md).</span></span>

### <a name="individual-controls"></a><span data-ttu-id="56cb6-137">Controlli autonomi</span><span class="sxs-lookup"><span data-stu-id="56cb6-137">Individual Controls</span></span>

<span data-ttu-id="56cb6-138">I controlli seguenti non sono conformi al comportamento standard dell'evento Click del mouse:</span><span class="sxs-lookup"><span data-stu-id="56cb6-138">The following controls do not conform to the standard mouse click event behavior:</span></span>

- <xref:System.Windows.Forms.Button>
- <xref:System.Windows.Forms.CheckBox>
- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.RadioButton>

  > [!NOTE]
  > <span data-ttu-id="56cb6-139">Per il controllo <xref:System.Windows.Forms.ComboBox>, il comportamento dell'evento descritto di seguito si verifica se l'utente fa clic sul campo di modifica, sul pulsante o su una voce dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="56cb6-139">For the <xref:System.Windows.Forms.ComboBox> control, the event behavior detailed later occurs if the user clicks on the edit field, the button, or on an item within the list.</span></span>

  - <span data-ttu-id="56cb6-140">Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-140">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="56cb6-141">Clic con pulsante destro: nessun evento Click generato</span><span class="sxs-lookup"><span data-stu-id="56cb6-141">Right click: No click events raised</span></span>

  - <span data-ttu-id="56cb6-142">Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-142">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="56cb6-143">Doppio clic con pulsante destro: nessun evento Click generato</span><span class="sxs-lookup"><span data-stu-id="56cb6-143">Right double-click: No click events raised</span></span>

- <span data-ttu-id="56cb6-144">Controlli <xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox> e <xref:System.Windows.Forms.CheckedListBox></span><span class="sxs-lookup"><span data-stu-id="56cb6-144"><xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox>, and <xref:System.Windows.Forms.CheckedListBox> controls</span></span>

  > [!NOTE]
  > <span data-ttu-id="56cb6-145">Il comportamento dell'evento descritto di seguito si verifica se l'utente fa clic in un punto qualsiasi di tali controlli.</span><span class="sxs-lookup"><span data-stu-id="56cb6-145">The event behavior detailed later occurs when the user clicks anywhere within these controls.</span></span>

  - <span data-ttu-id="56cb6-146">Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-146">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="56cb6-147">Clic con pulsante destro: nessun evento Click generato</span><span class="sxs-lookup"><span data-stu-id="56cb6-147">Right click: No click events raised</span></span>

  - <span data-ttu-id="56cb6-148">Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-148">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="56cb6-149">Doppio clic con pulsante destro: nessun evento Click generato</span><span class="sxs-lookup"><span data-stu-id="56cb6-149">Right double-click: No click events raised</span></span>

- <span data-ttu-id="56cb6-150">Controllo <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="56cb6-150"><xref:System.Windows.Forms.ListView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="56cb6-151">Il comportamento dell'evento descritto di seguito si verifica solo quando l'utente fa clic sugli elementi nel controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-151">The event behavior detailed later occurs only when the user clicks on the items in the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="56cb6-152">Per i clic in altri punti del controllo non verranno generati eventi.</span><span class="sxs-lookup"><span data-stu-id="56cb6-152">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="56cb6-153">Oltre agli eventi descritti di seguito esistono gli eventi <xref:System.Windows.Forms.ListView.BeforeLabelEdit> e <xref:System.Windows.Forms.ListView.AfterLabelEdit>, rilevanti se si desidera usare la convalida con il controllo <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-153">In addition to the events described later, there are the <xref:System.Windows.Forms.ListView.BeforeLabelEdit> and <xref:System.Windows.Forms.ListView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.ListView> control.</span></span>

  - <span data-ttu-id="56cb6-154">Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-154">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="56cb6-155">Clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-155">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="56cb6-156">Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-156">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="56cb6-157">Doppio clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-157">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

- <span data-ttu-id="56cb6-158">Controllo <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="56cb6-158"><xref:System.Windows.Forms.TreeView> control</span></span>

  > [!NOTE]
  > <span data-ttu-id="56cb6-159">Il comportamento dell'evento descritto di seguito si verifica solo quando l'utente fa clic sugli elementi stessi o a destra degli elementi nel controllo <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-159">The event behavior detailed later occurs only when the user clicks on the items themselves or to the right of the items in the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="56cb6-160">Per i clic in altri punti del controllo non verranno generati eventi.</span><span class="sxs-lookup"><span data-stu-id="56cb6-160">No events are raised for clicks anywhere else on the control.</span></span> <span data-ttu-id="56cb6-161">Oltre agli eventi descritti di seguito, esistono gli eventi <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> e <xref:System.Windows.Forms.TreeView.AfterLabelEdit>, rilevanti se si desidera usare la convalida con il controllo <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-161">In addition to those described later, there are the <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck>, and <xref:System.Windows.Forms.TreeView.AfterLabelEdit> events, which may be of interest to you if you want to use validation with the <xref:System.Windows.Forms.TreeView> control.</span></span>

  - <span data-ttu-id="56cb6-162">Clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-162">Left click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="56cb6-163">Clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-163">Right click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick></span></span>

  - <span data-ttu-id="56cb6-164">Doppio clic con pulsante sinistro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-164">Left double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

  - <span data-ttu-id="56cb6-165">Doppio clic con pulsante destro: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span><span class="sxs-lookup"><span data-stu-id="56cb6-165">Right double-click: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick></span></span>

### <a name="painting-behavior-of-toggle-controls"></a><span data-ttu-id="56cb6-166">Comportamento del disegno dei controlli di attivazione/disimpostazione</span><span class="sxs-lookup"><span data-stu-id="56cb6-166">Painting behavior of toggle controls</span></span>

<span data-ttu-id="56cb6-167">I controlli di attivazione/disattivazione, quali quelli che derivano dalla classe <xref:System.Windows.Forms.ButtonBase>, presentano il seguente comportamento di disegno distintivo in combinazione con eventi Click del mouse:</span><span class="sxs-lookup"><span data-stu-id="56cb6-167">Toggle controls, such as the controls deriving from the <xref:System.Windows.Forms.ButtonBase> class, have the following distinctive painting behavior in combination with mouse click events:</span></span>

1. <span data-ttu-id="56cb6-168">L'utente preme il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="56cb6-168">The user presses the mouse button.</span></span>

2. <span data-ttu-id="56cb6-169">Il controllo viene disegnato nello stato premuto.</span><span class="sxs-lookup"><span data-stu-id="56cb6-169">The control paints in the pressed state.</span></span>

3. <span data-ttu-id="56cb6-170">Viene generato l'evento <xref:System.Windows.Forms.Control.MouseDown>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-170">The <xref:System.Windows.Forms.Control.MouseDown> event is raised.</span></span>

4. <span data-ttu-id="56cb6-171">L'utente rilascia il pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="56cb6-171">The user releases the mouse button.</span></span>

5. <span data-ttu-id="56cb6-172">Il controllo viene disegnato nello stato generato.</span><span class="sxs-lookup"><span data-stu-id="56cb6-172">The control paints in the raised state.</span></span>

6. <span data-ttu-id="56cb6-173">Viene generato l'evento <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-173">The <xref:System.Windows.Forms.Control.Click> event is raised.</span></span>

7. <span data-ttu-id="56cb6-174">Viene generato l'evento <xref:System.Windows.Forms.Control.MouseClick>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-174">The <xref:System.Windows.Forms.Control.MouseClick> event is raised.</span></span>

8. <span data-ttu-id="56cb6-175">Viene generato l'evento <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-175">The <xref:System.Windows.Forms.Control.MouseUp> event is raised.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56cb6-176">Se l'utente sposta il puntatore all'esterno del controllo di attivazione/disattivazione mentre il pulsante del mouse è premuto, ad esempio spostando il mouse dal controllo <xref:System.Windows.Forms.Button> mentre il pulsante è premuto, il controllo di attivazione/disattivazione viene disegnato nello stato generato e si verifica solo l'evento <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="56cb6-176">If the user moves the pointer out of the toggle control while the mouse button is down (such as moving the mouse off the <xref:System.Windows.Forms.Button> control while it is pressed), the toggle control will paint in the raised state and only the <xref:System.Windows.Forms.Control.MouseUp> event occurs.</span></span> <span data-ttu-id="56cb6-177">In tale situazione l'evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> non si verificherà.</span><span class="sxs-lookup"><span data-stu-id="56cb6-177">The <xref:System.Windows.Forms.Control.Click> or <xref:System.Windows.Forms.Control.MouseClick> events will not occur in this situation.</span></span>

## <a name="see-also"></a><span data-ttu-id="56cb6-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56cb6-178">See also</span></span>

- [<span data-ttu-id="56cb6-179">Input del mouse in un'applicazione Windows Forms</span><span class="sxs-lookup"><span data-stu-id="56cb6-179">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
