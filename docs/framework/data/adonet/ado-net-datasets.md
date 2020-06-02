---
title: DataSets
description: Informazioni sul set di dati, una rappresentazione di dati residente in memoria che fornisce un modello di programmazione relazionale coerente indipendentemente dall'origine dati in ADO.NET.
ms.date: 03/30/2017
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
ms.openlocfilehash: 2fc5963937f7bf15dc192c6dc0a980d544a23194
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287129"
---
# <a name="adonet-datasets"></a>Dataset ADO.NET
L' <xref:System.Data.DataSet> oggetto è fondamentale per supportare scenari di dati disconnessi e distribuiti con ADO.NET. Il **set** di dati è una rappresentazione di dati residente in memoria che fornisce un modello di programmazione relazionale coerente indipendentemente dall'origine dati. È possibile usarlo con numerose origini dati diverse, con dati XML o per la gestione di dati locali all'applicazione. Il **set di dati rappresenta un** set completo di dati, tra cui tabelle correlate, vincoli e relazioni tra le tabelle. Nella figura seguente viene illustrato il modello a oggetti del **set di dati** .  
  
 ![Rappresentazione grafica di ADO.Net](./media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Modello a oggetti DataSet  
  
 I metodi e gli oggetti in un **set** di dati sono coerenti con quelli nel modello di database relazionale.  
  
 Il **set di dati** può inoltre salvare in modo permanente e ricaricare il contenuto come XML e lo schema come XML Schema Definition Language schema XSD. Per altre informazioni, vedere [Uso di XML in un set di dati](./dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 Un **set di dati** ADO.NET contiene una raccolta di zero o più tabelle rappresentate da <xref:System.Data.DataTable> oggetti. <xref:System.Data.DataTableCollection>Contiene tutti gli oggetti **DataTable** in un **set di dati**.  
  
 Un **DataTable** viene definito nello <xref:System.Data> spazio dei nomi e rappresenta una singola tabella di dati residenti in memoria. In tale oggetto sono contenuti una raccolta di colonne rappresentata da un tipo <xref:System.Data.DataColumnCollection> e dei vincoli rappresentati da un tipo <xref:System.Data.ConstraintCollection>. Lo schema della tabella viene definito da questi due elementi. Una **DataTable** contiene inoltre una raccolta di righe rappresentate dall'oggetto <xref:System.Data.DataRowCollection> , che contiene i dati nella tabella. Oltre allo stato corrente, in <xref:System.Data.DataRow> vengono mantenute sia la versione corrente che la versione originale, in modo da consentire l'identificazione delle modifiche apportate ai valori memorizzati nella riga.  
  
## <a name="the-dataview-class"></a>Classe DataView  
 Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati. Usando un oggetto <xref:System.Data.DataView>, è possibile esporre i dati di una tabella applicando diversi tipi di ordinamento e filtrare i dati per stato di riga o sulla base di un'espressione di filtro. Per altre informazioni, vedere [DataViews](./dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 Un **set di dati** contiene relazioni nell' <xref:System.Data.DataRelationCollection> oggetto. Una relazione, rappresentata dall' <xref:System.Data.DataRelation> oggetto, associa le righe di una **DataTable** alle righe di un'altra **DataTable**. Una relazione è analoga a un eventuale percorso di join esistente tra colonne di chiave primaria e di chiave esterna di un database relazionale. Una **DataRelation** identifica le colonne corrispondenti in due tabelle di un **set di dati**.  
  
 Le relazioni consentono la navigazione da una tabella a un'altra in un **set di dati**. Gli elementi essenziali di un oggetto **DataRelation** sono il nome della relazione, il nome delle tabelle correlate e le colonne correlate in ogni tabella. È possibile compilare relazioni con più colonne per tabella specificando una matrice di oggetti <xref:System.Data.DataColumn> come colonne chiave. Quando si aggiunge una relazione a <xref:System.Data.DataRelationCollection> , è possibile aggiungere facoltativamente un **UniqueKeyConstraint** e un **vincolo ForeignKeyConstraint** per applicare i vincoli di integrità quando vengono apportate modifiche ai valori di colonna correlati.  
  
 Per ulteriori informazioni, vedere [aggiunta di oggetti DataRelations](./dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 È possibile compilare un **set di dati** da un flusso o documento XML. È possibile utilizzare il flusso o il documento XML per fornire al **set** di dati i dati, le informazioni sullo schema o entrambi. Le informazioni fornite dal flusso o dal documento XML possono essere combinate con i dati esistenti o le informazioni sullo schema già presenti nel **set**di dati. Per altre informazioni, vedere [Uso di XML in un set di dati](./dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 **DataSet**, **DataTable**e **DataColumn** dispongono tutti di una proprietà **ExtendedProperties** . **ExtendedProperties** è un **PropertyCollection** in cui è possibile inserire informazioni personalizzate, ad esempio l'istruzione SELECT utilizzata per generare il set di risultati o l'ora in cui sono stati generati i dati. La raccolta **ExtendedProperties** viene mantenute con le informazioni sullo schema per il **set di dati**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 LINQ to DataSet fornisce funzionalità di query integrate nel linguaggio per i dati disconnessi archiviati in un set di dati. LINQ to DataSet usa la sintassi LINQ standard e fornisce il controllo della sintassi in fase di compilazione, la tipizzazione statica e il supporto IntelliSense quando si usa l'IDE di Visual Studio.  
  
 Per altre informazioni, vedere [LINQ to DataSet](linq-to-dataset.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](ado-net-overview.md)
- [Oggetti DataSet, DataTable e DataView](./dataset-datatable-dataview/index.md)
- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
