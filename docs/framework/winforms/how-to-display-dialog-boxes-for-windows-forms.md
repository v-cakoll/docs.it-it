---
title: 'Procedura: Visualizzare le finestre di dialogo per Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: b99f2273dae88faf86448da6e1d2986a83803abf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311084"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="80ead-102">Procedura: Visualizzare le finestre di dialogo per Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80ead-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="80ead-103">Visualizzare una finestra di dialogo nello stesso modo che visualizzare qualsiasi altra forma in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="80ead-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="80ead-104">Form di avvio viene caricata automaticamente quando viene eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="80ead-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="80ead-105">Per rendere un secondo form o finestra di dialogo visualizzata nell'applicazione, scrivere codice per caricare e visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="80ead-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="80ead-106">In modo analogo, per consentire il form o finestra di dialogo casella scomparsa, scrivere il codice per scaricare o nasconderlo.</span><span class="sxs-lookup"><span data-stu-id="80ead-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="80ead-107">Per visualizzare una finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="80ead-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="80ead-108">Passare al gestore dell'evento a cui si desidera aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="80ead-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="80ead-109">Questa situazione può verificarsi quando un comando di menu è selezionato, quando viene selezionato un pulsante o quando si verifica qualsiasi altro evento.</span><span class="sxs-lookup"><span data-stu-id="80ead-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="80ead-110">Nel gestore dell'evento, aggiungere codice per aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="80ead-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="80ead-111">In questo esempio, un evento click del pulsante consente di visualizzare la finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="80ead-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
