---
title: 'Procedura: Impostare stili di righe alterne per il controllo di DataGridView Windows Form usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 723dca7b87190b1a2a63427ecc894987f556ab54
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616238"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: Impostare stili di righe alterne per il controllo di DataGridView Windows Form usando la finestra di progettazione
Dati tabulari spesso sono presentati in un formato simile a di contabilità in cui le righe alterne hanno colori di sfondo diversi. Questo formato permette agli utenti di individuare più facilmente le celle di ogni riga, soprattutto nelle tabelle estese in larghezza con molte colonne.  
  
 Con il controllo <xref:System.Windows.Forms.DataGridView>, è possibile specificare informazioni di stile complete per le righe alterne. È possibile utilizzare le caratteristiche di stile, come colore di primo piano e del tipo di carattere, oltre al colore di sfondo, per differenziare le righe alterne. Per altre informazioni, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [come: Aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="define-styles-for-alternating-rows"></a>Definire gli stili per le righe alterne  
  
1.  Selezionare il <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione.  
  
2.  Nel **delle proprietà** finestra, fare clic sul pulsante con puntini di sospensione (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> proprietà.  
  
3.  Nel **Generatore CellStyle** finestra di dialogo, definire lo stile, impostando le proprietà e utilizzare il **anteprima** riquadro per confermare le scelte effettuate. Gli stili specificati vengono usati per tutte le altre righe visualizzata nel controllo, inizia con il secondo.  
  
4.  Per definire gli stili per le righe rimanenti, ripetere i passaggi 2 e 3 mediante il <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> proprietà.  
  
    > [!NOTE]
    >  Le celle vengono visualizzate utilizzando gli stili ereditati da più proprietà. Per altre informazioni sull'ereditarietà degli stili, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Formattazione e stile di base nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Uso della finestra di progettazione con il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un progetto Applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)
- [Procedura: Aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
