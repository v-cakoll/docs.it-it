---
title: Personalizzare l'aspetto delle righe nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 099b2104e7a4887aa846c4d65273db2dd4f60559
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744036"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a>Procedura: personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Form
È possibile controllare l'aspetto delle righe <xref:System.Windows.Forms.DataGridView> mediante la gestione di uno degli eventi o entrambi gli eventi <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>. Questi eventi sono stati progettati in modo che l'utente possa disegnare solo ciò che vuole e lasciare che il controllo <xref:System.Windows.Forms.DataGridView> disegni il resto. Ad esempio, se si vuole disegnare uno sfondo personalizzato, è possibile gestire l'evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> e lasciare che le singole celle disegnino il contenuto in primo piano. In alternativa è possibile lasciare che le celle si disegnino da sole e aggiungere il contenuto in primo piano in un gestore per l'evento <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>. È anche possibile disabilitare il disegno delle celle e disegnare tutto personalmente in un gestore dell'evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.  
  
 Nell'esempio di codice seguente i gestori vengono implementati per entrambi gli eventi in modo da fornire uno sfondo con sfumature selezionabili e un contenuto in primo piano personalizzato che si estende su più colonne.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)
- [Architettura del controllo DataGridView](datagridview-control-architecture-windows-forms.md)
