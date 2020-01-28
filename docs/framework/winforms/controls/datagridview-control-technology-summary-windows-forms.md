---
title: Riepilogo della tecnologia del controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: 18eebd067df9768e14cc81258184551d00dd1402
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742473"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Riepilogo della tecnologia del controllo DataGridView (Windows Form)
Questo argomento riepiloga le informazioni relative al controllo `DataGridView` e alle classi che ne supportano l'uso.  
  
 La visualizzazione dei dati in formato tabulare è un'attività che è probabile eseguire di frequente. Il controllo `DataGridView` è progettato per essere una soluzione completa per la presentazione dei dati in una griglia.  
  
## <a name="keywords"></a>Parole chiave  
 DataGridView, BindingSource, tabella, cella, data binding, modalità virtuale  
  
## <a name="namespaces"></a>Spazi dei nomi  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Tecnologie correlate  
 `BindingSource`  
  
## <a name="background"></a>Informazioni di background sul  
 Le finestre di progettazione dell'interfaccia utente trovano spesso la necessità di visualizzare i dati tabulari agli utenti. Il .NET Framework offre diversi modi per visualizzare i dati in una tabella o in una griglia. Il controllo `DataGridView` rappresenta la più recente evoluzione di questa tecnologia per le applicazioni Windows Forms.  
  
 Il controllo `DataGridView` può visualizzare le righe di dati da un archivio dati. Sono supportati molti tipi di archivi dati. L'archivio dati può contenere dati semplici e non tipizzati, ad esempio una matrice unidimensionale, oppure può contenere dati tipizzati, ad esempio un <xref:System.Data.DataSet>. Per altre informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Forms](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Il controllo `DataGridView` fornisce un sistema efficiente e flessibile per visualizzare i dati in formato tabulare. È possibile utilizzare il controllo per visualizzare le visualizzazioni di sola lettura o modificabili di set di dati di piccole e grandi dimensioni.  
  
 È possibile estendere il controllo `DataGridView` in diversi modi per creare comportamenti personalizzati nelle applicazioni. Ad esempio, è possibile specificare a livello di codice i propri algoritmi di ordinamento e creare i propri tipi di celle. È possibile personalizzare facilmente l'aspetto del controllo `DataGridView` scegliendo tra diverse proprietà. Molti tipi di archivi dati possono essere usati come origine dati oppure il controllo `DataGridView` può funzionare senza un'origine dati associata.  
  
## <a name="implementing-datagridview-classes"></a>Implementazione di classi DataGridView  
 Sono disponibili diversi modi per sfruttare le funzionalità di estendibilità del controllo `DataGridView`. È possibile personalizzare molti aspetti del controllo tramite eventi e proprietà, ma alcune personalizzazioni richiedono la creazione di nuove classi derivate dalle classi di `DataGridView` esistenti.  
  
 Le classi di base usate più di solito sono `DataGridViewCell` e `DataGridViewColumn`. È possibile derivare la propria classe di celle da `DataGridViewCell` o da una qualsiasi delle relative classi figlio. Sebbene sia possibile aggiungere qualsiasi tipo di cella a qualsiasi colonna, in genere viene derivata anche una classe di colonna complementare da `DataGridViewColumn` che ospita celle del tipo di cella personalizzato per impostazione predefinita.  
  
 È possibile implementare l'interfaccia `IDataGridViewEditingCell` nella classe cella derivata per creare un tipo di cella con funzionalità di modifica, ma che non ospita un controllo in modalità di modifica. Per creare un controllo che può essere ospitato in una cella in modalità di modifica, è possibile implementare l'interfaccia `IDataGridViewEditingControl` in una classe derivata da <xref:System.Windows.Forms.Control>.  
  
 Per altre informazioni, vedere [How to: Customize Cells and Columns nel Windows Forms controllo DataGridView estendendo il comportamento e l'aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) e [procedura: ospitare i controlli in Windows Forms celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Riepilogo delle classi DataGridView  
 <xref:System.Windows.Forms>  
  
|Area tecnologica|Classi/interfacce/elementi di configurazione|  
|---------------------|-------------------------------------------------|  
|Data binding|<xref:System.Windows.Forms.BindingSource>|  
|Presentazione dei dati|<xref:System.Windows.Forms.DataGridView><br /><br /> classi derivate e <xref:System.Windows.Forms.DataGridViewCell><br /><br /> classi derivate e <xref:System.Windows.Forms.DataGridViewRow><br /><br /> classi derivate e <xref:System.Windows.Forms.DataGridViewColumn><br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|Estensibilità <xref:System.Windows.Forms.DataGridView>|classi derivate e <xref:System.Windows.Forms.DataGridViewCell><br /><br /> classi derivate e <xref:System.Windows.Forms.DataGridViewColumn><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Novità  
 Il controllo <xref:System.Windows.Forms.DataGridView> è progettato per essere una soluzione completa per la visualizzazione dei dati tabulari con Windows Forms. È consigliabile usare il controllo <xref:System.Windows.Forms.DataGridView> prima di altre soluzioni, ad esempio <xref:System.Windows.Forms.DataGrid>, quando si crea una nuova applicazione. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Il controllo <xref:System.Windows.Forms.DataGridView> può funzionare in stretta combinazione con il componente <xref:System.Windows.Forms.BindingSource>. Questo componente è stato progettato per essere l'origine dati primaria di un modulo. Può gestire l'interazione tra un controllo <xref:System.Windows.Forms.DataGridView> e la relativa origine dati, indipendentemente dal tipo di origine dati.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo DataGridView](datagridview-control-overview-windows-forms.md)
- [Architettura del controllo DataGridView](datagridview-control-architecture-windows-forms.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
