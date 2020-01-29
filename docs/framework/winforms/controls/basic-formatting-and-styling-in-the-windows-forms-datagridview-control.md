---
title: Formattazione e stile di base nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732006"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a>Formattazione e stile di base nel controllo DataGridView Windows Form
Il controllo `DataGridView` semplifica la definizione dell'aspetto di base delle celle e la formattazione di visualizzazione dei valori delle celle. È possibile definire gli stili di aspetto e formattazione per le singole celle, per le celle in colonne e righe specifiche o per tutte le celle nel controllo impostando le proprietà degli oggetti `DataGridViewCellStyle` a cui si accede tramite varie proprietà del controllo `DataGridView`. Inoltre, è possibile modificare questi stili in modo dinamico in base a fattori quali il valore della cella gestendo l'evento `CellFormatting`.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Form](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 Viene descritto come impostare `DataGridView` proprietà che definiscono l'aspetto del bordo del controllo e le linee di limite tra le celle.  
  
 [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)  
 Viene descritta la classe `DataGridViewCellStyle` e il modo in cui le proprietà di tale tipo interagiscono per definire la modalità di visualizzazione delle celle nel controllo.  
  
 [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Form](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare `DataGridViewCellStyle` proprietà per definire l'aspetto predefinito delle celle in righe e colonne specifiche e nell'intero controllo.  
  
 [Procedura: Formattare i dati nel controllo DataGridView di Windows Form](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 Viene descritto come formattare i valori di visualizzazione delle celle utilizzando `DataGridViewCellStyle` proprietà.  
  
 [Procedura: Impostare gli stili di carattere e colore nel controllo DataGridView di Windows Form](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare la proprietà `DefaultCellStyle` per impostare le caratteristiche di visualizzazione di base per tutte le celle nel controllo.  
  
 [Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 Viene descritto come creare un effetto di tipo Ledger nel controllo utilizzando righe alternate visualizzate in modo diverso.  
  
 [Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Form](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 Viene descritto come utilizzare la proprietà `RowTemplate` per impostare le proprietà delle righe che verranno utilizzate per tutte le righe nel controllo.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 Fornisce la documentazione di riferimento per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Personalizzazione del controllo DataGridView di Windows Form](customizing-the-windows-forms-datagridview-control.md)  
 Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.  
  
 [Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Fornisce argomenti che descrivono le proprietà di celle, righe e colonne comunemente utilizzate.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
