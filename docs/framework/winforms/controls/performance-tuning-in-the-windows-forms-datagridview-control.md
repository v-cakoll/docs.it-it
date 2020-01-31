---
title: Ottimizzazione delle prestazioni nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
ms.openlocfilehash: 77ad86c4cd606bcf074473c97371ec27bcc5605b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744269"
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form
Quando si lavora con grandi quantità di dati, il controllo `DataGridView` può utilizzare una grande quantità di memoria in sovraccarico, a meno che non venga utilizzato con cautela. Nei client con memoria limitata è possibile evitare questo sovraccarico evitando funzionalità con un costo elevato di memoria. È anche possibile gestire alcune o tutte le attività di manutenzione e recupero dei dati utilizzando la modalità virtuale per personalizzare l'utilizzo della memoria per lo scenario.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare il controllo `DataGridView` in modo da evitare l'utilizzo di memoria superfluo e le penalizzazioni delle prestazioni quando si utilizzano grandi quantità di dati.  
  
 [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare la modalità virtuale per integrare o sostituire il meccanismo standard di associazione dati.  
  
 [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Form](implementing-virtual-mode-wf-datagridview-control.md)  
 Viene descritto come implementare i gestori per diversi eventi in modalità virtuale. Viene inoltre illustrato come implementare il rollback a livello di riga e il commit per le modifiche dell'utente.  
  
 [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Viene descritto come caricare i dati su richiesta, che risulta utile quando si dispone di più dati da visualizzare rispetto alla memoria del client disponibile che è possibile archiviare.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
## <a name="see-also"></a>Vedere anche

- [Controllo DataGridView](datagridview-control-windows-forms.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
