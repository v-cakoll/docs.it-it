---
title: Personalizzare il controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744030"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Personalizzazione del controllo DataGridView Windows Form
Il controllo `DataGridView` fornisce diverse proprietà che è possibile utilizzare per modificare l'aspetto e il comportamento di base (aspetto) delle relative celle, righe e colonne. Se si hanno esigenze particolari che vanno oltre le funzionalità della classe <xref:System.Windows.Forms.DataGridViewCellStyle>, tuttavia, è anche possibile implementare il disegno del proprietario per il controllo o estenderne le funzionalità creando celle, colonne e righe personalizzate.  
  
 Per disegnare le celle e le righe manualmente, è possibile gestire vari eventi di disegno `DataGridView`. Per modificare la funzionalità esistente o fornire nuove funzionalità, è possibile creare tipi personalizzati derivati dai tipi di `DataGridViewCell`, `DataGridViewColumn`e `DataGridViewRow` esistenti. È anche possibile fornire nuove funzionalità di modifica creando tipi derivati che visualizzano un controllo a scelta quando una cella è in modalità di modifica.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form](customize-the-appearance-of-cells-in-the-datagrid.md)  
 Viene descritto come gestire l'evento <xref:System.Windows.Forms.DataGridView.CellPainting> per disegnare manualmente le celle.  
  
 [Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Form](customize-the-appearance-of-rows-in-the-datagrid.md)  
 Viene descritto come gestire gli eventi <xref:System.Windows.Forms.DataGridView.RowPrePaint> e <xref:System.Windows.Forms.DataGridView.RowPostPaint> per disegnare le righe con uno sfondo sfumato e un contenuto personalizzati che si estende su più colonne.  
  
 [Procedura: Personalizzare celle e colonne nel controllo DataGridView di Windows Form estendendone il comportamento e l'aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Viene descritto come creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per evidenziare le celle quando il puntatore del mouse viene posizionato su di essi.  
  
 [Procedura: Disabilitare i pulsanti in una colonna del controllo DataGridView di Windows Form](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Viene descritto come creare tipi personalizzati derivati da <xref:System.Windows.Forms.DataGridViewButtonCell> e <xref:System.Windows.Forms.DataGridViewButtonColumn> per visualizzare i pulsanti disabilitati in una colonna di un pulsante.  
  
 [Procedura: Inserire controlli in celle del controllo DataGridView di Windows Form](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Viene descritto come implementare l'interfaccia `IDataGridViewEditingControl` e creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per visualizzare un controllo <xref:System.Windows.Forms.DateTimePicker> quando una cella è in modalità di modifica.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewCell>.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewRow>.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Fornisce la documentazione di riferimento per l'interfaccia <xref:System.Windows.Forms.IDataGridViewEditingControl>.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Formattazione e stile di base nel controllo DataGridView di Windows Form](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
