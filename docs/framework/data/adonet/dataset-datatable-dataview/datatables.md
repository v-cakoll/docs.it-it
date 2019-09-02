---
title: DataTables
ms.date: 03/30/2017
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
ms.openlocfilehash: 365eafc938f3db511fd6714bec02cea2bd27ea25
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204968"
---
# <a name="datatables"></a>DataTables
Un tipo <xref:System.Data.DataSet> è composto da una raccolta di tabelle, relazioni e vincoli. In ADO.NET, <xref:System.Data.DataTable> gli oggetti vengono usati per rappresentare le tabelle in un **set di dati**. Un **DataTable** rappresenta una tabella di dati relazionali in memoria; i dati sono locali a. Applicazione basata su rete in cui risiede, ma che può essere popolata da un'origine dati, ad esempio Microsoft SQL Server usando un **DataAdapter** per ulteriori informazioni, vedere [popolamento di un DataSet da un oggetto DataAdapter](../populating-a-dataset-from-a-dataadapter.md).  
  
 La classe **DataTable** è un membro dello spazio dei nomi **System. Data** all'interno della libreria di classi .NET Framework. È possibile creare e usare una **DataTable** in modo indipendente o come membro di un **set di dati**e gli oggetti **DataTable** possono essere usati anche insieme ad altri oggetti <xref:System.Data.DataView>.NET Framework, tra cui. È possibile accedere alla raccolta di tabelle in un **set di dati** tramite la proprietà **Tables** dell'oggetto **DataSet** .  
  
 Lo schema o struttura di una tabella è rappresentato da colonne e vincoli. Si definisce lo schema di una **DataTable** usando <xref:System.Data.DataColumn> <xref:System.Data.ForeignKeyConstraint> oggetti, nonché oggetti e <xref:System.Data.UniqueConstraint> . Le colonne di una tabella possono essere associate a colonne di un'origine dati, contenere valori calcolati da espressioni, incrementare automaticamente i propri valori o contenere valori di chiavi primarie.  
  
 Oltre a uno schema, è necessario che un **oggetto DataTable** includa anche righe che contengono e ordinano i dati. La classe <xref:System.Data.DataRow> rappresenta i dati effettivi contenuti in una tabella. Usare **DataRow** e i relativi metodi e proprietà per recuperare, valutare e modificare i dati in una tabella. Quando si accede e si modificano i dati all'interno di una riga, l'oggetto **DataRow** mantiene lo stato corrente e quello originale.  
  
 L'utilizzo di una o più colonne correlate delle tabelle consente di creare relazioni padre-figlio tra tabelle. Si crea una relazione tra oggetti **DataTable** usando un <xref:System.Data.DataRelation>oggetto. Gli oggetti DataRelation possono quindi essere utilizzati per restituire le righe padre o figlio correlate di una determinata riga. Per ulteriori informazioni, vedere [aggiunta](adding-datarelations.md)di oggetti DataRelations.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Creazione di un oggetto DataTable](creating-a-datatable.md)  
 Viene illustrato come creare una **DataTable** e aggiungerla a un **set di dati**.  
  
 [Definizione dello schema DataTable](datatable-schema-definition.md)  
 Vengono fornite informazioni sulla creazione e sull'utilizzo di oggetti e vincoli **DataColumn** .  
  
 [Manipolazione di dati in un oggetto DataTable](manipulating-data-in-a-datatable.md)  
 Viene spiegato come aggiungere, modificare ed eliminare i dati di una tabella Viene illustrato come utilizzare gli eventi **DataTable** per esaminare le modifiche apportate ai dati nella tabella.  
  
 [Gestione di eventi DataTable](handling-datatable-events.md)  
 Fornisce informazioni sugli eventi disponibili per l'utilizzo con un **oggetto DataTable**, inclusi gli eventi quando vengono modificati i valori di colonna e le righe vengono aggiunte o eliminate.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [ADO.NET](../index.md)  
 Vengono descritti l'architettura e i componenti di ADO.NET e come usarli per l'accesso alle origini dati esistenti e per la gestione dei dati dell'applicazione.  
  
 [Oggetti DataSet, DataTable e DataView](index.md)  
 Fornisce informazioni sul set di **dati** ADO.NET, inclusa la modalità di creazione di relazioni tra tabelle.  
  
 <xref:System.Data.Constraint>  
 Fornisce informazioni di riferimento sull'oggetto **vincolo** .  
  
 <xref:System.Data.DataColumn>  
 Fornisce informazioni di riferimento sull'oggetto **DataColumn** .  
  
 <xref:System.Data.DataSet>  
 Fornisce informazioni di riferimento sull'oggetto **DataSet** .  
  
 <xref:System.Data.DataTable>  
 Fornisce informazioni di riferimento sull'oggetto **DataTable** .  
  
 [Panoramica della libreria di classi](../../../../standard/class-library-overview.md)  
 Viene fornita una panoramica della libreria di classi .NET Framework, inclusi lo spazio dei nomi **System** e il relativo spazio dei nomi di secondo livello, **System. Data**.  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
