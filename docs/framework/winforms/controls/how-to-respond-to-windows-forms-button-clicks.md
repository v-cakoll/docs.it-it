---
title: Rispondere ai clic sui controlli Button
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: dd6cf75a316257c86a23b44a818422336c12aa67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735721"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="e2dd9-102">Procedura: rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e2dd9-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="e2dd9-103">L'uso più semplice di un controllo di <xref:System.Windows.Forms.Button> Windows Forms consiste nell'eseguire codice quando si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="e2dd9-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="e2dd9-104">Se si fa clic su un controllo <xref:System.Windows.Forms.Button> viene generato anche un numero di altri eventi, ad esempio gli eventi <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>e <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="e2dd9-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="e2dd9-105">Se si intende alleghi i gestori eventi per questi eventi correlati, assicurarsi che le azioni non siano in conflitto.</span><span class="sxs-lookup"><span data-stu-id="e2dd9-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="e2dd9-106">Se, ad esempio, si fa clic sul pulsante per cancellare le informazioni digitate dall'utente in una casella di testo, la sospensione del puntatore del mouse sul pulsante non dovrebbe visualizzare una descrizione comando con le informazioni attualmente inesistenti.</span><span class="sxs-lookup"><span data-stu-id="e2dd9-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="e2dd9-107">Se l'utente tenta di fare doppio clic sul controllo <xref:System.Windows.Forms.Button>, ogni clic verrà elaborato separatamente. ovvero, il controllo non supporta l'evento di doppio clic.</span><span class="sxs-lookup"><span data-stu-id="e2dd9-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="e2dd9-108">Per rispondere a un clic del pulsante</span><span class="sxs-lookup"><span data-stu-id="e2dd9-108">To respond to a button click</span></span>  
  
- <span data-ttu-id="e2dd9-109">Nel `Click` del pulsante <xref:System.EventHandler> scrivere il codice per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e2dd9-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="e2dd9-110">`Button1_Click` deve essere associato al controllo.</span><span class="sxs-lookup"><span data-stu-id="e2dd9-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="e2dd9-111">Per altre informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e2dd9-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e2dd9-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2dd9-112">See also</span></span>

- [<span data-ttu-id="e2dd9-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="e2dd9-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="e2dd9-114">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e2dd9-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="e2dd9-115">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="e2dd9-115">Button Control</span></span>](button-control-windows-forms.md)
