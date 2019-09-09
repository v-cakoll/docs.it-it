---
title: Cenni preliminari sul componente PrintDocument (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928981"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="d22e4-102">Cenni preliminari sul componente PrintDocument (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="d22e4-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="d22e4-103">Il componente [PrintDocument](printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="d22e4-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="d22e4-104">Può essere usato insieme al componente [PrintDialog](printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.</span><span class="sxs-lookup"><span data-stu-id="d22e4-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="d22e4-105">Utilizzo del componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="d22e4-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="d22e4-106">Due degli scenari principali che coinvolgono il <xref:System.Drawing.Printing.PrintDocument> componente sono:</span><span class="sxs-lookup"><span data-stu-id="d22e4-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="d22e4-107">Processi di stampa semplici, come la stampa di un singolo file di testo.</span><span class="sxs-lookup"><span data-stu-id="d22e4-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="d22e4-108">In tal caso, è necessario aggiungere il <xref:System.Drawing.Printing.PrintDocument> componente a un Windows Form, quindi aggiungere la logica di programmazione che stampa un file <xref:System.Drawing.Printing.PrintDocument.PrintPage> nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="d22e4-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="d22e4-109">La logica di programmazione deve culminare con <xref:System.Drawing.Printing.PrintDocument.Print%2A> il metodo per stampare il documento.</span><span class="sxs-lookup"><span data-stu-id="d22e4-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="d22e4-110">Questo metodo invia alla <xref:System.Drawing.Graphics> stampante un oggetto, contenuto <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> nella proprietà della <xref:System.Drawing.Printing.PrintPageEventArgs> classe.</span><span class="sxs-lookup"><span data-stu-id="d22e4-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="d22e4-111">Per un esempio in cui viene illustrato come stampare un documento di testo <xref:System.Drawing.Printing.PrintDocument> utilizzando il componente [, vedere Procedura: Stampare un file di testo con più pagine in](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d22e4-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="d22e4-112">Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata.</span><span class="sxs-lookup"><span data-stu-id="d22e4-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="d22e4-113">In tal caso, è necessario derivare un nuovo componente dal <xref:System.Drawing.Printing.PrintDocument> componente ed eseguire l'override (vedere [sostituzioni](../../../visual-basic/language-reference/modifiers/overrides.md) per Visual Basic C#o <xref:System.Drawing.Printing.PrintDocument.PrintPage> [override](../../../csharp/language-reference/keywords/override.md) per) l'evento.</span><span class="sxs-lookup"><span data-stu-id="d22e4-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](../../../csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="d22e4-114">Quando viene aggiunto a un modulo, il <xref:System.Drawing.Printing.PrintDocument> componente viene visualizzato nella barra delle applicazioni nella parte inferiore del progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d22e4-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="d22e4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d22e4-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="d22e4-116">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d22e4-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="d22e4-117">PrintDocument (componente)</span><span class="sxs-lookup"><span data-stu-id="d22e4-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
