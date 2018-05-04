---
title: Data binding e LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: e82cc5ecfc1272cfb4594cb556fa9455a7ea7813
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="data-binding-and-linq-to-dataset"></a>Data binding e LINQ to DataSet
*Associazione dati* è il processo che stabilisce una connessione tra l'interfaccia utente dell'applicazione e la logica di business. Se l'associazione è impostata correttamente e i dati forniscono le notifiche appropriate, quando il valore dei dati cambia la modifica si riflette automaticamente negli elementi associati ai dati. L'oggetto <xref:System.Data.DataSet> di ADO.NET è una rappresentazione di dati residente in memoria che fornisce un modello di programmazione relazionale coerente, indipendentemente dall'origine dati che contiene. L'oggetto <xref:System.Data.DataView> di ADO.NET 2.0 consente di ordinare e filtrare i dati archiviati in <xref:System.Data.DataTable>. Questa funzionalità viene spesso usata nelle applicazioni di associazione dati. Tramite un oggetto <xref:System.Data.DataView>, è possibile esporre i dati di una tabella applicando diversi tipi di ordinamento e filtrare i dati per stato di riga o sulla base di un'espressione di filtro. Per ulteriori informazioni sul <xref:System.Data.DataView> , vedere [DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consente agli sviluppatori di creare query complesse e potenti su un <xref:System.Data.DataSet> utilizzando [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]. Tuttavia, un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query restituisce un'enumerazione di <xref:System.Data.DataRow> oggetti, non è possibile utilizzare facilmente negli scenari di associazione. Per semplificare l'associazione, è possibile creare un <xref:System.Data.DataView> da un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query. Questo <xref:System.Data.DataView> utilizza il filtro e ordinamento specificate nella query, ma è più adatto per l'associazione dati. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] estende la funzionalità del <xref:System.Data.DataView> fornendo [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] basate su espressioni di filtro e ordinamento, che consente di gran lunga più complesse e potenti di filtro e ordinamento rispetto alle operazioni basate su stringa filtro.  
  
 Si noti che <xref:System.Data.DataView> rappresenta la query stessa e non è una visualizzazione sopra la query. L'oggetto <xref:System.Data.DataView> è associato a un controllo dell'interfaccia utente, ad esempio <xref:System.Windows.Forms.DataGrid> o <xref:System.Windows.Forms.DataGridView>, che fornisce un modello di associazione dati semplice. Un oggetto <xref:System.Data.DataView> può essere creato anche da <xref:System.Data.DataTable>, fornendo una visualizzazione predefinita della tabella.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataView](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Vengono fornite informazioni sulla creazione di un oggetto <xref:System.Data.DataView>.  
  
 [Filtro con DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Viene descritto come eseguire operazioni di filtro con l'oggetto <xref:System.Data.DataView>.  
  
 [Ordinamento con DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 Viene descritto come eseguire operazioni di ordinamento con l'oggetto <xref:System.Data.DataView>.  
  
 [Esecuzione di query sulla raccolta DataRowView in un oggetto DataView](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Vengono fornite informazioni sull'esecuzione di query sulla raccolta <xref:System.Data.DataRowView> esposto da <xref:System.Data.DataView>.  
  
 [Prestazioni di DataView](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Vengono fornite informazioni su <xref:System.Data.DataView> e sulle prestazioni.  
  
 [Procedura: Associare un oggetto DataView a un controllo DataGridView di Windows Form](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Viene illustrato come associare un oggetto <xref:System.Data.DataView> a <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
