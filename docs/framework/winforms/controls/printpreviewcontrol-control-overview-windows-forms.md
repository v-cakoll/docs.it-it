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
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewControl (Windows Form)
Windows Form <xref:System.Windows.Forms.PrintPreviewControl> viene utilizzato per visualizzare un [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) così come verrà stampato. Il controllo non dispone di alcun pulsante o altri elementi dell'interfaccia utente, pertanto, in genere <xref:System.Windows.Forms.PrintPreviewControl> viene usato solo se si vuole creare un'interfaccia utente di anteprima di stampa personalizzata. Se si desidera che l'interfaccia utente standard, utilizzare un <xref:System.Windows.Forms.PrintPreviewDialog> controllare; vedere [Cenni preliminari sul controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md) per una panoramica.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, che imposta il documento da visualizzare in anteprima. Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto. Per una panoramica della creazione di documenti per la stampa, vedere [Cenni preliminari sul componente PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) e [il supporto di stampa di Windows Form](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md). Il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> determinano il numero di pagine visualizzate orizzontalmente e verticalmente il controllo. Anti-aliasing può visualizzare il testo più uniforme, ma può inoltre consentire la visualizzazione. Per utilizzarla, impostare il <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> proprietà `true`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.PrintPreviewControl>  
 [Cenni preliminari sul controllo PrintPreviewDialog](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)  
 [Controllo PrintPreviewControl](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)  
 [Controlli e componenti della finestra di dialogo](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)
