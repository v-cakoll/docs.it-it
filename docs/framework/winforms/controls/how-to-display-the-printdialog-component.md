---
title: Come visualizzare il componente PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 198ae75d407bd1837033a1cc186d84ff972fdc2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941570"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="0ff2a-102">Come visualizzare il componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="0ff2a-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="0ff2a-103">Il <xref:System.Windows.Forms.PrintDialog> componente è la finestra di dialogo Stampa di Windows standard che molti utenti risulterà familiare con.</span><span class="sxs-lookup"><span data-stu-id="0ff2a-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="0ff2a-104">Poiché gli utenti saranno subito in grado di con esso, si rivela particolarmente vantaggioso per l'utilizzo di <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="0ff2a-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="0ff2a-105">Per visualizzare il componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="0ff2a-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="0ff2a-106">Chiamare il <xref:System.Windows.Forms.Form.ShowDialog%2A> metodo dal codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0ff2a-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="0ff2a-107">Una volta visualizzato il componente, gli utenti potranno usarlo, impostando le proprietà del processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="0ff2a-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="0ff2a-108">Queste proprietà vengono salvate nel <xref:System.Drawing.Printing.PrinterSettings> classe (e il <xref:System.Drawing.Printing.PageSettings> classe, se l'utente accede il [componente PageSetupDialog](pagesetupdialog-component-windows-forms.md) attraverso il <xref:System.Windows.Forms.PrintDialog> componente) associata al processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="0ff2a-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="0ff2a-109">Sarà quindi possibile effettuare chiamate alle proprietà così impostate per determinare le specifiche del processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="0ff2a-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="0ff2a-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ff2a-110">See also</span></span>

- [<span data-ttu-id="0ff2a-111">Procedura: Creare processi di stampa Standard di Windows Form</span><span class="sxs-lookup"><span data-stu-id="0ff2a-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="0ff2a-112">Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="0ff2a-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="0ff2a-113">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="0ff2a-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="0ff2a-114">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="0ff2a-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="0ff2a-115">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ff2a-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="0ff2a-116">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="0ff2a-116">Windows Forms Controls</span></span>](index.md)