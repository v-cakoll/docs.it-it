---
title: Supporto stampa
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: d6e8f60db7afe2f1b04eaae6fe71aa93e5c22cae
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732499"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="0d013-102">Supporto per la stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d013-102">Windows Forms Print Support</span></span>
<span data-ttu-id="0d013-103">La stampa in Windows Forms è costituita principalmente dall'utilizzo del componente [PrintDocument](../controls/printdocument-component-windows-forms.md) per consentire all'utente di stampare e dal controllo di [controllo PrintPreviewDialog](../controls/printpreviewdialog-control-windows-forms.md) , dal [componente PrintDialog](../controls/printdialog-component-windows-forms.md) e dai componenti [PageSetupDialog](../controls/pagesetupdialog-component-windows-forms.md) per fornire un'interfaccia grafica familiare agli utenti abituati al sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="0d013-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="0d013-104">In genere, si crea una nuova istanza del componente <xref:System.Drawing.Printing.PrintDocument>, si impostano le proprietà che descrivono cosa stampare usando le classi <xref:System.Drawing.Printing.PrinterSettings> e <xref:System.Drawing.Printing.PageSettings> e si chiama il metodo <xref:System.Drawing.Printing.PrintDocument.Print%2A> per stampare effettivamente il documento.</span><span class="sxs-lookup"><span data-stu-id="0d013-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="0d013-105">Durante la stampa da un'applicazione basata su Windows, nel componente <xref:System.Drawing.Printing.PrintDocument> verrà visualizzata una finestra di dialogo Interrompi stampa per segnalare agli utenti il fatto che la stampa è in corso e per consentire l'annullamento del processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="0d013-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d013-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0d013-106">In This Section</span></span>  
 [<span data-ttu-id="0d013-107">Procedura: Creare processi di stampa standard per Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d013-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="0d013-108">Viene illustrato come utilizzare il componente <xref:System.Drawing.Printing.PrintDocument> per stampare da un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="0d013-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="0d013-109">Procedura: Acquisire l'input dell'utente da un elemento PrintDialog in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="0d013-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="0d013-110">Viene illustrato come modificare le opzioni di stampa selezionate a livello di codice utilizzando il componente <xref:System.Windows.Forms.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="0d013-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="0d013-111">Procedura: Selezionare le stampanti connesse al computer dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d013-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="0d013-112">Viene descritta la modifica della stampante per la stampa in utilizzando il componente <xref:System.Windows.Forms.PrintDialog> in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="0d013-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="0d013-113">Procedura: stampare grafica in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d013-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="0d013-114">Viene descritto come inviare grafica alla stampante.</span><span class="sxs-lookup"><span data-stu-id="0d013-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="0d013-115">Procedura: stampare un file di testo con più pagine in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0d013-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="0d013-116">Viene descritto come inviare testo alla stampante.</span><span class="sxs-lookup"><span data-stu-id="0d013-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="0d013-117">Procedura: Completare processi di stampa in Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d013-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="0d013-118">Viene illustrato come segnalare agli utenti il completamento di un processo di stampa.</span><span class="sxs-lookup"><span data-stu-id="0d013-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="0d013-119">Procedura: Stampare un Windows Form</span><span class="sxs-lookup"><span data-stu-id="0d013-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="0d013-120">Viene illustrato come stampare una copia del form corrente.</span><span class="sxs-lookup"><span data-stu-id="0d013-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="0d013-121">Procedura: Stampare in Windows Form tramite l'anteprima di stampa</span><span class="sxs-lookup"><span data-stu-id="0d013-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="0d013-122">Viene illustrato come utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> per la stampa di un documento.</span><span class="sxs-lookup"><span data-stu-id="0d013-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0d013-123">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0d013-123">Related Sections</span></span>  
 [<span data-ttu-id="0d013-124">Componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="0d013-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="0d013-125">Viene illustrato l'utilizzo del componente <xref:System.Drawing.Printing.PrintDocument>.</span><span class="sxs-lookup"><span data-stu-id="0d013-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="0d013-126">Componente PrintDialog</span><span class="sxs-lookup"><span data-stu-id="0d013-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="0d013-127">Viene illustrato l'utilizzo del componente <xref:System.Windows.Forms.PrintDialog>.</span><span class="sxs-lookup"><span data-stu-id="0d013-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="0d013-128">Controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="0d013-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="0d013-129">Viene illustrato l'utilizzo del controllo <xref:System.Windows.Forms.PrintPreviewDialog>.</span><span class="sxs-lookup"><span data-stu-id="0d013-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="0d013-130">Componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="0d013-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="0d013-131">Viene illustrato l'utilizzo del componente <xref:System.Windows.Forms.PageSetupDialog>.</span><span class="sxs-lookup"><span data-stu-id="0d013-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="0d013-132">Descrive le classi nello spazio dei nomi <xref:System.Drawing.Printing>.</span><span class="sxs-lookup"><span data-stu-id="0d013-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
