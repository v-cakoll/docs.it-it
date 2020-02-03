---
title: Designare un pulsante come pulsante Annulla
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743256"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="2f833-102">Procedura: Impostare un pulsante Windows Form come pulsante di annullamento</span><span class="sxs-lookup"><span data-stu-id="2f833-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="2f833-103">In qualsiasi Windows Form è possibile designare un controllo <xref:System.Windows.Forms.Button> come pulsante Annulla.</span><span class="sxs-lookup"><span data-stu-id="2f833-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="2f833-104">Quando l'utente preme il tasto ESC, viene fatto clic su un pulsante Annulla, indipendentemente da quale altro controllo nel form abbia lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="2f833-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="2f833-105">Un pulsante di questo tipo è in genere programmato per consentire all'utente di uscire rapidamente da un'operazione senza eseguire il commit in alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="2f833-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="2f833-106">Per impostare il pulsante Annulla</span><span class="sxs-lookup"><span data-stu-id="2f833-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="2f833-107">Impostare la proprietà <xref:System.Windows.Forms.Form.CancelButton%2A> del modulo sul controllo <xref:System.Windows.Forms.Button> appropriato.</span><span class="sxs-lookup"><span data-stu-id="2f833-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2f833-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f833-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="2f833-109">Panoramica sul controllo Button</span><span class="sxs-lookup"><span data-stu-id="2f833-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="2f833-110">Modalità di selezione di un controllo Button di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2f833-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="2f833-111">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2f833-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="2f833-112">Procedura: Designare un pulsante Windows Form come pulsante di conferma</span><span class="sxs-lookup"><span data-stu-id="2f833-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="2f833-113">Controllo Button</span><span class="sxs-lookup"><span data-stu-id="2f833-113">Button Control</span></span>](button-control-windows-forms.md)
