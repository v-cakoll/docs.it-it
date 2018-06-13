---
title: Personalizzazione del controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 92bbace4d0869aca67025f1e4ac8c451fe073219
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529844"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Personalizzazione del controllo DataGridView Windows Form
Il `DataGridView` controllo fornisce diverse proprietà che è possibile utilizzare per modificare l'aspetto e il comportamento di base (aspetto) delle relative celle, righe e colonne. Se si dispone di particolari esigenze che vanno oltre le capacità del <xref:System.Windows.Forms.DataGridViewCellStyle> classe, tuttavia, è possibile inoltre implementare il disegno personalizzato per il controllo o estenderne le funzionalità tramite la creazione di celle, colonne e righe.  
  
 Per disegnare celle e righe personalizzate, è possibile gestire vari `DataGridView` gli eventi di disegno. Per modificare le funzionalità esistenti o fornire nuove funzionalità, è possibile creare i propri tipi derivati da esistenti `DataGridViewCell`, `DataGridViewColumn`, e `DataGridViewRow` tipi. È anche possibile fornire nuove funzionalità di modifica mediante la creazione di tipi derivati che visualizzano un controllo di propria scelta quando una cella si trova in modalità di modifica.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 Viene descritto come gestire il <xref:System.Windows.Forms.DataGridView.CellPainting> evento per disegnare le celle manualmente.  
  
 [Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 Viene descritto come gestire il <xref:System.Windows.Forms.DataGridView.RowPrePaint> e <xref:System.Windows.Forms.DataGridView.RowPostPaint> gli eventi per disegnare righe con uno sfondo sfumato personalizzato e un contenuto che si estende su più colonne.  
  
 [Procedura: Personalizzare celle e colonne nel controllo DataGridView di Windows Form estendendone il comportamento e l'aspetto](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Viene descritto come creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per evidenziare le celle quando il puntatore del mouse si sofferma su di essi.  
  
 [Procedura: Disabilitare i pulsanti in una colonna del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Viene descritto come creare tipi personalizzati derivati da <xref:System.Windows.Forms.DataGridViewButtonCell> e <xref:System.Windows.Forms.DataGridViewButtonColumn> per visualizzare i pulsanti disabilitati in una colonna.  
  
 [Procedura: Inserire controlli in celle del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Viene descritto come implementare il `IDataGridViewEditingControl` l'interfaccia e creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per visualizzare un <xref:System.Windows.Forms.DateTimePicker> controllare quando una cella si trova in modalità di modifica.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewCell> classe.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewRow> classe.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewColumn> classe.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Formattazione e stile di base nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Tipi di colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
