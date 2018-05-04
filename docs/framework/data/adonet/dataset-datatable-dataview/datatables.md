---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: e148b20c7d8efdb16a897c5606535e4b0112ea29
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="datatables"></a>DataTables
Un tipo <xref:System.Data.DataSet> è composto da una raccolta di tabelle, relazioni e vincoli. In ADO.NET <xref:System.Data.DataTable> gli oggetti vengono utilizzati per rappresentare le tabelle in un **DataSet**. Oggetto **DataTable** rappresenta una tabella di dati relazionali in memoria; i dati sono locali per il. Applicazione basata su rete in cui si trova, ma possono essere popolato da un'origine dati, ad esempio Microsoft SQL Server utilizzando un **DataAdapter** per ulteriori informazioni, vedere [popolamento di un set di dati da un oggetto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .  
  
 Il **DataTable** classe è un membro del **System. Data** spazio dei nomi nella libreria di classi .NET Framework. È possibile creare e utilizzare un **DataTable** in modo indipendente o come membro di un **DataSet**, e **DataTable** oggetti possono essere utilizzati anche insieme ad altri oggetti di .NET Framework, tra cui la <xref:System.Data.DataView>. Accedere alla raccolta di tabelle in un **set di dati** tramite il **tabelle** proprietà del **DataSet** oggetto.  
  
 Lo schema o struttura di una tabella è rappresentato da colonne e vincoli. Per definire lo schema di un **DataTable** utilizzando <xref:System.Data.DataColumn> oggetti nonché <xref:System.Data.ForeignKeyConstraint> e <xref:System.Data.UniqueConstraint> oggetti. Le colonne di una tabella possono essere associate a colonne di un'origine dati, contenere valori calcolati da espressioni, incrementare automaticamente i propri valori o contenere valori di chiavi primarie.  
  
 Oltre a uno schema, un **DataTable** deve anche avere righe per contenere e ordinare i dati. La classe <xref:System.Data.DataRow> rappresenta i dati effettivi contenuti in una tabella. Utilizzare il **DataRow** e relative proprietà e metodi per recuperare, valutare e modificare i dati in una tabella. Come si accedere e modificare i dati all'interno di una riga, il **DataRow** oggetto mantiene lo stato corrente e originale.  
  
 L'utilizzo di una o più colonne correlate delle tabelle consente di creare relazioni padre-figlio tra tabelle. Creare una relazione tra **DataTable** degli oggetti mediante un <xref:System.Data.DataRelation>. **DataRelation** oggetti possono quindi essere utilizzati per restituire le righe padre o figlio correlate di una particolare riga. Per ulteriori informazioni, vedere [aggiunta di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Viene illustrato come creare un **DataTable** e aggiungerla a un **DataSet**.  
  
 [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Vengono fornite informazioni sulla creazione e utilizzo **DataColumn** oggetti e vincoli.  
  
 [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Viene spiegato come aggiungere, modificare ed eliminare i dati di una tabella Viene illustrato come utilizzare **DataTable** eventi per esaminare le modifiche ai dati nella tabella.  
  
 [Gestione di eventi DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Fornisce informazioni sugli eventi disponibili per l'utilizzo con un **DataTable**, inclusi gli eventi quando vengono modificati i valori delle colonne e righe vengono aggiunte o eliminate.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET e come usarli per l'accesso alle origini dati esistenti e per la gestione dei dati dell'applicazione.  
  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Fornisce informazioni su ADO.NET **DataSet** incluso come creare relazioni tra tabelle.  
  
 <xref:System.Data.Constraint>  
 Fornisce informazioni di riferimento sul **vincolo** oggetto.  
  
 <xref:System.Data.DataColumn>  
 Fornisce informazioni di riferimento sul **DataColumn** oggetto.  
  
 <xref:System.Data.DataSet>  
 Fornisce informazioni di riferimento sul **DataSet** oggetto.  
  
 <xref:System.Data.DataTable>  
 Fornisce informazioni di riferimento sul **DataTable** oggetto.  
  
 [Panoramica della libreria di classi](../../../../../docs/standard/class-library-overview.md)  
 Viene fornita una panoramica della libreria di classi .NET Framework, inclusi il **sistema** dello spazio dei nomi e lo spazio dei nomi di secondo livello, **System. Data**.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
