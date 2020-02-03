---
title: Ridimensionare colonne e righe nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742408"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a>Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form
Il controllo `DataGridView` offre numerose opzioni per la personalizzazione del comportamento di ridimensionamento delle colonne e delle righe. In genere, `DataGridView` le celle non vengono ridimensionate in base al relativo contenuto. Ma ritagliano qualsiasi valore di visualizzazione superiore alla cella. Se il contenuto può essere visualizzato come stringa, la cella la Visualizza in una descrizione comando.  
  
 Per impostazione predefinita, gli utenti possono trascinare i divisori di riga, colonna e intestazione con il mouse per visualizzare altre informazioni. Gli utenti possono anche fare doppio clic su un divisore per ridimensionare automaticamente la riga, la colonna o la banda di intestazione associata in base al relativo contenuto.  
  
 Il controllo `DataGridView` fornisce proprietà, metodi ed eventi che consentono di personalizzare o disabilitare tutti questi comportamenti indirizzati dall'utente. Inoltre, è possibile ridimensionare a livello di codice le righe, le colonne e le intestazioni per adattarne il contenuto, oppure è possibile configurarle in modo che vengano ridimensionate automaticamente ogni volta che il contenuto viene modificato. È inoltre possibile configurare le colonne per dividere automaticamente la larghezza disponibile del controllo in proporzioni specificate.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)  
 Descrive le opzioni per il dimensionamento di righe, colonne e intestazioni. Vengono inoltre fornite informazioni dettagliate sulle proprietà e sui metodi correlati al dimensionamento e vengono descritti gli scenari di utilizzo comuni.  
  
 [Modalità di riempimento di colonna nel controllo DataGridView di Windows Form](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 Viene descritta in dettaglio la modalità di riempimento delle colonne e viene fornito il codice dimostrativo che è possibile utilizzare per sperimentare la modalità di riempimento delle colonne e altre modalità.  
  
 [Procedura: Impostare le modalità dimensionamento del controllo DataGridView di Windows Form](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 Viene descritto come configurare le modalità di ridimensionamento per scopi comuni.  
  
 [Procedura: Ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Form](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 Fornisce il codice dimostrativo che è possibile usare per sperimentare il ridimensionamento a livello di codice.  
  
 [Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto del controllo DataGridView di Windows Form](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 Fornisce il codice dimostrativo che è possibile usare per sperimentare le modalità di ridimensionamento automatico.  
  
## <a name="reference"></a>Riferimento  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
