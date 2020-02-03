---
title: Cenni preliminari sul componente PrintDocument
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a82cc0cdcb8cfae796c9c6bf60ab73873f85a291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728546"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="4ba71-102">Cenni preliminari sul componente PrintDocument (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="4ba71-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="4ba71-103">Il componente [PrintDocument](printdocument-component-windows-forms.md) di Windows Forms viene usato per impostare le proprietà che descrivono cosa stampare e per stampare quindi il documento nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="4ba71-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="4ba71-104">Può essere usato insieme al componente [PrintDialog](printdialog-component-windows-forms.md) per controllare tutti gli aspetti della stampa dei documenti.</span><span class="sxs-lookup"><span data-stu-id="4ba71-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="4ba71-105">Utilizzo del componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="4ba71-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="4ba71-106">Due degli scenari principali che coinvolgono il componente <xref:System.Drawing.Printing.PrintDocument> sono:</span><span class="sxs-lookup"><span data-stu-id="4ba71-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="4ba71-107">Processi di stampa semplici, come la stampa di un singolo file di testo.</span><span class="sxs-lookup"><span data-stu-id="4ba71-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="4ba71-108">In tal caso, è necessario aggiungere il componente <xref:System.Drawing.Printing.PrintDocument> a un Windows Form, quindi aggiungere la logica di programmazione che stampa un file nel gestore dell'evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="4ba71-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="4ba71-109">La logica di programmazione deve culminare con il metodo <xref:System.Drawing.Printing.PrintDocument.Print%2A> per stampare il documento.</span><span class="sxs-lookup"><span data-stu-id="4ba71-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="4ba71-110">Questo metodo invia alla stampante un oggetto <xref:System.Drawing.Graphics>, contenuto nella proprietà <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> della classe <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="4ba71-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="4ba71-111">Per un esempio in cui viene illustrato come stampare un documento di testo usando il componente <xref:System.Drawing.Printing.PrintDocument>, vedere [procedura: stampare un file di testo con più pagine in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4ba71-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="4ba71-112">Processi di stampa più complessi, come i casi in cui è necessario riutilizzare la logica di stampa creata.</span><span class="sxs-lookup"><span data-stu-id="4ba71-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="4ba71-113">In tal caso, è necessario derivare un nuovo componente dal componente <xref:System.Drawing.Printing.PrintDocument> ed eseguire l'override (vedere [sostituzioni](../../../visual-basic/language-reference/modifiers/overrides.md) per Visual Basic C#o [override](../../../csharp/language-reference/keywords/override.md) per) <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento.</span><span class="sxs-lookup"><span data-stu-id="4ba71-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](../../../csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="4ba71-114">Quando viene aggiunto a un modulo, il componente <xref:System.Drawing.Printing.PrintDocument> viene visualizzato nella barra delle applicazioni nella parte inferiore della Progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4ba71-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ba71-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ba71-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="4ba71-116">Supporto per la stampa in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ba71-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="4ba71-117">Componente PrintDocument</span><span class="sxs-lookup"><span data-stu-id="4ba71-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
