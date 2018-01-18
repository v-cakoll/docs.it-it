---
title: Dataset ADO.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82b641bb-6001-4512-bf1a-2830acdd92ab
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b9d566f99802ea80ae73132579bb3068b1ff3b28
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="adonet-datasets"></a>Dataset ADO.NET
L'oggetto <xref:System.Data.DataSet> è fondamentale per il supporto di scenari di dati disconnessi e distribuiti con [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. Il **set di dati** è una rappresentazione residente in memoria dei dati che fornisce un modello di programmazione relazionale coerente indipendentemente dall'origine dati. È possibile usarlo con numerose origini dati diverse, con dati XML o per la gestione di dati locali all'applicazione. Il **DataSet** rappresenta un set completo di dati, incluse le tabelle correlate, vincoli e relazioni tra tabelle. La figura seguente mostra il **DataSet** modello a oggetti.  
  
 ![ADO.Net graphic](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado_1_bpuedev11")  
Modello a oggetti DataSet  
  
 I metodi e gli oggetti in un **set di dati** siano coerenti con quelli nel modello di database relazionale.  
  
 Il **DataSet** possono inoltre mantenere e ricaricare il contenuto come XML e lo schema come schema XML schema definition language (XSD). Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="the-datatablecollection"></a>DataTableCollection  
 Un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] **DataSet** contiene una raccolta di zero o più tabelle rappresentate da <xref:System.Data.DataTable> oggetti. Il <xref:System.Data.DataTableCollection> contiene tutte le **DataTable** gli oggetti in un **set di dati**.  
  
 Oggetto **DataTable** è definito nel <xref:System.Data> dello spazio dei nomi e rappresenta una singola tabella di dati residenti in memoria. In tale oggetto sono contenuti una raccolta di colonne rappresentata da un tipo <xref:System.Data.DataColumnCollection> e dei vincoli rappresentati da un tipo <xref:System.Data.ConstraintCollection>. Lo schema della tabella viene definito da questi due elementi. Oggetto **DataTable** contiene inoltre una raccolta di righe rappresentata dal <xref:System.Data.DataRowCollection>, che contiene i dati nella tabella. Oltre allo stato corrente, in <xref:System.Data.DataRow> vengono mantenute sia la versione corrente che la versione originale, in modo da consentire l'identificazione delle modifiche apportate ai valori memorizzati nella riga.  
  
## <a name="the-dataview-class"></a>Classe DataView  
 Un oggetto <xref:System.Data.DataView> consente di creare diverse visualizzazioni dei dati archiviati in un oggetto <xref:System.Data.DataTable>. Questa funzionalità è usata spesso nelle applicazioni di associazione dati. Usando un oggetto <xref:System.Data.DataView>, è possibile esporre i dati di una tabella applicando diversi tipi di ordinamento e filtrare i dati per stato di riga o sulla base di un'espressione di filtro. Per ulteriori informazioni, vedere [DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
## <a name="the-datarelationcollection"></a>DataRelationCollection  
 Oggetto **set di dati** contiene le relazioni nel relativo <xref:System.Data.DataRelationCollection> oggetto. Una relazione, rappresentata dal <xref:System.Data.DataRelation> oggetto, associa le righe in una **DataTable** con righe in un altro **DataTable**. Una relazione è analoga a un eventuale percorso di join esistente tra colonne di chiave primaria e di chiave esterna di un database relazionale. Oggetto **DataRelation** identifica le colonne corrispondenti in due tabelle di un **DataSet**.  
  
 Le relazioni consentono lo spostamento da una tabella a un'altra in un **DataSet**. Gli elementi essenziali di un **DataRelation** sono il nome della relazione, il nome di tabelle correlate e le colonne correlate in ogni tabella. È possibile compilare relazioni con più colonne per tabella specificando una matrice di oggetti <xref:System.Data.DataColumn> come colonne chiave. Quando si aggiunge una relazione con il <xref:System.Data.DataRelationCollection>, è possibile aggiungere facoltativamente un **UniqueKeyConstraint** e **ForeignKeyConstraint** per imporre vincoli di integrità quando vengono apportate modifiche alla colonna correlata valori.  
  
 Per ulteriori informazioni, vedere [aggiunta di oggetti DataRelation](../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).  
  
## <a name="xml"></a>XML  
 È possibile compilare un **DataSet** da un flusso o documento XML. È possibile utilizzare il flusso o documento XML per fornire al **DataSet** dati, le informazioni sullo schema o entrambi. Le informazioni fornite dal documento o flusso XML possono essere combinate con i dati o informazioni sullo schema già presenti nel **DataSet**. Per altre informazioni, vedere [Uso di XML in un set di dati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).  
  
## <a name="extendedproperties"></a>ExtendedProperties  
 Il **DataSet**, **DataTable**, e **DataColumn** hanno un **ExtendedProperties** proprietà. **ExtendedProperties** è un **PropertyCollection** in cui è possibile inserire informazioni personalizzate, ad esempio l'istruzione SELECT utilizzata per generare il set di risultati o l'ora di generazione quando i dati. Il **ExtendedProperties** insieme viene conservata con le informazioni sullo schema per il **DataSet**.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] fornisce funzionalità di esecuzione delle query integrate nel linguaggio per dati disconnessi archiviati in un oggetto DataSet. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]utilizza standard [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] sintassi e fornisce la verifica della sintassi in fase di compilazione, la tipizzazione statica e il supporto IntelliSense quando si utilizza il [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] IDE.  
  
 Per altre informazioni, vedere [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
