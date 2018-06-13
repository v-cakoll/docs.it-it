---
title: Aggiunta di vincoli esistenti a un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: c3c28392a9e4bee0e2f9e0dcf553e13b67c378dd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758357"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Aggiunta di vincoli esistenti a un dataset
Il **riempimento** metodo il **DataAdapter** riempie una <xref:System.Data.DataSet> solo con le colonne della tabella e le righe da un'origine dati; tuttavia vincoli vengano in genere impostati dall'origine dati, il **riempimento** metodo non aggiunge queste informazioni sullo schema per il **DataSet** per impostazione predefinita. Per popolare un **DataSet** con informazioni di vincolo di chiave primaria esistente da un'origine dati, è possibile chiamare il **FillSchema** metodo il **DataAdapter**, o impostare il **MissingSchemaAction** proprietà del **DataAdapter** a **AddWithKey** prima di chiamare **riempimento**. In questo modo la chiave primaria vincoli di **DataSet** riflettano quelli nell'origine dati. Informazioni sul vincolo di chiave esterna non è incluse e deve essere create in modo esplicito, come illustrato nella [vincoli DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Aggiunta di informazioni sullo schema da un **set di dati** prima di inserire i dati assicura che i vincoli di chiave primaria siano inclusi con il <xref:System.Data.DataTable> gli oggetti di **set di dati**. Di conseguenza, quando ulteriori chiamate per compilare il **set di dati** vengono eseguite, il database primario informazioni della colonna chiave viene utilizzate per confrontare le nuove righe dall'origine dati con le righe correnti in ogni **DataTable**e i dati correnti in le tabelle viene sovrascritto con i dati dall'origine dati. Senza le informazioni sullo schema, vengono aggiunte le nuove righe dall'origine dati per il **DataSet**, generando righe duplicate.  
  
> [!NOTE]
>  Se una colonna in un'origine dati viene identificata come con incremento automatico, il **FillSchema** metodo, o **riempimento** metodo con un **MissingSchemaAction** di  **AddWithKey**, crea un **DataColumn** con un **AutoIncrement** proprietà impostata su `true`. Tuttavia, è necessario impostare il **AutoIncrementStep** e **AutoIncrementSeed** valori manualmente. Per ulteriori informazioni sulle colonne a incremento automatico, vedere [la creazione di colonne AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Utilizzando **FillSchema** o impostazione di **MissingSchemaAction** a **AddWithKey** necessaria un'elaborazione aggiuntiva nell'origine dati per determinare le informazioni di colonna chiave primaria. Questa ulteriore elaborazione può ridurre le prestazioni. Se le informazioni sulla chiave primaria sono note in fase di progettazione, è consigliabile specificare la colonna o le colonne della chiave primaria in modo esplicito per migliorare le prestazioni. Per informazioni sull'impostazione delle informazioni sulla chiave primarie per una tabella in modo esplicito, vedere [la definizione di chiavi primarie](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 Esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema da un **DataSet** utilizzando **FillSchema**.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 Esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema da un **set di dati** utilizzando il **MissingSchemaAction. AddWithKey** proprietà del **riempimento** metodo.  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>Gestione di più set di risultati  
 Se il **DataAdapter** rileva più set di risultati restituito dal **SelectCommand**, verrà create più tabelle nel **DataSet**. Le tabelle viene assegnato un nome predefinito incrementale in base zero di **tabella** *N*, a partire da **tabella** anziché con "Table0". Se un nome di tabella viene passato come argomento per il **FillSchema** (metodo), le tabelle viene assegnato un nome incrementale in base zero di **TableName** *N*, a partire da **TableName** anziché con "TableName0".  
  
> [!NOTE]
>  Se il **FillSchema** metodo il **OleDbDataAdapter** viene chiamato per un comando che restituisce più set di risultati, viene restituite solo le informazioni sullo schema dal primo set di risultati. Quando la restituzione di informazioni sullo schema per il risultato di più set mediante il **OleDbDataAdapter**, si consiglia di specificare un **MissingSchemaAction** di **AddWithKey** e ottenere le informazioni sullo schema quando si chiama il **riempimento** metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
