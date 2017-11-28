---
title: 'Procedura: visualizzare le finestre di dialogo per Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3f827e9052260c1b836246d38c55e2cb2a9e5cc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="b98b2-102">Procedura: visualizzare le finestre di dialogo per Windows Form</span><span class="sxs-lookup"><span data-stu-id="b98b2-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="b98b2-103">Viene visualizzata una finestra di dialogo nello stesso modo che visualizzare qualsiasi altra forma in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b98b2-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="b98b2-104">Il form di avvio carica automaticamente quando viene eseguita l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b98b2-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="b98b2-105">Per rendere un secondo form o finestra di dialogo visualizzata nell'applicazione, scrivere codice per caricare e visualizzarlo.</span><span class="sxs-lookup"><span data-stu-id="b98b2-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="b98b2-106">Analogamente, per rendere il modulo o finestra di dialogo casella scomparsa, scrivere il codice per scaricare o nasconderla.</span><span class="sxs-lookup"><span data-stu-id="b98b2-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="b98b2-107">Per visualizzare una finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="b98b2-107">To display a dialog box</span></span>  
  
1.  <span data-ttu-id="b98b2-108">Passare al gestore dell'evento a cui si desidera aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b98b2-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="b98b2-109">Questa situazione può verificarsi quando un comando di menu è selezionato, quando viene premuto un pulsante o quando si verifica qualsiasi altro evento.</span><span class="sxs-lookup"><span data-stu-id="b98b2-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2.  <span data-ttu-id="b98b2-110">Nel gestore eventi, aggiungere il codice per aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b98b2-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="b98b2-111">In questo esempio viene utilizzato un evento clic sul pulsante per visualizzare la finestra di dialogo:</span><span class="sxs-lookup"><span data-stu-id="b98b2-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
