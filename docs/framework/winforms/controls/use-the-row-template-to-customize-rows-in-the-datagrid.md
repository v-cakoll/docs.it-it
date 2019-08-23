---
title: 'Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966500"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Forms
Il <xref:System.Windows.Forms.DataGridView> controllo Usa il modello di riga come base per tutte le righe aggiunte al controllo tramite Data Binding o quando si chiama il <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> metodo senza specificare una riga esistente da usare.  
  
 Il modello di riga offre un maggiore controllo sull'aspetto e sul comportamento delle righe rispetto <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> a quanto fornito dalla proprietà. Con il modello di riga, è possibile impostare <xref:System.Windows.Forms.DataGridViewRow> qualsiasi proprietà, <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>incluso.  
  
 In alcune situazioni è necessario utilizzare il modello di riga per ottenere un effetto specifico. Ad esempio, le informazioni sull'altezza della riga non possono <xref:System.Windows.Forms.DataGridViewCellStyle>essere archiviate in un oggetto, pertanto è necessario utilizzare un modello di riga per modificare l'altezza predefinita utilizzata da tutte le righe. Il modello di riga è utile anche quando si creano classi derivate <xref:System.Windows.Forms.DataGridViewRow> da e si desidera utilizzare il tipo personalizzato quando vengono aggiunte nuove righe al controllo.  
  
> [!NOTE]
> Il modello di riga viene utilizzato solo quando vengono aggiunte righe. Non è possibile modificare le righe esistenti modificando il modello di riga.  
  
### <a name="to-use-the-row-template"></a>Per utilizzare il modello di riga  
  
- Impostare le proprietà nell'oggetto recuperato dalla <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> proprietà.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
