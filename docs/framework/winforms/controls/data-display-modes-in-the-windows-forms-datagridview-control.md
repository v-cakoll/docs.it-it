---
title: "Modalità di visualizzazione dati nel controllo DataGridView di Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92b66d27683fad4adf0ed2179a5bb29ef6220e3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Modalità di visualizzazione dati nel controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo può visualizzare i dati in tre modalità distinte: associata, non associati e virtuale. Scegliere la modalità più adatta in base alle esigenze.  
  
## <a name="unbound"></a>Non associato  
 La modalità non associata è adatta per la visualizzazione relativamente piccole quantità di dati gestiti a livello di codice. Non si associa il <xref:System.Windows.Forms.DataGridView> controllo direttamente a un'origine dati come modalità di associazione. In alternativa, è necessario popolare il controllo manualmente, in genere tramite il <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> metodo.  
  
 Modalità non associata può essere particolarmente utile per i dati statici di sola lettura, o quando si desidera fornire il proprio codice che interagisce con un archivio dati esterno. Quando si desidera che gli utenti di interagire con un'origine dati esterna, tuttavia, in genere utilizzare modalità di associazione.  
  
 Per un esempio che usa una proprietà di sola lettura non associati <xref:System.Windows.Forms.DataGridView>, vedere [procedura: creare un controllo DataGridView di Windows Form non associato](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Associato  
 Modalità di associazione è appropriata per la gestione dei dati mediante l'interazione automatica con l'archivio dati. È possibile collegare il <xref:System.Windows.Forms.DataGridView> controllo direttamente all'origine dati impostando la <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà. Quando il controllo è associato a dati, le righe di dati sono push e pull senza la necessità di gestione esplicita da parte dell'utente. Quando il <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> proprietà `true`, ogni colonna nell'origine dati causerà una colonna corrispondente da creare nel controllo. Se si preferisce creare le proprie colonne, è possibile impostare questa proprietà `false` e utilizzare il <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> proprietà da associare ogni colonna al momento della configurazione. Ciò è utile quando si desidera utilizzare un tipo di colonna diversi dai tipi che vengono generati per impostazione predefinita. Per ulteriori informazioni, vedere [tipi di colonna nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).  
  
 Per un esempio che usa un limite <xref:System.Windows.Forms.DataGridView> di controllo, vedere [procedura dettagliata: convalida di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 È inoltre possibile aggiungere colonne non associate a un <xref:System.Windows.Forms.DataGridView> controllo in modalità di associazione. Ciò è utile quando si desidera visualizzare una colonna di pulsanti o collegamenti che consentono agli utenti di eseguire operazioni su righe specifiche. È inoltre utile visualizzare le colonne con i valori calcolati dalle colonne associate. È possibile popolare i valori delle celle per le colonne calcolate in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento. Se si utilizza un <xref:System.Data.DataSet> o <xref:System.Data.DataTable> come origine dati, tuttavia, è consigliabile utilizzare il <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> proprietà per creare una colonna calcolata. In questo caso, il <xref:System.Windows.Forms.DataGridView> controllo verrà considerato una colonna calcolata esattamente come qualsiasi altra colonna nell'origine dati.  
  
 Ordinamento in base a colonne non associate in modalità di associazione non è supportata. Se si crea una colonna non associata in modalità di associazione che contiene i valori modificabili dall'utente, è necessario implementare la modalità virtuale per gestire questi valori quando il controllo viene ordinato in base a una colonna associata.  
  
## <a name="virtual"></a>Virtuale  
 La modalità virtuale, è possibile implementare operazioni di gestione dati. Ciò è necessario per mantenere i valori delle colonne in modalità di associazione quando il controllo viene ordinato in base a colonne associate. L'utilizzo principale di modalità virtuale, è tuttavia, per ottimizzare le prestazioni durante l'interazione con grandi quantità di dati.  
  
 Si collega il <xref:System.Windows.Forms.DataGridView> controllo a una cache gestiti e i controlli di codice quando le righe di dati vengono effettuato il push e pull. Per ridurre il footprint di memoria, la cache deve essere simile al numero di righe attualmente visualizzate. Quando l'utente scorre le nuove righe nella visualizzazione, il codice richiede nuovi dati dalla cache e, facoltativamente, Elimina i dati obsoleti dalla memoria.  
  
 Quando si implementa la modalità virtuale, è necessario tenere traccia di una nuova riga è necessaria nel modello di dati e quando eseguire il rollback, l'aggiunta della nuova riga. L'implementazione esatta di questa funzionalità varia in base l'implementazione del modello di dati e la semantica delle transazioni del modello di dati; indica se l'ambito di commit è a livello di cella o riga.  
  
 Per ulteriori informazioni sulla modalità virtuale, vedere [modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md). Per un esempio che illustra come utilizzare eventi in modalità virtuale, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>  
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Tipi di colonne nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Procedura dettagliata: Creazione di un controllo DataGridView di Windows Form non associato](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 [Procedura: Associare dati al controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 [Modo virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)
