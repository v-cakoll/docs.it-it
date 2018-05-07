---
title: 'Procedura: utilizzare il modello di riga personalizzare le righe nel controllo DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 2bde9b3f6934833804866e29c18f3636c65ba069
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Procedura: utilizzare il modello di riga personalizzare le righe nel controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo utilizza il modello di riga come base per tutte le righe da aggiungere al controllo tramite l'associazione dati o quando si chiama il <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> metodo senza specificare una riga esistente da utilizzare.  
  
 Il modello di riga garantisce un maggiore controllo sull'aspetto e comportamento di righe rispetto al <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> fornisce proprietà. Con il modello di riga, è possibile impostare qualsiasi <xref:System.Windows.Forms.DataGridViewRow> proprietà, tra cui <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.  
  
 Esistono alcune situazioni in cui è necessario utilizzare il modello di riga per ottenere un risultato specifico. Ad esempio, informazioni relative all'altezza di riga non possono essere archiviate un <xref:System.Windows.Forms.DataGridViewCellStyle>, pertanto è necessario utilizzare un modello di riga per modificare l'altezza predefinita per tutte le righe. Il modello di riga è utile anche quando si creano le proprie classi derivate da <xref:System.Windows.Forms.DataGridViewRow> e si desidera utilizzare un tipo personalizzato nuove righe vengono aggiunte al controllo.  
  
> [!NOTE]
>  Il modello di riga viene utilizzato solo quando vengono aggiunte le righe. È possibile modificare le righe esistenti modificando il modello di riga.  
  
### <a name="to-use-the-row-template"></a>Utilizzare il modello di riga  
  
-   Impostare le proprietà per l'oggetto recuperato dal <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> proprietà.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
-   Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>  
 [Formattazione e stile di base nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
