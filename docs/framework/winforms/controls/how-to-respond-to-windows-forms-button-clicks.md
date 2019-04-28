---
title: 'Procedura: Rispondere alla selezione dei pulsanti Windows Forms'
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
ms.openlocfilehash: a10eaa3ea62df9301a53f5609b503bfabcb50a46
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913081"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="d133b-102">Procedura: Rispondere alla selezione dei pulsanti Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d133b-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="d133b-103">L'utilizzo di base di un form Windows <xref:System.Windows.Forms.Button> controllo consiste nell'eseguire codice quando si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="d133b-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="d133b-104">Facendo clic su un <xref:System.Windows.Forms.Button> controllo genera inoltre un numero di altri eventi, ad esempio il <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, e <xref:System.Windows.Forms.Control.MouseUp> eventi.</span><span class="sxs-lookup"><span data-stu-id="d133b-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="d133b-105">Se si prevede di collegare i gestori eventi per questi eventi correlati, assicurarsi che le relative azioni non sono in conflitto.</span><span class="sxs-lookup"><span data-stu-id="d133b-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="d133b-106">Ad esempio, se facendo clic sul pulsante Cancella le informazioni che l'utente ha digitato in una casella di testo, quando si posiziona il puntatore del mouse su pulsante non visualizzerà una descrizione comando con le informazioni ora inesistente.</span><span class="sxs-lookup"><span data-stu-id="d133b-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="d133b-107">Se l'utente tenta di fare doppio clic il <xref:System.Windows.Forms.Button> controllo, ogni clic verranno elaborate separatamente; vale a dire, il controllo non supporta l'evento doppio clic.</span><span class="sxs-lookup"><span data-stu-id="d133b-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="d133b-108">Per rispondere a un clic del pulsante</span><span class="sxs-lookup"><span data-stu-id="d133b-108">To respond to a button click</span></span>  
  
- <span data-ttu-id="d133b-109">Nel pulsante `Click` <xref:System.EventHandler> scrivere il codice da eseguire.</span><span class="sxs-lookup"><span data-stu-id="d133b-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="d133b-110">`Button1_Click` deve essere associato al controllo.</span><span class="sxs-lookup"><span data-stu-id="d133b-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="d133b-111">Per altre informazioni, vedere [Procedura: Creare i gestori eventi in fase di esecuzione per Windows Form](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d133b-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d133b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d133b-112">See also</span></span>

- [<span data-ttu-id="d133b-113">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="d133b-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="d133b-114">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="d133b-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="d133b-115">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="d133b-115">Button Control</span></span>](button-control-windows-forms.md)
