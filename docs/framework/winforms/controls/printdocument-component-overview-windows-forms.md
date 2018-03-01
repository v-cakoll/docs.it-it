---
title: Cenni preliminari sul componente PrintDocument (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 414a7972550558b40403b7f4cbfd9a49194666be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="58a3e-102">Cenni preliminari sul componente PrintDocument (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="58a3e-102">PrintDocument Component Overview (Windows Forms)</span></span>
<span data-ttu-id="58a3e-103">Il componente [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="58a3e-103">The Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="58a3e-104">Può essere usato insieme al componente [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.</span><span class="sxs-lookup"><span data-stu-id="58a3e-104">It can be used in conjunction with the [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>  
  
## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="58a3e-105">Utilizzo del componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="58a3e-105">Working with the PrintDocument Component</span></span>  
 <span data-ttu-id="58a3e-106">Due dei principali scenari che comportano la <xref:System.Drawing.Printing.PrintDocument> componente sono:</span><span class="sxs-lookup"><span data-stu-id="58a3e-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>  
  
-   <span data-ttu-id="58a3e-107">Processi di stampa semplici, come la stampa di un singolo file di testo.</span><span class="sxs-lookup"><span data-stu-id="58a3e-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="58a3e-108">In questo caso si aggiunge il <xref:System.Drawing.Printing.PrintDocument> componente a un Windows Form, quindi aggiungere la logica di programmazione che consente di stampare un file nel <xref:System.Drawing.Printing.PrintDocument.PrintPage> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="58a3e-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="58a3e-109">La logica di programmazione dovrebbe culminare con il <xref:System.Drawing.Printing.PrintDocument.Print%2A> metodo per stampare il documento.</span><span class="sxs-lookup"><span data-stu-id="58a3e-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="58a3e-110">Questo metodo invia un <xref:System.Drawing.Graphics> oggetto, contenuto nella <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> proprietà del <xref:System.Drawing.Printing.PrintPageEventArgs> (classe), alla stampante.</span><span class="sxs-lookup"><span data-stu-id="58a3e-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="58a3e-111">Per un esempio che illustra come stampare un documento di testo utilizzando il <xref:System.Drawing.Printing.PrintDocument> componente, vedere [procedura: stampare un File di testo a più pagine in Windows Form](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="58a3e-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="58a3e-112">Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata.</span><span class="sxs-lookup"><span data-stu-id="58a3e-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="58a3e-113">In questo caso derivare un nuovo componente dal <xref:System.Drawing.Printing.PrintDocument> componente ed eseguire l'override (vedere [esegue l'override](~/docs/visual-basic/language-reference/modifiers/overrides.md) per Visual Basic o [override](~/docs/csharp/language-reference/keywords/override.md) per c#) di <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.</span><span class="sxs-lookup"><span data-stu-id="58a3e-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](~/docs/visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](~/docs/csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
 <span data-ttu-id="58a3e-114">Quando viene aggiunto a un modulo, il <xref:System.Drawing.Printing.PrintDocument> componente viene visualizzato nella barra delle applicazioni nella parte inferiore della finestra di progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="58a3e-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a3e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58a3e-115">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="58a3e-116">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58a3e-116">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [<span data-ttu-id="58a3e-117">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="58a3e-117">PrintDocument Component</span></span>](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
