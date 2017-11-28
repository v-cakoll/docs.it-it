---
title: 'Procedura: Visualizzare il componente PrintDialog'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7e1162a4e926d5be35f8f7bb7cdeb92264f293aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="2ab31-102">Procedura: Visualizzare il componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="2ab31-102">How to: Display the PrintDialog Component</span></span>
<span data-ttu-id="2ab31-103">Il <xref:System.Windows.Forms.PrintDialog> componente è la casella di dialogo di stampa Windows standard che familiarità con molti utenti.</span><span class="sxs-lookup"><span data-stu-id="2ab31-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="2ab31-104">Poiché gli utenti saranno immediatamente dimestichezza, si rivela particolarmente vantaggioso per l'utilizzo di <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="2ab31-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
### <a name="to-display-the-printdialog-component"></a><span data-ttu-id="2ab31-105">Per visualizzare il componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="2ab31-105">To display the PrintDialog component</span></span>  
  
-   <span data-ttu-id="2ab31-106">Chiamare il <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo all'interno di codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2ab31-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>  
  
     <span data-ttu-id="2ab31-107">Una volta visualizzato il componente, gli utenti potranno usarlo, impostando le proprietà del processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="2ab31-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="2ab31-108">Queste proprietà vengono salvate nel <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` classe (e <xref:System.Drawing.Printing.PageSettings> classe, se l'utente accede il [PageSetupDialog (componente)](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) tramite il <xref:System.Windows.Forms.PrintDialog> componente) associata al processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="2ab31-108">These are saved in the <!--zz <xref:System.Drawing.Printing.PrinterSetting>--> `PrinterSetting` class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="2ab31-109">Sarà quindi possibile effettuare chiamate alle proprietà così impostate per determinare le specifiche del processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="2ab31-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab31-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ab31-110">See Also</span></span>  
 [<span data-ttu-id="2ab31-111">Procedura: Creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="2ab31-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="2ab31-112">Procedura: Acquisire l'input dell'utente da un elemento PrintDialog in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="2ab31-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 [<span data-ttu-id="2ab31-113">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="2ab31-113">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [<span data-ttu-id="2ab31-114">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="2ab31-114">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 [<span data-ttu-id="2ab31-115">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2ab31-115">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="2ab31-116">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="2ab31-116">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
