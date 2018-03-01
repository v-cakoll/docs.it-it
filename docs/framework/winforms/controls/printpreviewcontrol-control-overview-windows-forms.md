---
title: Cenni preliminari sul controllo PrintPreviewControl (Windows Form)
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
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d50e772cf870d47314a25347f4909367062ffb94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="26f16-102">Cenni preliminari sul controllo PrintPreviewControl (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="26f16-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="26f16-103">Windows Form <xref:System.Windows.Forms.PrintPreviewControl> viene utilizzato per visualizzare un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) così come verrà stampato.</span><span class="sxs-lookup"><span data-stu-id="26f16-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="26f16-104">Il controllo non dispone di alcun pulsante o altri elementi dell'interfaccia utente, pertanto, in genere <xref:System.Windows.Forms.PrintPreviewControl> viene usato solo se si vuole creare un'interfaccia utente di anteprima di stampa personalizzata.</span><span class="sxs-lookup"><span data-stu-id="26f16-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="26f16-105">Se si desidera che l'interfaccia utente standard, utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> controllare; vedere [Cenni preliminari sul controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) per una panoramica.</span><span class="sxs-lookup"><span data-stu-id="26f16-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="26f16-106">Proprietà chiave</span><span class="sxs-lookup"><span data-stu-id="26f16-106">Key Properties</span></span>  
 <span data-ttu-id="26f16-107">Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, che imposta il documento da visualizzare in anteprima.</span><span class="sxs-lookup"><span data-stu-id="26f16-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="26f16-108">Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto.</span><span class="sxs-lookup"><span data-stu-id="26f16-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="26f16-109">Per una panoramica della creazione di documenti per la stampa, vedere [Cenni preliminari sul componente PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) e [il supporto di stampa di Windows Form](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span><span class="sxs-lookup"><span data-stu-id="26f16-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="26f16-110">Il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> determinano il numero di pagine visualizzate orizzontalmente e verticalmente il controllo.</span><span class="sxs-lookup"><span data-stu-id="26f16-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="26f16-111">Anti-aliasing può visualizzare il testo più uniforme, ma può inoltre consentire la visualizzazione. Per utilizzarla, impostare il <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="26f16-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26f16-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26f16-112">See Also</span></span>  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [<span data-ttu-id="26f16-113">Cenni preliminari sul controllo PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="26f16-113">PrintPreviewDialog Control Overview</span></span>](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [<span data-ttu-id="26f16-114">Controllo PrintPreviewControl</span><span class="sxs-lookup"><span data-stu-id="26f16-114">PrintPreviewControl Control</span></span>](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [<span data-ttu-id="26f16-115">Controlli e componenti della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="26f16-115">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
