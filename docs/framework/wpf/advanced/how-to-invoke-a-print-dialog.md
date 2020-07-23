---
title: 'Procedura: richiamare una finestra di dialogo di stampa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 75a4160366766efbd19d6e8ae26fbec102e7f95b
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924500"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="63246-102">Procedura: richiamare una finestra di dialogo di stampa</span><span class="sxs-lookup"><span data-stu-id="63246-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="63246-103">Per consentire la stampa dall'applicazione, è possibile creare e aprire semplicemente un <xref:System.Windows.Controls.PrintDialog> oggetto.</span><span class="sxs-lookup"><span data-stu-id="63246-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63246-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="63246-104">Example</span></span>  
 <span data-ttu-id="63246-105">Il <xref:System.Windows.Controls.PrintDialog> controllo fornisce un singolo punto di ingresso per l' [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] invio di processi, configurazione e XPS.</span><span class="sxs-lookup"><span data-stu-id="63246-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and XPS job submission.</span></span> <span data-ttu-id="63246-106">Il controllo è facile da usare ed è possibile crearne un'istanza usando il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup o il codice.</span><span class="sxs-lookup"><span data-stu-id="63246-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="63246-107">Nell'esempio seguente viene illustrato come creare un'istanza di e come aprire il controllo nel codice e come stamparlo.</span><span class="sxs-lookup"><span data-stu-id="63246-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="63246-108">Viene inoltre illustrato come assicurarsi che la finestra di dialogo fornisca all'utente la possibilità di impostare un intervallo specifico di pagine.</span><span class="sxs-lookup"><span data-stu-id="63246-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="63246-109">Nel codice di esempio si presuppone che esista un file FixedDocumentSequence. XPS nella radice dell'unità C:.</span><span class="sxs-lookup"><span data-stu-id="63246-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="63246-110">Una volta aperta la finestra di dialogo, gli utenti saranno in grado di effettuare una selezione tra le stampanti installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="63246-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="63246-111">Hanno inoltre la possibilità di selezionare il writer di [documenti XPS Microsoft](/windows/win32/printdocs/microsoft-xps-document-writer) per creare un file XPS (XML Paper Specification) anziché stampare.</span><span class="sxs-lookup"><span data-stu-id="63246-111">They will also have the option of selecting the [Microsoft XPS Document Writer](/windows/win32/printdocs/microsoft-xps-document-writer) to create an XML Paper Specification (XPS) file instead of printing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="63246-112">Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo di WPF, descritto in questo argomento, non dovrebbe essere confuso con il <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente di Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="63246-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of WPF, which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="63246-113">In modo esplicito, è possibile usare il <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> metodo senza mai aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="63246-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="63246-114">In questo senso, il controllo può essere usato come componente di stampa non visibile.</span><span class="sxs-lookup"><span data-stu-id="63246-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="63246-115">Tuttavia, per motivi di prestazioni, è preferibile usare il <xref:System.Printing.PrintQueue.AddJob%2A> metodo o uno dei molti <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> metodi e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> di <xref:System.Windows.Xps.XpsDocumentWriter> .</span><span class="sxs-lookup"><span data-stu-id="63246-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="63246-116">Per ulteriori informazioni, vedere la pagina relativa alla [stampa di file XPS a livello di codice](how-to-programmatically-print-xps-files.md).</span><span class="sxs-lookup"><span data-stu-id="63246-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63246-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63246-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="63246-118">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="63246-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="63246-119">Cenni preliminari sulla stampa</span><span class="sxs-lookup"><span data-stu-id="63246-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="63246-120">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="63246-120">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
