---
title: 'Procedura: visualizzare immagini in celle del controllo DataGridView di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56c8558f34c895567c3eebfbb5a89612c4b56224
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Procedura: visualizzare immagini in celle del controllo DataGridView di Windows Form
Un'immagine o un grafico è uno dei valori che è possibile visualizzare in una riga di dati. Spesso, questi elementi grafici assumono la forma di fotografia di un dipendente o un logo aziendale.  
  
 L'inserimento delle immagini è semplice quando si visualizzano dati all'interno di <xref:System.Windows.Forms.DataGridView> controllo. Il <xref:System.Windows.Forms.DataGridView> qualsiasi formato di immagine supportato da e gestisce in modo nativo la <xref:System.Drawing.Image> classe, nonché OLE immagine formato utilizzato da alcuni database.  
  
 Se il <xref:System.Windows.Forms.DataGridView> origine dati del controllo dispone di una colonna di immagini, verranno visualizzati automaticamente dal <xref:System.Windows.Forms.DataGridView> controllo.  
  
 Esempio di codice riportato di seguito viene illustrato come estrarre un'icona da una risorsa incorporata e convertirlo in una bitmap da visualizzare in ogni cella di una colonna di tipo image. Ad esempio un altro che sostituisce i valori delle celle testuali con immagini corrispondenti, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Una risorsa icona incorporata denominata `tree.ico`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> e <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Procedura: Formattare dati personalizzati in un controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
