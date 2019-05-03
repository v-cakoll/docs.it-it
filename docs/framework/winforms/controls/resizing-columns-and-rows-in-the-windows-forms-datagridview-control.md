---
title: Ridimensionamento di colonne e righe nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: e1fa2d57cfb2cd374d691fe03a0e0bdbd3ad7141
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903188"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a>Ridimensionamento di colonne e righe nel controllo DataGridView di Windows Form
Il `DataGridView` controllo offre numerose opzioni per personalizzare il comportamento di ridimensionamento di colonne e righe. In genere, `DataGridView` celle non vengono ridimensionano in base al rispettivo contenuto. Al contrario, vengono tagliati qualsiasi valore di visualizzazione che è maggiore della cella. Se il contenuto può essere visualizzato sotto forma di stringa, viene inserito in una descrizione comando.  
  
 Per impostazione predefinita, gli utenti possono trascinare righe, colonne e i separatori di intestazione con il mouse per visualizzare altre informazioni. Gli utenti possono anche fare doppio clic su un divisore per ridimensionare automaticamente la banda riga, colonna o nell'intestazione associata in base al contenuto.  
  
 Il `DataGridView` controllo fornisce proprietà, metodi ed eventi che consentono la personalizzazione o la disattivazione di tutti i comportamenti gestito dall'utente. Inoltre, è possibile ridimensionare a livello di programmazione le righe, colonne e intestazioni in base al contenuto oppure è possibile configurare in modo da ridimensionarsi automaticamente ogni volta che cambia il relativo contenuto. È anche possibile configurare colonne per suddividere automaticamente la larghezza disponibile del controllo in base alle proporzioni specificato.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)  
 Vengono descritte le opzioni per dimensionamento di righe, colonne e intestazioni. Inoltre fornisce informazioni dettagliate sui metodi e proprietà correlate al dimensionamento e vengono descritti scenari comuni di utilizzo.  
  
 [Modalità di riempimento di colonna nel controllo DataGridView di Windows Form](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 Descrive in dettaglio la modalità di riempimento di colonna e offre codice di esempio che è possibile usare per sperimentare con modalità riempimento delle colonne e gli altri modi.  
  
 [Procedura: Impostare le modalità dimensionamento del controllo DataGridView Windows Form](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 Viene descritto come configurare le modalità di ridimensionamento per attività comuni.  
  
 [Procedura: Ridimensiona a livello di codice le celle per adattarsi al contenuto nel controllo DataGridView Windows Form](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 Fornisce il codice di esempio che è possibile usare per sperimentare con ridimensionamento a livello di codice.  
  
 [Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto nel controllo DataGridView Windows Form](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 Fornisce il codice di esempio che è possibile usare per sperimentare le modalità di ridimensionamento automatico.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
