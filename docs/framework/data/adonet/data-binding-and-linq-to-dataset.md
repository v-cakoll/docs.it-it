---
title: Data binding e LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: 563d57249daa3aa720da1d9654866727f770afb3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786697"
---
# <a name="data-binding-and-linq-to-dataset"></a>Data binding e LINQ to DataSet
Il *Data Binding* è il processo che stabilisce una connessione tra l'interfaccia utente dell'applicazione e la logica di business. Se l'associazione è impostata correttamente e i dati forniscono le notifiche appropriate, quando il valore dei dati cambia la modifica si riflette automaticamente negli elementi associati ai dati. L'oggetto <xref:System.Data.DataSet> di ADO.NET è una rappresentazione di dati residente in memoria che fornisce un modello di programmazione relazionale coerente, indipendentemente dall'origine dati che contiene. L'oggetto <xref:System.Data.DataView> di ADO.NET 2.0 consente di ordinare e filtrare i dati archiviati in <xref:System.Data.DataTable>. Questa funzionalità viene spesso usata nelle applicazioni di data binding. Tramite un oggetto <xref:System.Data.DataView>, è possibile esporre i dati di una tabella applicando diversi tipi di ordinamento e filtrare i dati per stato di riga o sulla base di un'espressione di filtro. Per ulteriori informazioni sull' <xref:System.Data.DataView> oggetto, vedere [DataViews](./dataset-datatable-dataview/dataviews.md).  
  
 LINQ to DataSet consente agli sviluppatori di creare query complesse e potenti su <xref:System.Data.DataSet> un usando [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]. Tuttavia, una query LINQ to DataSet restituisce un'enumerazione di <xref:System.Data.DataRow> oggetti, che non è facile da utilizzare in uno scenario di associazione. Per semplificare l'associazione, è possibile creare un <xref:System.Data.DataView> oggetto da una query LINQ to DataSet. Questa <xref:System.Data.DataView> operazione usa il filtro e l'ordinamento specificati nella query, ma è più adatto per data binding. LINQ to DataSet estende la funzionalità di <xref:System.Data.DataView> [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] mediante l'applicazione di filtri e ordinamento basati sulle espressioni, che consente operazioni di filtro e ordinamento molto più complesse e potenti rispetto all'ordinamento e al filtro basati su stringa.  
  
 Si noti che <xref:System.Data.DataView> rappresenta la query stessa e non è una visualizzazione sopra la query. L'oggetto <xref:System.Data.DataView> è associato a un controllo dell'interfaccia utente, ad esempio <xref:System.Windows.Forms.DataGrid> o <xref:System.Windows.Forms.DataGridView>, che fornisce un modello di data binding semplice. Un oggetto <xref:System.Data.DataView> può essere creato anche da <xref:System.Data.DataTable>, fornendo una visualizzazione predefinita della tabella.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataView](creating-a-dataview-object-linq-to-dataset.md)  
 Vengono fornite informazioni sulla creazione di un oggetto <xref:System.Data.DataView>.  
  
 [Filtro con DataView](filtering-with-dataview-linq-to-dataset.md)  
 Viene descritto come eseguire operazioni di filtro con l'oggetto <xref:System.Data.DataView>.  
  
 [Ordinamento con DataView](sorting-with-dataview-linq-to-dataset.md)  
 Viene descritto come eseguire operazioni di ordinamento con l'oggetto <xref:System.Data.DataView>.  
  
 [Esecuzione di query sulla raccolta DataRowView in un oggetto DataView](querying-the-datarowview-collection-in-a-dataview.md)  
 Vengono fornite informazioni sull'esecuzione di query sulla raccolta <xref:System.Data.DataRowView> esposto da <xref:System.Data.DataView>.  
  
 [Prestazioni di DataView](dataview-performance.md)  
 Vengono fornite informazioni su <xref:System.Data.DataView> e sulle prestazioni.  
  
 [Procedura: Associare un oggetto DataView a un controllo DataGridView Windows Forms](how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Viene illustrato come associare un oggetto <xref:System.Data.DataView> a <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori](programming-guide-linq-to-dataset.md)
