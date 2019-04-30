---
title: Supporto per la stampa in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011848"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="73ad4-102">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="73ad4-102">Windows Forms Print Support</span></span>
<span data-ttu-id="73ad4-103">Stampa in Windows Form è costituita principalmente tramite il [sul componente PrintDocument](../controls/printdocument-component-windows-forms.md) componente per consentire all'utente di stampare e il [controllo PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) controllo, [PrintDialog Componente](../controls/printdialog-component-windows-forms.md) e [componente PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) componenti per fornire un'interfaccia grafica familiare agli utenti di familiarizzare con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="73ad4-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="73ad4-104">In genere, si crea una nuova istanza della <xref:System.Drawing.Printing.PrintDocument> componente, impostare le proprietà che descrivono cosa stampare utilizzando la <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> classi e chiamare il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo effettivamente stampa del documento.</span><span class="sxs-lookup"><span data-stu-id="73ad4-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="73ad4-105">Nel corso di stampa da un'applicazione basata su Windows, il <xref:System.Drawing.Printing.PrintDocument> componente consentirà di visualizzare la finestra di dialogo Stampa abort per avvisare gli utenti per il fatto che è in corso la stampa e per consentire il processo di stampa deve essere annullata.</span><span class="sxs-lookup"><span data-stu-id="73ad4-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73ad4-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="73ad4-106">In This Section</span></span>  
 [<span data-ttu-id="73ad4-107">Procedura: Creare processi di stampa Standard di Windows Form</span><span class="sxs-lookup"><span data-stu-id="73ad4-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="73ad4-108">Viene illustrato come utilizzare il <xref:System.Drawing.Printing.PrintDocument> componente stampare da un modulo di Windows.</span><span class="sxs-lookup"><span data-stu-id="73ad4-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="73ad4-109">Procedura: Acquisire l'Input dell'utente da un elemento PrintDialog in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="73ad4-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="73ad4-110">Viene spiegato come modificare alcune opzioni di stampa a livello di codice usando il <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="73ad4-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="73ad4-111">Procedura: Selezionare le stampanti connesse al Computer dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="73ad4-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="73ad4-112">Viene descritto come cambiare la stampante per stampare utilizzando la <xref:System.Windows.Forms.PrintDialog> componente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73ad4-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="73ad4-113">Procedura: Stampare grafica in Windows Form</span><span class="sxs-lookup"><span data-stu-id="73ad4-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="73ad4-114">Descrive l'invio della grafica per la stampante.</span><span class="sxs-lookup"><span data-stu-id="73ad4-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="73ad4-115">Procedura: Stampare un File di testo con più pagine in Windows Form</span><span class="sxs-lookup"><span data-stu-id="73ad4-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="73ad4-116">Descrive il testo inviano alla stampante.</span><span class="sxs-lookup"><span data-stu-id="73ad4-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="73ad4-117">Procedura: Processi di stampa di Windows completo form</span><span class="sxs-lookup"><span data-stu-id="73ad4-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="73ad4-118">Viene illustrato come gli utenti per il completamento di un processo di stampa di avviso.</span><span class="sxs-lookup"><span data-stu-id="73ad4-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="73ad4-119">Procedura: Stampare un Windows Form</span><span class="sxs-lookup"><span data-stu-id="73ad4-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="73ad4-120">Viene illustrato come stampare una copia del modulo corrente.</span><span class="sxs-lookup"><span data-stu-id="73ad4-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="73ad4-121">Procedura: Stampa in Windows Form tramite l'anteprima di stampa</span><span class="sxs-lookup"><span data-stu-id="73ad4-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="73ad4-122">Viene illustrato come utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> per stampare un documento.</span><span class="sxs-lookup"><span data-stu-id="73ad4-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="73ad4-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="73ad4-123">Related Sections</span></span>  
 [<span data-ttu-id="73ad4-124">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="73ad4-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="73ad4-125">Illustra l'utilizzo del <xref:System.Drawing.Printing.PrintDocument> componente.</span><span class="sxs-lookup"><span data-stu-id="73ad4-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="73ad4-126">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="73ad4-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="73ad4-127">Illustra l'utilizzo del <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="73ad4-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="73ad4-128">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="73ad4-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="73ad4-129">Illustra l'utilizzo del <xref:System.Windows.Forms.PrintPreviewDialog> controllo.</span><span class="sxs-lookup"><span data-stu-id="73ad4-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="73ad4-130">Componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="73ad4-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="73ad4-131">Illustra l'utilizzo del <xref:System.Windows.Forms.PageSetupDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="73ad4-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="73ad4-132">Vengono descritte le classi di <xref:System.Drawing.Printing> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="73ad4-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
