---
title: 'Procedura: Aggiungere o rimuovere da una raccolta di controlli in fase di esecuzione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 6ec4e41f5a3bee6302996f21afa81f2b5eeb9568
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720891"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="b1fb5-102">Procedura: Aggiungere o rimuovere da una raccolta di controlli in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="b1fb5-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="b1fb5-103">Attività comuni nello sviluppo di applicazioni sono controlli per l'aggiunta e rimozione di controlli da un controllo contenitore sui form (ad esempio la <xref:System.Windows.Forms.Panel> o <xref:System.Windows.Forms.GroupBox> controllo o il form stesso).</span><span class="sxs-lookup"><span data-stu-id="b1fb5-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="b1fb5-104">In fase di progettazione è possibile trascinare i controlli direttamente in un pannello o una casella di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="b1fb5-105">In fase di esecuzione questi controlli mantengono una raccolta `Controls`, che tiene traccia di quali controlli vengono posizionati su essi.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1fb5-106">L'esempio di codice seguente si applica a qualsiasi controllo che mantiene una raccolta di controlli al suo interno.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="b1fb5-107">Per aggiungere un controllo a una raccolta a livello di codice</span><span class="sxs-lookup"><span data-stu-id="b1fb5-107">To add a control to a collection programmatically</span></span>  
  
1.  <span data-ttu-id="b1fb5-108">Creare un'istanza del controllo da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-108">Create an instance of the control to be added.</span></span>  
  
2.  <span data-ttu-id="b1fb5-109">Impostare le proprietà del nuovo controllo.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-109">Set properties of the new control.</span></span>  
  
3.  <span data-ttu-id="b1fb5-110">Aggiungere il controllo alla raccolta `Controls` del controllo padre.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="b1fb5-111">Esempio di codice seguente viene illustrato come creare un'istanza di <xref:System.Windows.Forms.Button> controllo.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="b1fb5-112">Richiede un modulo con un <xref:System.Windows.Forms.Panel> controllo e che viene creato il metodo di gestione degli eventi per il pulsante, `NewPanelButton_Click`, esiste già.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="b1fb5-113">Per rimuovere controlli da una raccolta a livello di codice</span><span class="sxs-lookup"><span data-stu-id="b1fb5-113">To remove controls from a collection programmatically</span></span>  
  
1.  <span data-ttu-id="b1fb5-114">Rimuovere il gestore eventi dall'evento.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-114">Remove the event handler from the event.</span></span> <span data-ttu-id="b1fb5-115">In Visual Basic, usare il [istruzione RemoveHandler](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) parola chiave; nell'oggetto visivo C#, usare il [operatore-= (C# riferimento)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="b1fb5-115">In Visual Basic, use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in Visual C#, use the [-= Operator (C# Reference)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span></span>  
  
2.  <span data-ttu-id="b1fb5-116">Usare il metodo `Remove` per eliminare il controllo desiderato dalla raccolta del pannello `Controls`.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3.  <span data-ttu-id="b1fb5-117">Chiamare il <xref:System.Windows.Forms.Control.Dispose%2A> metodo per rilasciare tutte le risorse usate dal controllo.</span><span class="sxs-lookup"><span data-stu-id="b1fb5-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b1fb5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1fb5-118">See also</span></span>
- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="b1fb5-119">Controllo Panel</span><span class="sxs-lookup"><span data-stu-id="b1fb5-119">Panel Control</span></span>](panel-control-windows-forms.md)
