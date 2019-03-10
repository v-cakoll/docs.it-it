---
title: Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: d425488adb8569a48333de4f8c0312143029fbe0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703166"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form
Quando si lavora con grandi quantità di dati, il `DataGridView` controllo può utilizzare una grande quantità di memoria, in overhead, a meno che non si usarla con cautela. Nei client con memoria limitata, è possibile evitare alcuni questo overhead, evitando le funzionalità che presentano un elevato utilizzo della memoria. È anche possibile gestire alcune o tutte le operazioni di manutenzione di dati e il recupero di attività manualmente utilizzando la modalità virtuale per personalizzare l'utilizzo della memoria per il proprio scenario.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare il `DataGridView` controllo in modo da evitare sanzioni utilizzo e le prestazioni della memoria non necessarie quando si lavora con grandi quantità di dati.  
  
 [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare la modalità virtuale per integrare o sostituire il meccanismo di data binding standard.  
  
 [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView Windows Form](implementing-virtual-mode-wf-datagridview-control.md)  
 Viene descritto come implementare i gestori per vari eventi in modalità virtuale. Viene inoltre illustrato come implementare il rollback a livello di riga ed eseguire il commit per le modifiche dell'utente.  
  
 [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Viene descritto come caricare i dati su richiesta, è utile quando sono presenti più dati da visualizzare più la capacità di memoria client disponibili.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà.  
  
## <a name="see-also"></a>Vedere anche
- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
