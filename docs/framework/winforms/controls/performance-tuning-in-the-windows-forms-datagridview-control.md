---
title: Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], performance tuning
- performance [Windows Forms], DataGridView control
- performance tuning [Windows Forms], data grids
ms.assetid: 6ccbff28-a0ff-41e4-b601-61b31b61851d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da0171bf4fa056de2dd06c2f7e431ea55a8dab1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="performance-tuning-in-the-windows-forms-datagridview-control"></a>Ottimizzazione delle prestazioni nel controllo DataGridView Windows Form
Quando si lavora con grandi quantità di dati, il `DataGridView` controllo può utilizzare una grande quantità di memoria in overhead, se non si utilizza con attenzione. Nei client con memoria limitata, è possibile evitare alcuni questo overhead, evitando di funzionalità che hanno un costo elevato della memoria. È inoltre possibile gestire alcune o tutte le operazioni di manutenzione dati e il recupero di attività manualmente utilizzando la modalità virtuale per personalizzare l'utilizzo della memoria per il proprio scenario.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare il `DataGridView` controllo in modo da evitare possibili problemi legati all'utilizzo e le prestazioni della memoria necessaria quando si lavora con grandi quantità di dati.  
  
 [Modo virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 Viene descritto come utilizzare la modalità virtuale per integrare o sostituire il meccanismo di associazione dati standard.  
  
 [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)  
 Viene descritto come implementare i gestori per diversi eventi in modalità virtuale. Viene inoltre illustrato come implementare il rollback a livello di riga e il commit di modifiche dell'utente.  
  
 [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 Viene descritto come caricare dati su richiesta, è utile quando si dispone di più dati per visualizzare la memoria disponibile client possa memorizzare.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.DataGridView>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
