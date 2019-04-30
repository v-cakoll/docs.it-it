---
title: Ordinamento dei dati nel controllo DataGridView di Windows Form
ms.date: 02/13/2018
helpviewer_keywords:
- data [Windows Forms], sorting in grids
- data grids [Windows Forms], sorting data
- DataGridView control [Windows Forms], sorting data
ms.assetid: c1d4f24c-d961-4181-809d-5a5caa6122e4
ms.openlocfilehash: 606ffc7bd6136b775adaaaa79cf5042cf1e2dd70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012147"
---
# <a name="sorting-data-in-the-windows-forms-datagridview-control"></a>Ordinamento dei dati nel controllo DataGridView di Windows Form

Per impostazione predefinita, gli utenti possono ordinare i dati in un <xref:System.Windows.Forms.DataGridView> controllo facendo l'intestazione di una colonna della casella di testo (o premendo F3 quando una cella di casella di testo è evidenziata in .NET Framework 4.7.2 e versioni successive). È possibile modificare il <xref:System.Windows.Forms.DataGridViewColumn.SortMode> proprietà delle colonne specifiche per consentire agli utenti di ordinare gli altri tipi di colonna quando sarà opportuno eseguire questa operazione. È anche possibile ordinare i dati a livello di codice da qualsiasi colonna o da più colonne.

## <a name="in-this-section"></a>Contenuto della sezione

[Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form](column-sort-modes-in-the-windows-forms-datagridview-control.md)  
Vengono descritte le opzioni per l'ordinamento dei dati nel controllo.

[Procedura: Impostare la modalità di ordinamento delle colonne nel controllo DataGridView Windows Form](set-the-sort-modes-for-columns-wf-datagridview-control.md)  
Viene descritto come consentire agli utenti di ordinare le colonne che non sono ordinabili per impostazione predefinita.

[Procedura: Personalizzare l'ordinamento nel controllo DataGridView Windows Form](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)  
Viene descritto come ordinare i dati a livello di programmazione e su come personalizzare l'ordinamento utilizzando il <xref:System.Windows.Forms.DataGridView.SortCompare?displayProperty=nameWithType> evento o implementando il <xref:System.Collections.IComparer> interfaccia.

## <a name="reference"></a>Riferimenti

<xref:System.Windows.Forms.DataGridView>  
Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  

<xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridView.Sort%2A> (metodo).

<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> proprietà.

<xref:System.Windows.Forms.DataGridViewColumnSortMode>  
Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridViewColumnSortMode> enumerazione.

## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
