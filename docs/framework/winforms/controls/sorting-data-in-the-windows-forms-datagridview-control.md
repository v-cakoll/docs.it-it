---
title: Ordinamento di dati nel controllo DataGridView
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 1fcd5a5f5c6d690c573c4c2c5fa7c32aa0292441
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742940"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Ordinamento dei dati nel controllo DataGridView Windows Forms

Per impostazione predefinita, gli utenti possono ordinare i dati in un controllo <xref:System.Windows.Forms.DataGridView> facendo clic sull'intestazione di una colonna casella di testo (o premendo F3 quando una cella della casella di testo è concentrata su .NET Framework 4.7.2 e versioni successive). È possibile modificare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode> di colonne specifiche per consentire agli utenti di eseguire l'ordinamento in base ad altri tipi di colonna quando è opportuno eseguire questa operazione. È anche possibile ordinare i dati a livello di codice in base a qualsiasi colonna o a più colonne.

## <a name="in-this-section"></a>Contenuto della sezione

[Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
Descrive le opzioni per l'ordinamento dei dati nel controllo.

[Procedura: Impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
Viene descritto come consentire agli utenti di eseguire l'ordinamento in base a colonne non ordinabili per impostazione predefinita.

[Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Form](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
Viene descritto come ordinare i dati a livello di codice e come personalizzare l'ordinamento utilizzando l'evento <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> o implementando l'interfaccia <xref:System.Collections.IComparer>.

## <a name="reference"></a>Riferimento

<xref:System.Windows.Forms.DataGridView>  
Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
Fornisce la documentazione di riferimento per il metodo <xref:System.Windows.Forms.DataGridView.Sort%2A>.

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>.

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
Fornisce la documentazione di riferimento per l'enumerazione <xref:System.Windows.Forms.DataGridViewColumnSortMode>.

## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
