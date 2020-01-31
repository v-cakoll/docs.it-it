---
title: Specificare la modalità di modifica per il controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743760"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Procedura: specificare la modalità di modifica per il controllo DataGridView di Windows Form
Per impostazione predefinita, gli utenti possono modificare il contenuto della cella della casella di testo <xref:System.Windows.Forms.DataGridView> corrente digitando o premendo F2. In questo modo, la cella viene attivata in modalità di modifica se vengono soddisfatte tutte le condizioni seguenti:  
  
- L'origine dati sottostante supporta la modifica.  
  
- Il controllo <xref:System.Windows.Forms.DataGridView> è abilitato.  
  
- Il valore della proprietà <xref:System.Windows.Forms.DataGridView.EditMode%2A> non è <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
- Le proprietà `ReadOnly` della cella, della riga, della colonna e del controllo sono tutte impostate su `false`.  
  
 In modalità di modifica, l'utente può modificare il valore della cella e premere INVIO per eseguire il commit della modifica o dell'ESC per ripristinare il valore originale della cella.  
  
 È possibile configurare un controllo <xref:System.Windows.Forms.DataGridView> in modo che una cella entri in modalità di modifica non appena diventa la cella corrente. In questo caso, il comportamento dei tasti ENTER e ESC è invariato, ma la cella rimane in modalità di modifica dopo il commit o il ripristino del valore. È anche possibile configurare il controllo in modo che le celle entrino in modalità di modifica solo quando gli utenti digitano la cella o solo quando gli utenti preme F2. Infine, è possibile impedire che le celle entrino in modalità di modifica tranne quando si chiama il metodo <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>Per modificare la modalità di modifica di un controllo DataGridView  
  
- Impostare la proprietà <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> sull'enumerazione <xref:System.Windows.Forms.DataGridViewEditMode> appropriata.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1`.  
  
- Riferimenti agli assembly <xref:System> e <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
