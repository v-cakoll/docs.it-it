---
title: Cenni preliminari sul controllo PrintPreviewControl (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: e9f1c2ae912b6beeba70c318b94a3052e2f99acb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59122499"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>Cenni preliminari sul controllo PrintPreviewControl (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.PrintPreviewControl> consente di visualizzare una [PrintDocument](printdocument-component-windows-forms.md) così come verrà stampato. Il controllo non dispone di alcun pulsante o altri elementi dell'interfaccia utente, pertanto, in genere <xref:System.Windows.Forms.PrintPreviewControl> viene usato solo se si vuole creare un'interfaccia utente di anteprima di stampa personalizzata. Se si vuole che l'interfaccia utente standard, usare una <xref:System.Windows.Forms.PrintPreviewDialog> controllano, vedere [Cenni preliminari sul controllo PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md) per una panoramica.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Proprietà chiave del controllo è <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, che imposta il documento da visualizzare in anteprima. Il documento deve essere un <xref:System.Drawing.Printing.PrintDocument> oggetto. Per una panoramica della creazione di documenti per la stampa, vedere [Cenni preliminari sul componente PrintDocument](printdocument-component-overview-windows-forms.md) e [supporto per la stampa di Windows Form](../advanced/windows-forms-print-support.md). Il <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> e <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> proprietà determinano il numero di pagine visualizzate orizzontalmente e verticalmente sul controllo. Anti-aliasing può rendere il testo vengono visualizzati più uniforme, ma può anche rendere la visualizzazione. per usarlo, impostare il <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> proprietà `true`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.PrintPreviewControl>
- [Cenni preliminari sul controllo PrintPreviewDialog](printpreviewdialog-control-overview-windows-forms.md)
- [Controllo PrintPreviewControl](printpreviewcontrol-control-windows-forms.md)
- [Controlli e componenti della finestra di dialogo](dialog-box-controls-and-components-windows-forms.md)
