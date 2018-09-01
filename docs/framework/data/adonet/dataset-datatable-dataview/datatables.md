---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 2849d159fbfdb0c0739b76fd288a987d4ce3d02f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43395784"
---
# <a name="datatables"></a>DataTables
Un tipo <xref:System.Data.DataSet> è composto da una raccolta di tabelle, relazioni e vincoli. In ADO.NET <xref:System.Data.DataTable> gli oggetti vengono utilizzati per rappresentare le tabelle in un **set di dati**. Oggetto **DataTable** rappresenta una tabella di dati relazionali in memoria; i dati sono locali per il. Applicazione basata su rete in cui risiedono, ma possono essere popolato da un'origine dati, ad esempio Microsoft SQL Server usando un **DataAdapter** per altre informazioni, vedere [popolamento di un set di dati da un oggetto DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .  
  
 Il **DataTable** classe è un membro delle **System. Data** dello spazio dei nomi all'interno della libreria di classi .NET Framework. È possibile creare e usare una **DataTable** in modo indipendente o come membro di un **DataSet**, e **DataTable** oggetti possono essere utilizzati anche in combinazione con altri oggetti di .NET Framework, tra cui la <xref:System.Data.DataView>. Accedere alla raccolta di tabelle in un **set di dati** tramite il **tabelle** proprietà del **set di dati** oggetto.  
  
 Lo schema o struttura di una tabella è rappresentato da colonne e vincoli. Definire lo schema di un **DataTable** utilizzando <xref:System.Data.DataColumn> oggetti, nonché <xref:System.Data.ForeignKeyConstraint> e <xref:System.Data.UniqueConstraint> oggetti. Le colonne di una tabella possono essere associate a colonne di un'origine dati, contenere valori calcolati da espressioni, incrementare automaticamente i propri valori o contenere valori di chiavi primarie.  
  
 Oltre a uno schema, un **DataTable** deve anche avere righe per contenere e ordinare i dati. La classe <xref:System.Data.DataRow> rappresenta i dati effettivi contenuti in una tabella. Si utilizza il **DataRow** e relative proprietà e metodi per recuperare, valutare e modificare i dati in una tabella. Quando si accedono e modificano i dati all'interno di una riga, il **DataRow** oggetto mantiene il relativo stato corrente e originale.  
  
 L'utilizzo di una o più colonne correlate delle tabelle consente di creare relazioni padre-figlio tra tabelle. Si crea una relazione tra **DataTable** di oggetti usando un <xref:System.Data.DataRelation>. **DataRelation** oggetti possono quindi essere utilizzati per restituire le righe padre o figlio correlate di una determinata riga. Per altre informazioni, vedere [aggiunta di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 Viene illustrato come creare un **DataTable** e aggiungerlo a un **DataSet**.  
  
 [Definizione dello schema DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 Vengono fornite informazioni sulla creazione e utilizzo **DataColumn** oggetti e i vincoli.  
  
 [Manipolazione di dati in un oggetto DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 Viene spiegato come aggiungere, modificare ed eliminare i dati di una tabella Viene illustrato come utilizzare **DataTable** gli eventi per esaminare le modifiche ai dati nella tabella.  
  
 [Gestione di eventi DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 Fornisce informazioni sugli eventi disponibili per l'uso con un **DataTable**, inclusi gli eventi quando vengono modificati i valori delle colonne e righe vengono aggiunti o eliminate.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET e come usarli per l'accesso alle origini dati esistenti e per la gestione dei dati dell'applicazione.  
  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Fornisce informazioni su ADO.NET **set di dati** incluso come creare relazioni tra tabelle.  
  
 <xref:System.Data.Constraint>  
 Vengono fornite informazioni di riferimento sul **vincolo** oggetto.  
  
 <xref:System.Data.DataColumn>  
 Vengono fornite informazioni di riferimento sul **DataColumn** oggetto.  
  
 <xref:System.Data.DataSet>  
 Vengono fornite informazioni di riferimento sul **set di dati** oggetto.  
  
 <xref:System.Data.DataTable>  
 Vengono fornite informazioni di riferimento sul **DataTable** oggetto.  
  
 [Panoramica della libreria di classi](../../../../../docs/standard/class-library-overview.md)  
 Viene fornita una panoramica della libreria di classi .NET Framework, inclusi i **System** dello spazio dei nomi, nonché lo spazio dei nomi di secondo livello, **System. Data**.  
  
## <a name="see-also"></a>Vedere anche  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
