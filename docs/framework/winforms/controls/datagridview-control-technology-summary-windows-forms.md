---
title: Riepilogo della tecnologia del controllo DataGridView (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
ms.openlocfilehash: f8898f76971b6088fa8ca831961ea7f12e1ab4e6
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588819"
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Riepilogo della tecnologia del controllo DataGridView (Windows Form)
Questo argomento riepiloga le informazioni relative al controllo `DataGridView` e alle classi che ne supportano l'uso.  
  
 Visualizzazione dei dati in un formato tabulare è un'attività che probabilmente verranno eseguite di frequente. Il `DataGridView` controllo è progettato per essere una soluzione completa per la presentazione dei dati in una griglia.  
  
## <a name="keywords"></a>Parole chiave  
 DataGridView BindingSource, tabella, celle, l'associazione dati, la modalità virtuale  
  
## <a name="namespaces"></a>Spazi dei nomi  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Tecnologie correlate  
 `BindingSource`  
  
## <a name="background"></a>Sfondo  
 Finestre di progettazione dell'interfaccia utente di frequente che sia necessario visualizzare dati in formato tabulare per gli utenti. .NET Framework offre diversi modi per visualizzare i dati in una tabella o una griglia. Il `DataGridView` controllo rappresenta la più recente evoluzione di questa tecnologia per le applicazioni Windows Form.  
  
 Il `DataGridView` controllo può visualizzare le righe di dati da un archivio dati. Sono supportati molti tipi di archivi dati. L'archivio dati può contenere dati semplici e non tipizzati, ad esempio una matrice unidimensionale, o può contenere dati tipizzati, ad esempio un <xref:System.Data.DataSet>. Per altre informazioni, vedere [Procedura: Associare i dati per i Windows Form controllo DataGridView](how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Il controllo `DataGridView` fornisce un sistema efficiente e flessibile per visualizzare i dati in formato tabulare. È possibile usare il controllo per mostrare le visualizzazioni di sola lettura o modificabili di piccole dimensioni molto grandi set di dati.  
  
 È possibile estendere il `DataGridView` controllo in diversi modi per compilare un comportamento personalizzato nelle tue applicazioni. Ad esempio, è possibile specificare a livello di codice i propri algoritmi di ordinamento e creare i propri tipi di celle. È possibile personalizzare facilmente l'aspetto del controllo `DataGridView` scegliendo tra diverse proprietà. Molti tipi di archivi dati possono essere utilizzati come origine dati, o `DataGridView` controllo può essere utilizzato senza un'origine dati a esso associata.  
  
## <a name="implementing-datagridview-classes"></a>Implementazione di classi di DataGridView  
 Esistono diversi modi per poter sfruttare il `DataGridView` le funzionalità di estendibilità del controllo. È possibile personalizzare molti aspetti del controllo tramite proprietà ed eventi, ma alcune personalizzazioni richiedono la creazione di nuove classi derivate da esistente `DataGridView` classi.  
  
 Le classi di base utilizzate più di frequente `DataGridViewCell` e `DataGridViewColumn`. È possibile derivare la propria classe di cella da `DataGridViewCell` o una delle relative classi figlio. Sebbene sia possibile aggiungere qualsiasi tipo di cella per qualsiasi colonna, si sarà in genere anche un complementare colonna derivata da `DataGridViewColumn` che ospita le celle del tipo di cella personalizzato per impostazione predefinita.  
  
 È possibile implementare il `IDataGridViewEditingCell` interfaccia nella classe cella derivata per creare un tipo di cella che ha funzionalità di modifica, ma non ospita un controllo in modalità di modifica. Per creare un controllo che è possibile ospitare in una cella in modalità di modifica, è possibile implementare il `IDataGridViewEditingControl` interfaccia in una classe derivata da <xref:System.Windows.Forms.Control>.  
  
 Per altre informazioni, vedere [Procedura: Personalizzare celle e colonne in Windows il controllo DataGridView di form estendendone il comportamento e aspetto](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) e [come: Inserire controlli in Windows Form celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Introduzione alle classi DataGridView  
 <xref:System.Windows.Forms>  
  
|Area tecnologica|Classi/interfacce/elementi di configurazione|  
|---------------------|-------------------------------------------------|  
|Data binding|<xref:System.Windows.Forms.BindingSource>|  
|Presentazione dei dati|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell> e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewRow> e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView> Estendibilità|<xref:System.Windows.Forms.DataGridViewCell> e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn> e le classi derivate<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Novità  
 Il <xref:System.Windows.Forms.DataGridView> controllo è progettato per essere una soluzione completa per la visualizzazione di dati tabulari con Windows Form. È consigliabile usare la <xref:System.Windows.Forms.DataGridView> controllo prima di altre soluzioni, ad esempio <xref:System.Windows.Forms.DataGrid>, quando si crea una nuova applicazione. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo può interagire con il <xref:System.Windows.Forms.BindingSource> componente. Questo componente è progettato per essere l'origine dati primaria di un form. È possibile gestire l'interazione tra un <xref:System.Windows.Forms.DataGridView> controllo e la relativa origine dati, indipendentemente dal fatto i dati di tipo di origine.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo DataGridView](datagridview-control-overview-windows-forms.md)
- [Architettura del controllo DataGridView](datagridview-control-architecture-windows-forms.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
