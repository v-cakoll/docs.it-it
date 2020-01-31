---
title: 'Procedura: visualizzare le finestre di dialogo'
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
ms.openlocfilehash: dd04a06eaa0dd7583ef2f72edb4cffa99aaaa60c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739457"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="3c2d7-102">Procedura: Visualizzare le finestre di dialogo per Windows Form</span><span class="sxs-lookup"><span data-stu-id="3c2d7-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="3c2d7-103">Viene visualizzata una finestra di dialogo in modo analogo alla visualizzazione di qualsiasi altro modulo in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3c2d7-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="3c2d7-104">Il modulo di avvio viene caricato automaticamente quando viene eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3c2d7-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="3c2d7-105">Per fare in modo che nell'applicazione venga visualizzato un secondo form o una finestra di dialogo, scrivere il codice per caricarlo e visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="3c2d7-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="3c2d7-106">Analogamente, per far scomparire il form o la finestra di dialogo, scrivere il codice per scaricarlo o nasconderlo.</span><span class="sxs-lookup"><span data-stu-id="3c2d7-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="3c2d7-107">Per visualizzare una finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="3c2d7-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="3c2d7-108">Passare al gestore eventi con il quale si desidera aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3c2d7-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="3c2d7-109">Questa situazione può verificarsi quando si seleziona un comando di menu, quando si fa clic su un pulsante o quando si verifica un altro evento.</span><span class="sxs-lookup"><span data-stu-id="3c2d7-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="3c2d7-110">Nel gestore eventi aggiungere il codice per aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="3c2d7-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="3c2d7-111">In questo esempio viene usato un evento clic del pulsante per visualizzare la finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="3c2d7-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
