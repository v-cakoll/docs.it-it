---
title: 'Procedura: richiamare una finestra di dialogo di stampa'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ba541b367e56a809fa444528dccd69860c4de46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="864f7-102">Procedura: richiamare una finestra di dialogo di stampa</span><span class="sxs-lookup"><span data-stu-id="864f7-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="864f7-103">Per fornire la possibilità di stampa dall'applicazione, è possibile semplicemente creare e aprire un <xref:System.Windows.Controls.PrintDialog> oggetto.</span><span class="sxs-lookup"><span data-stu-id="864f7-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="864f7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="864f7-104">Example</span></span>  
 <span data-ttu-id="864f7-105">Il controllo <xref:System.Windows.Controls.PrintDialog> rappresenta un singolo punto di ingresso per l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], la configurazione e l'invio di processi [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)].</span><span class="sxs-lookup"><span data-stu-id="864f7-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="864f7-106">Il controllo è facile da usare e può essere creata un'istanza tramite [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup o codice.</span><span class="sxs-lookup"><span data-stu-id="864f7-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="864f7-107">Nell'esempio seguente viene illustrato come creare un'istanza e aprire il controllo nel codice e come stampare da esso.</span><span class="sxs-lookup"><span data-stu-id="864f7-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="864f7-108">Viene inoltre illustrato come assicurarsi che la finestra di dialogo consenta all'utente la possibilità di impostare un intervallo specifico di pagine.</span><span class="sxs-lookup"><span data-stu-id="864f7-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="864f7-109">Nell'esempio di codice si presuppone che sia presente un file FixedDocumentSequence. XPS nella radice dell'unità c.</span><span class="sxs-lookup"><span data-stu-id="864f7-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="864f7-110">Dopo avere aperto la finestra di dialogo, è possibile che gli utenti saranno in grado di selezionare le stampanti installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="864f7-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="864f7-111">Hanno inoltre la possibilità di selezionare il [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) per creare un [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file anziché la stampa.</span><span class="sxs-lookup"><span data-stu-id="864f7-111">They will also have the option of selecting the [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="864f7-112">Il <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> controllo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], illustrata in questo argomento, non deve essere confuso con il <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> componente di [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="864f7-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="864f7-113">In teoria, è possibile utilizzare il <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> metodo senza mai aprire la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="864f7-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="864f7-114">In tal senso, il controllo può essere utilizzato come un componente di stampa non visibili.</span><span class="sxs-lookup"><span data-stu-id="864f7-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="864f7-115">Ma per motivi di prestazioni, sarebbe preferibile utilizzare il di <xref:System.Printing.PrintQueue.AddJob%2A> metodo o una delle numerose <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> e <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> metodi il <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="864f7-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="864f7-116">Per ulteriori informazioni, vedere [a livello di programmazione i file di stampa XPS](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) e.</span><span class="sxs-lookup"><span data-stu-id="864f7-116">For more about this, see [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="864f7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="864f7-117">See Also</span></span>  
 <xref:System.Windows.Controls.PrintDialog>  
 [<span data-ttu-id="864f7-118">Documenti in WPF</span><span class="sxs-lookup"><span data-stu-id="864f7-118">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="864f7-119">Panoramica della stampa</span><span class="sxs-lookup"><span data-stu-id="864f7-119">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="864f7-120">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="864f7-120">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
