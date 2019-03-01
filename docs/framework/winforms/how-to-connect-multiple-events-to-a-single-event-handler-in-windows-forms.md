---
title: 'Procedura: Connettere più eventi a un unico gestore eventi in Windows Form'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 869ef0d7717ca64209bc61c2ae22ce929edcec5e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967867"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="e577f-102">Procedura: Connettere più eventi a un unico gestore eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e577f-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="e577f-103">Nella progettazione delle applicazioni, si potrebbe essere necessario utilizzare un unico gestore eventi per più eventi o avere più eventi di eseguire la stessa procedura.</span><span class="sxs-lookup"><span data-stu-id="e577f-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="e577f-104">Ad esempio, è spesso un notevole risparmio di tempo per avere un comando di menu generano lo stesso evento come un pulsante sul form se espongono la stessa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e577f-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="e577f-105">Questo scopo, è possibile utilizzare la visualizzazione di eventi della finestra proprietà in C# o tramite il `Handles` parola chiave e il **nome della classe** e **nome metodo** caselle di riepilogo a discesa nell'Editor di codice Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e577f-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="e577f-106">Per connettere più eventi a un unico gestore eventi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e577f-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="e577f-107">Fare clic sulla forma e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="e577f-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="e577f-108">Dal **nome della classe** casella di riepilogo a discesa, selezionare uno dei controlli che si desidera gestire con il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e577f-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="e577f-109">Dal **nome del metodo** casella a discesa, selezionare uno degli eventi che si desidera che il gestore di evento da gestire.</span><span class="sxs-lookup"><span data-stu-id="e577f-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="e577f-110">L'Editor di codice inserito il gestore eventi appropriato e posiziona il punto di inserimento all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="e577f-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="e577f-111">Nell'esempio seguente, è il <xref:System.Windows.Forms.Control.Click> evento per il <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="e577f-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="e577f-112">Aggiungere gli altri eventi si vuole gestiti per il `Handles` clausola.</span><span class="sxs-lookup"><span data-stu-id="e577f-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="e577f-113">Aggiungere il codice appropriato per il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e577f-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="e577f-114">Per connettere più eventi a un unico gestore eventi in C\#</span><span class="sxs-lookup"><span data-stu-id="e577f-114">To connect multiple events to a single event handler in C\#</span></span>
  
1.  <span data-ttu-id="e577f-115">Selezionare il controllo a cui si desidera collegare un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="e577f-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="e577f-116">Nella finestra Proprietà scegliere il **eventi** pulsante (![pulsante eventi](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="e577f-116">In the Properties window, click the **Events** button (![Events Button](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="e577f-117">Fare clic sul nome dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="e577f-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="e577f-118">Nella sezione valore accanto al nome dell'evento, fare clic sul pulsante giù per visualizzare un elenco di gestori degli eventi esistenti che corrispondono alla firma del metodo dell'evento che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="e577f-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="e577f-119">Selezionare il gestore eventi appropriato dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e577f-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="e577f-120">Verrà aggiunto codice al form per associare l'evento al gestore dell'evento esistente.</span><span class="sxs-lookup"><span data-stu-id="e577f-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e577f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e577f-121">See also</span></span>
- [<span data-ttu-id="e577f-122">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e577f-122">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="e577f-123">Informazioni generali sui gestori eventi</span><span class="sxs-lookup"><span data-stu-id="e577f-123">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
