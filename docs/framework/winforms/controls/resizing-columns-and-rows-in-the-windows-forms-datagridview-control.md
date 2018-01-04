---
title: Ridimensionamento di colonne e righe nel controllo DataGridView di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1c11ca487003e57a499b3ff46178350e6aad404
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a>Ridimensionamento di colonne e righe nel controllo DataGridView di Windows Form
Il `DataGridView` controllo fornisce numerose opzioni per personalizzare il comportamento di ridimensionamento di colonne e righe. In genere, `DataGridView` celle non vengono ridimensionano in base al relativo contenuto. Al contrario, vengono tagliati qualsiasi valore di visualizzazione che è maggiore della cella. Se è possibile visualizzare il contenuto come stringa, viene inserito in una descrizione comando.  
  
 Per impostazione predefinita, gli utenti possono trascinare righe, colonne e i separatori di intestazione con il mouse per visualizzare ulteriori informazioni. Gli utenti possono anche fare doppio clic su un divisore per ridimensionare automaticamente la banda di riga, colonna o intestazione associata in base al relativo contenuto.  
  
 Il `DataGridView` controllo fornisce proprietà, metodi ed eventi che consentono la personalizzazione o la disattivazione di tutti i comportamenti gestiti dall'utente. Inoltre, è possibile ridimensionare a livello di codice le righe, colonne e intestazioni in base al contenuto, oppure è possibile configurare in modo da ridimensionati automaticamente ogni volta che cambia il relativo contenuto. È inoltre possibile configurare le colonne per dividere automaticamente la larghezza disponibile del controllo in base alle proporzioni specificato.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 Vengono descritte le opzioni per intestazioni, colonne e righe di ridimensionamento. Inoltre fornisce informazioni dettagliate sui metodi e proprietà correlate al ridimensionamento e vengono descritti scenari comuni di utilizzo.  
  
 [Modalità di riempimento di colonna nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 Descrive in dettaglio la modalità di riempimento di colonna e viene fornito codice dimostrativo che è possibile utilizzare per sperimentare modalità riempimento delle colonne e gli altri modi.  
  
 [Procedura: Impostare le modalità dimensionamento del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 Viene descritto come configurare le modalità di ridimensionamento per attività comuni.  
  
 [Procedura: Ridimensionare a livello di codice le celle in base al contenuto nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 Fornisce il codice di esempio che è possibile utilizzare per sperimentare il ridimensionamento a livello di codice.  
  
 [Procedura: Ridimensionare automaticamente le celle alla modifica del contenuto del controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 Fornisce il codice di esempio che consente di sperimentare le modalità di ridimensionamento automatico.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
