---
title: 'Procedura: impostare stili di righe alterne per il controllo DataGridView di Windows Form utilizzando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8d78509a7d088511096d2e02e8e6603ba5fe5c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a>Procedura: impostare stili di righe alterne per il controllo DataGridView di Windows Form utilizzando la finestra di progettazione
Dati tabulari sono spesso presentati in un formato in cui le righe alterne hanno colori di sfondo diversi. Questo formato permette agli utenti di individuare più facilmente le celle di ogni riga, soprattutto nelle tabelle estese in larghezza con molte colonne.  
  
 Con il controllo <xref:System.Windows.Forms.DataGridView>, è possibile specificare informazioni di stile complete per le righe alterne. È possibile utilizzare le caratteristiche di stile come colore di primo piano e tipo di carattere, oltre al colore di sfondo, per differenziare le righe alterne. Per ulteriori informazioni, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGridView> controllo. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="define-styles-for-alternating-rows"></a>Definire gli stili per le righe alterne  
  
1.  Selezionare il <xref:System.Windows.Forms.DataGridView> controllo nella finestra di progettazione.  
  
2.  Nel **proprietà** finestra, fare clic sul pulsante con i puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> proprietà.  
  
3.  Nel **Generatore CellStyle** la finestra di dialogo, definire lo stile impostando le proprietà, utilizzare il **anteprima** riquadro per confermare le scelte. Gli stili specificati vengono utilizzati per tutte le altre righe visualizzata nel controllo, a partire dal secondo.  
  
4.  Per definire gli stili per le righe rimanenti, ripetere i passaggi 2 e 3 utilizzando il <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> proprietà.  
  
    > [!NOTE]
    >  Le celle vengono visualizzate utilizzando gli stili ereditati da più proprietà. Per ulteriori informazioni sull'ereditarietà degli stili, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Formattazione e stile di base nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Uso della finestra di progettazione con il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)  
 [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
