---
title: 'Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], click event handlers
- ToolBar control [Windows Forms], coding button click events
- toolbars [Windows Forms], click event handlers
ms.assetid: 98374f70-993d-4ca4-89fb-48fea6ce5b45
ms.openlocfilehash: 381b8ba08db6ff5bb817c9c89008dacb1085ac1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956029"
---
# <a name="how-to-trigger-menu-events-for-toolbar-buttons"></a><span data-ttu-id="3961d-102">Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="3961d-102">How to: Trigger Menu Events for Toolbar Buttons</span></span>
> [!NOTE]
> <span data-ttu-id="3961d-103">Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="3961d-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="3961d-104">Se il Windows Form dispone di <xref:System.Windows.Forms.ToolBar> un controllo con i pulsanti della barra degli strumenti, è necessario individuare il pulsante che l'utente fa clic.</span><span class="sxs-lookup"><span data-stu-id="3961d-104">If your Windows Form features a <xref:System.Windows.Forms.ToolBar> control with toolbar buttons, you will want to know which button the user clicks.</span></span>  
  
 <span data-ttu-id="3961d-105">Nell'evento del controllo è <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> possibile<xref:System.Windows.Forms.ToolBarButtonClickEventArgs> valutare la proprietà della classe. <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.ButtonClick></span><span class="sxs-lookup"><span data-stu-id="3961d-105">On the <xref:System.Windows.Forms.ToolBar.ButtonClick> event of the <xref:System.Windows.Forms.ToolBar> control, you can evaluate the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> property of the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class.</span></span> <span data-ttu-id="3961d-106">Nell'esempio seguente viene visualizzata una finestra di messaggio, che indica il pulsante selezionato.</span><span class="sxs-lookup"><span data-stu-id="3961d-106">In the example below, a message box is shown, indicating which button was clicked.</span></span> <span data-ttu-id="3961d-107">Per informazioni dettagliate, vedere <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="3961d-107">For details, see <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
 <span data-ttu-id="3961d-108">Nell'esempio seguente si presuppone <xref:System.Windows.Forms.ToolBar> che sia stato aggiunto un controllo a un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="3961d-108">The example below assumes a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form.</span></span>  
  
### <a name="to-handle-the-click-event-on-a-toolbar"></a><span data-ttu-id="3961d-109">Per gestire l'evento Click in una barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="3961d-109">To handle the Click event on a toolbar</span></span>  
  
1. <span data-ttu-id="3961d-110">In una procedura aggiungere i pulsanti della <xref:System.Windows.Forms.ToolBar> barra degli strumenti al controllo.</span><span class="sxs-lookup"><span data-stu-id="3961d-110">In a procedure, add toolbar buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
    ```vb  
    Public Sub ToolBarConfig()  
    ' Instantiate the toolbar buttons, set their Text properties  
    ' and add them to the ToolBar control.  
       ToolBar1.Buttons.Add(New ToolBarButton("One"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Two"))  
       ToolBar1.Buttons.Add(New ToolBarButton("Three"))  
    ' Add the event handler delegate.  
       AddHandler ToolBar1.ButtonClick, AddressOf Me.ToolBar1_ButtonClick  
    End Sub  
    ```  
  
    ```csharp  
    public void ToolBarConfig()   
    {  
       toolBar1.Buttons.Add(new ToolBarButton("One"));  
       toolBar1.Buttons.Add(new ToolBarButton("Two"));  
       toolBar1.Buttons.Add(new ToolBarButton("Three"));  
  
       toolBar1.ButtonClick +=   
          new ToolBarButtonClickEventHandler(this.toolBar1_ButtonClick);  
    }  
    ```  
  
    ```cpp  
    public:  
       void ToolBarConfig()  
       {  
          toolBar1->Buttons->Add(gcnew ToolBarButton("One"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Two"));  
          toolBar1->Buttons->Add(gcnew ToolBarButton("Three"));  
  
          toolBar1->ButtonClick +=   
             gcnew ToolBarButtonClickEventHandler(this,  
             &Form1::toolBar1_ButtonClick);  
       }  
    ```  
  
2. <span data-ttu-id="3961d-111">Aggiungere un gestore eventi per l' <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.ButtonClick> evento del controllo.</span><span class="sxs-lookup"><span data-stu-id="3961d-111">Add an event handler for the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ButtonClick> event.</span></span> <span data-ttu-id="3961d-112">Utilizzare un'istruzione di cambio del case <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> e la classe per determinare il pulsante della barra degli strumenti su cui è stato fatto clic.</span><span class="sxs-lookup"><span data-stu-id="3961d-112">Use a case switching statement and the <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> class to determine the toolbar button that was clicked.</span></span> <span data-ttu-id="3961d-113">Verrà visualizzata una finestra di messaggio appropriata.</span><span class="sxs-lookup"><span data-stu-id="3961d-113">Based on this, show an appropriate message box.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3961d-114">In questo esempio la finestra di messaggio viene usata esclusivamente come segnaposto.</span><span class="sxs-lookup"><span data-stu-id="3961d-114">A message box is being used solely as a placeholder in this example.</span></span> <span data-ttu-id="3961d-115">È possibile aggiungere altro codice da eseguire quando vengono selezionati i pulsanti della barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="3961d-115">Feel free to add other code to execute when the toolbar buttons are clicked.</span></span>  
  
    ```vb  
    Protected Sub ToolBar1_ButtonClick(ByVal sender As Object, _  
    ByVal e As ToolBarButtonClickEventArgs)  
    ' Evaluate the Button property of the ToolBarButtonClickEventArgs  
    ' to determine which button was clicked.  
       Select Case ToolBar1.Buttons.IndexOf(e.Button)  
         Case 0  
           MessageBox.Show("First toolbar button clicked")  
         Case 1  
           MessageBox.Show("Second toolbar button clicked")  
         Case 2  
           MessageBox.Show("Third toolbar button clicked")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    protected void toolBar1_ButtonClick(object sender,  
    ToolBarButtonClickEventArgs e)  
    {  
       // Evaluate the Button property of the ToolBarButtonClickEventArgs  
       // to determine which button was clicked.  
       switch (toolBar1.Buttons.IndexOf(e.Button))  
       {  
          case 0 :  
             MessageBox.Show("First toolbar button clicked");  
             break;  
          case 1 :  
             MessageBox.Show("Second toolbar button clicked");  
             break;  
          case 2 :  
             MessageBox.Show("Third toolbar button clicked");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    protected:  
       void toolBar1_ButtonClick(System::Object ^ sender,  
          ToolBarButtonClickEventArgs ^ e)  
       {  
         // Evaluate the Button property of the ToolBarButtonClickEventArgs  
         // to determine which button was clicked.  
          switch (toolBar1->Buttons->IndexOf(e->Button))  
          {  
             case 0 :  
                MessageBox::Show("First toolbar button clicked");  
                break;  
             case 1 :  
                MessageBox::Show("Second toolbar button clicked");  
                break;  
             case 2 :  
                MessageBox::Show("Third toolbar button clicked");  
                break;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3961d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3961d-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="3961d-117">Procedura: Aggiungere pulsanti a un controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="3961d-117">How to: Add Buttons to a ToolBar Control</span></span>](how-to-add-buttons-to-a-toolbar-control.md)
- [<span data-ttu-id="3961d-118">Procedura: Definire un'icona per un pulsante della barra degli strumenti</span><span class="sxs-lookup"><span data-stu-id="3961d-118">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="3961d-119">Controllo ToolBar</span><span class="sxs-lookup"><span data-stu-id="3961d-119">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
