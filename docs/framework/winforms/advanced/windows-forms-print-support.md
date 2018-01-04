---
title: Supporto per la stampa in Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81f89ee41eb9f8b492ab12e30ae4580cdffbd8f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="5db1b-102">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5db1b-102">Windows Forms Print Support</span></span>
<span data-ttu-id="5db1b-103">Stampa in Windows Form è costituita principalmente tramite il [sul componente PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) componente per consentire all'utente di stampare e il [controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) controllo [PrintDialog Componente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) e [componente PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) i componenti per fornire un'interfaccia grafica familiare agli utenti di familiarizzare con il sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="5db1b-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="5db1b-104">In genere, si crea una nuova istanza del <xref:System.Drawing.Printing.PrintDocument> componente, impostare le proprietà che descrivono cosa stampare utilizzando il <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> classi e chiamare il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo per stampare il documento.</span><span class="sxs-lookup"><span data-stu-id="5db1b-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="5db1b-105">Nel corso di stampa da un'applicazione basata su Windows, il <xref:System.Drawing.Printing.PrintDocument> componente consentirà di visualizzare la finestra di dialogo Stampa interruzione per avvisare gli utenti per il fatto che si verifichi la stampa e per consentire il processo di stampa deve essere annullato.</span><span class="sxs-lookup"><span data-stu-id="5db1b-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5db1b-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="5db1b-106">In This Section</span></span>  
 [<span data-ttu-id="5db1b-107">Procedura: Creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="5db1b-107">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="5db1b-108">Viene illustrato come utilizzare il <xref:System.Drawing.Printing.PrintDocument> per stampare da un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="5db1b-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="5db1b-109">Procedura: Acquisire l'input dell'utente da un elemento PrintDialog in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="5db1b-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="5db1b-110">Viene descritto come modificare alcune opzioni di stampa a livello di codice utilizzando il <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="5db1b-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="5db1b-111">Procedura: Selezionare le stampanti connesse al computer dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5db1b-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="5db1b-112">Viene descritto come cambiare la stampante per stampare utilizzando il <xref:System.Windows.Forms.PrintDialog> componente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5db1b-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="5db1b-113">Procedura: stampare grafica in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5db1b-113">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="5db1b-114">Descrive l'invio di grafica per la stampante.</span><span class="sxs-lookup"><span data-stu-id="5db1b-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="5db1b-115">Procedura: stampare un file di testo con più pagine in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5db1b-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="5db1b-116">Descrive l'invio di testo alla stampante.</span><span class="sxs-lookup"><span data-stu-id="5db1b-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="5db1b-117">Procedura: Completare processi di stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5db1b-117">How to: Complete Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="5db1b-118">Viene illustrato come avvisare gli utenti per il completamento di un processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="5db1b-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="5db1b-119">Procedura: Stampare un Windows Form</span><span class="sxs-lookup"><span data-stu-id="5db1b-119">How to: Print a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 <span data-ttu-id="5db1b-120">Viene illustrato come stampare una copia del modulo corrente.</span><span class="sxs-lookup"><span data-stu-id="5db1b-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="5db1b-121">Procedura: Stampare in Windows Form tramite l'anteprima di stampa</span><span class="sxs-lookup"><span data-stu-id="5db1b-121">How to: Print in Windows Forms Using Print Preview</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="5db1b-122">Viene illustrato come utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> per la stampa del documento.</span><span class="sxs-lookup"><span data-stu-id="5db1b-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5db1b-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5db1b-123">Related Sections</span></span>  
 [<span data-ttu-id="5db1b-124">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="5db1b-124">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="5db1b-125">Viene illustrato l'utilizzo del <xref:System.Drawing.Printing.PrintDocument> componente.</span><span class="sxs-lookup"><span data-stu-id="5db1b-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="5db1b-126">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="5db1b-126">PrintDialog Component</span></span>](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="5db1b-127">Viene illustrato l'utilizzo del <xref:System.Windows.Forms.PrintDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="5db1b-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="5db1b-128">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="5db1b-128">PrintPreviewDialog Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="5db1b-129">Viene illustrato l'utilizzo del <xref:System.Windows.Forms.PrintPreviewDialog> controllo.</span><span class="sxs-lookup"><span data-stu-id="5db1b-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="5db1b-130">Componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="5db1b-130">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="5db1b-131">Viene illustrato l'utilizzo del <xref:System.Windows.Forms.PageSetupDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="5db1b-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="5db1b-132">Vengono descritte le classi di <xref:System.Drawing.Printing> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5db1b-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
