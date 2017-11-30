---
title: Riepilogo della tecnologia del controllo DataGridView (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- data grids [Windows Forms], about data grids
ms.assetid: 094498c3-a126-4a3f-83fe-f69e96c7717b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f172d28e5f03e1177db6ad1bd9e98f4c68267765
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="datagridview-control-technology-summary-windows-forms"></a>Riepilogo della tecnologia del controllo DataGridView (Windows Form)
Questo argomento riepiloga le informazioni relative al controllo `DataGridView` e alle classi che ne supportano l'uso.  
  
 La visualizzazione dei dati in un formato tabulare è un'attività che spesso eseguite di frequente. Il `DataGridView` controllo è progettato per essere una soluzione completa per la presentazione dei dati in una griglia.  
  
## <a name="keywords"></a>Parole chiave  
 DataGridView BindingSource, tabella, cella, associazione dati, la modalità virtuale  
  
## <a name="namespaces"></a>Spazi dei nomi  
 <xref:System.Windows.Forms?displayProperty=nameWithType>  
  
 <xref:System.Data?displayProperty=nameWithType>  
  
## <a name="related-technologies"></a>Tecnologie correlate  
 `BindingSource`  
  
## <a name="background"></a>Sfondo  
 Finestre di progettazione dell'interfaccia utente spesso è necessario visualizzare dati tabulari per gli utenti. Il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] offre diversi modi per visualizzare i dati in una tabella o una griglia. Il `DataGridView` controllo rappresenta l'evoluzione più recente di questa tecnologia per applicazioni Windows Form.  
  
 Il `DataGridView` controllo può visualizzare le righe di dati da un archivio dati. Sono supportati molti tipi di archivi dati. L'archivio dati può contenere dati semplici e non tipizzati, ad esempio una matrice unidimensionale, oppure può contenere dati tipizzati, ad esempio un <xref:System.Data.DataSet>. Per ulteriori informazioni, vedere [procedura: associare dati al controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md).  
  
 Il controllo `DataGridView` fornisce un sistema efficiente e flessibile per visualizzare i dati in formato tabulare. È possibile utilizzare il controllo per la visualizzazione in sola lettura o modificabili di piccole e grandi set di dati.  
  
 È possibile estendere il `DataGridView` controllo in diversi modi per compilare un comportamento personalizzato nelle applicazioni. Ad esempio, è possibile specificare a livello di codice i propri algoritmi di ordinamento e creare i propri tipi di celle. È possibile personalizzare facilmente l'aspetto del controllo `DataGridView` scegliendo tra diverse proprietà. Molti tipi di archivi dati possono essere utilizzati come origine dati, o `DataGridView` controllo può essere utilizzato senza un'origine dati associata.  
  
## <a name="implementing-datagridview-classes"></a>Implementazione di classi di DataGridView  
 Esistono diversi modi per poter sfruttare il `DataGridView` funzionalità di estensibilità del controllo. È possibile personalizzare molti aspetti del controllo tramite proprietà ed eventi, ma alcune personalizzazioni è necessario creare nuove classi derivate da esistente `DataGridView` classi.  
  
 Le classi di base utilizzate più di frequente sono `DataGridViewCell` e `DataGridViewColumn`. È possibile derivare la propria classe di cella da `DataGridViewCell` o le relative classi figlio. Sebbene sia possibile aggiungere qualsiasi tipo di cella per qualsiasi colonna, si verrà in genere anche derivare una classe di colonna correlata da `DataGridViewColumn` che ospita le celle del tipo di cella personalizzato per impostazione predefinita.  
  
 È possibile implementare il `IDataGridViewEditingCell` interfaccia nella classe di cella derivata per creare un tipo di cella che disponga di funzionalità di modifica, ma non ospita un controllo in modalità di modifica. Per creare un controllo che è possibile ospitare in una cella in modalità di modifica, è possibile implementare il `IDataGridViewEditingControl` interfaccia in una classe derivata da <xref:System.Windows.Forms.Control>.  
  
 Per ulteriori informazioni, vedere [procedura: personalizzare celle e colonne nel controllo DataGridView Windows Form dall'estensione di comportamento relativi e l'aspetto](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md) e [come: i controlli Host nelle celle del controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).  
  
## <a name="datagridview-classes-at-a-glance"></a>Riepilogo delle classi DataGridView  
 <xref:System.Windows.Forms>  
  
|Area tecnologica|Classi/interfacce/elementi di configurazione|  
|---------------------|-------------------------------------------------|  
|Data binding|<xref:System.Windows.Forms.BindingSource>|  
|Presentazione dei dati|<xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DataGridViewCell>e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewRow>e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn>e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewCellStyle>|  
|<xref:System.Windows.Forms.DataGridView>Estendibilità|<xref:System.Windows.Forms.DataGridViewCell>e le classi derivate<br /><br /> <xref:System.Windows.Forms.DataGridViewColumn>e le classi derivate<br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingCell><br /><br /> <xref:System.Windows.Forms.IDataGridViewEditingControl>|  
  
## <a name="whats-new"></a>Novità  
 Il <xref:System.Windows.Forms.DataGridView> controllo è progettato per essere una soluzione completa per la visualizzazione dei dati in formato tabulare con Windows Form. È consigliabile utilizzare il <xref:System.Windows.Forms.DataGridView> controllo prima di altre soluzioni, ad esempio <xref:System.Windows.Forms.DataGrid>, quando si crea una nuova applicazione. Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo può interagire con il <xref:System.Windows.Forms.BindingSource> componente. Questo componente è progettato per essere l'origine dati primaria di un form. È possibile gestire l'interazione tra un <xref:System.Windows.Forms.DataGridView> controllo e la relativa origine dati, indipendentemente dai dati di tipo di origine.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [Architettura del controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)
