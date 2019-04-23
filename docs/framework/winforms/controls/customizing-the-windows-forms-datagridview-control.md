---
title: Personalizzazione del controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: ab8d1f07c608aca4f14f5e73860f8c3e263a4610
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091382"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Personalizzazione del controllo DataGridView Windows Form
Il `DataGridView` controllo fornisce diverse proprietà che è possibile usare per regolare l'aspetto e il comportamento di base (aspetto) delle relative celle, righe e colonne. Se si hanno esigenze speciali che vanno oltre le funzionalità del <xref:System.Windows.Forms.DataGridViewCellStyle> classe, tuttavia, è possibile anche implementare il disegno personalizzato per il controllo o estendere le funzionalità creando le celle personalizzate, colonne e righe.  
  
 Per disegnare celle e righe personalizzate, è possibile gestire vari `DataGridView` gli eventi di disegno. Per modificare le funzionalità esistenti o forniscono nuove funzionalità, è possibile creare i propri tipi derivati da esistente `DataGridViewCell`, `DataGridViewColumn`, e `DataGridViewRow` tipi. È anche possibile fornire nuove funzionalità di modifica tramite la creazione di tipi derivati che consentono di visualizzare un controllo di propria scelta quando una cella è in modalità di modifica.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form](customize-the-appearance-of-cells-in-the-datagrid.md)  
 Viene descritto come gestire il <xref:System.Windows.Forms.DataGridView.CellPainting> eventi per disegnare celle manualmente.  
  
 [Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView Windows Form](customize-the-appearance-of-rows-in-the-datagrid.md)  
 Viene descritto come gestire le <xref:System.Windows.Forms.DataGridView.RowPrePaint> e <xref:System.Windows.Forms.DataGridView.RowPostPaint> eventi per disegnare le righe con uno sfondo sfumato personalizzato e un contenuto che si estende su più colonne.  
  
 [Procedura: Personalizzare celle e colonne nel controllo DataGridView Windows Form estendendone il comportamento e aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Viene descritto come creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per evidenziare le celle quando il puntatore del mouse è posizionato su di essi.  
  
 [Procedura: Disabilitare i pulsanti in una colonna nel controllo DataGridView Windows Form](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Viene descritto come creare tipi personalizzati derivati da <xref:System.Windows.Forms.DataGridViewButtonCell> e <xref:System.Windows.Forms.DataGridViewButtonColumn> per visualizzare i pulsanti disabilitati in una colonna.  
  
 [Procedura: Controlli host nelle celle del controllo DataGridView Windows Form](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Viene descritto come implementare il `IDataGridViewEditingControl` l'interfaccia e creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per visualizzare un <xref:System.Windows.Forms.DateTimePicker> controllare quando una cella è in modalità di modifica.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridViewCell> classe.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridViewRow> classe.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridViewColumn> classe.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
