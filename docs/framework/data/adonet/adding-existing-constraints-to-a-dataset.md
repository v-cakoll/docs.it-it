---
title: Aggiunta di vincoli esistenti a un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 267d6489d39f86fc06b35de8cf30dad74f501b0b
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523231"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Aggiunta di vincoli esistenti a un dataset

Il metodo **Fill** di **DataAdapter** compila un <xref:System.Data.DataSet> solo con le colonne e le righe della tabella di un'origine dati. Sebbene i vincoli siano comunemente impostati dall'origine dati, il metodo **Fill** non aggiunge le informazioni sullo schema al **set** di dati per impostazione predefinita. Per popolare un **set** di dati con informazioni sui vincoli PRIMARY KEY esistenti da un'origine dati, è possibile chiamare il metodo **FillSchema** di **DataAdapter**oppure impostare la proprietà **MissingSchemaAction** di **DataAdapter** . per **AddWithKey** prima di chiamare **Fill**. In questo modo si garantisce che i vincoli PRIMARY KEY nel **set** di dati corrispondano a quelli dell'origine dati. Le informazioni sui vincoli di chiave esterna non sono incluse e devono essere create in modo esplicito, come illustrato nei [vincoli DataTable](./dataset-datatable-dataview/datatable-constraints.md).  
  
L'aggiunta di informazioni sullo schema a un **set** di dati prima di compilarlo con i dati garantisce che i vincoli PRIMARY KEY siano inclusi con gli oggetti <xref:System.Data.DataTable> nel **DataSet**. Di conseguenza, quando vengono effettuate chiamate aggiuntive per il riempimento del **set** di dati, le informazioni sulla colonna chiave primaria vengono usate per trovare una corrispondenza tra le nuove righe dell'origine dati e le righe correnti in ogni **DataTable**e i dati correnti delle tabelle vengono sovrascritti con i dati del origine dati. Senza le informazioni sullo schema, le nuove righe dall'origine dati vengono accodate al **DataSet**, ottenendo righe duplicate.  
  
> [!NOTE]
> Se una colonna in un'origine dati viene identificata come incremento automatico, il metodo **FillSchema** o il metodo **Fill** con un oggetto **MissingSchemaAction** di **AddWithKey**, crea una **DataColumn** con una proprietà **AutoIncrement** impostare su `true`. Tuttavia, sarà necessario impostare manualmente i valori **AutoIncrementStep** e **AutoIncrementSeed** . Per altre informazioni sulle colonne a incremento automatico, vedere [creazione di colonne AutoIncrement](./dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
L'uso di **FillSchema** o dell'impostazione di **MissingSchemaAction** su **AddWithKey** richiede un'elaborazione aggiuntiva nell'origine dati per determinare le informazioni sulla colonna chiave primaria. Questa ulteriore elaborazione può ridurre le prestazioni. Se le informazioni sulla chiave primaria sono note in fase di progettazione, è consigliabile specificare la colonna o le colonne della chiave primaria in modo esplicito per migliorare le prestazioni. Per informazioni sull'impostazione esplicita delle informazioni sulla chiave primaria per una tabella, vedere [definizione di chiavi primarie](./dataset-datatable-dataview/defining-primary-keys.md).
  
Nell'esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema a un **DataSet** utilizzando **FillSchema**:
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
Nell'esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema a un **DataSet** utilizzando la proprietà **MissingSchemaAction. AddWithKey** del metodo **Fill** :
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a>Gestione di più set di risultati  

Se **DataAdapter** rileva più set di risultati restituiti da **SelectCommand**, creerà più tabelle nel **set di dati**. Alle tabelle verrà assegnato un nome predefinito incrementale in base zero della **tabella** *N*, a partire dalla **tabella** anziché da "Table0". Se un nome di tabella viene passato come argomento al metodo **FillSchema** , alle tabelle verrà assegnato un nome incrementale in base zero di **TableName** *N*, a partire da **TableName** anziché da "TableName0".  
  
> [!NOTE]
> Se viene chiamato il metodo **FillSchema** dell'oggetto **OleDbDataAdapter** per un comando che restituisce più set di risultati, vengono restituite solo le informazioni sullo schema del primo set di risultati. Quando si restituiscono informazioni sullo schema per più set di risultati utilizzando **OleDbDataAdapter**, è consigliabile specificare un **MissingSchemaAction** di **AddWithKey** e ottenere le informazioni sullo schema durante la chiamata al **riempimento** Metodo.  
  
## <a name="see-also"></a>Vedere anche

- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Oggetti DataSet, DataTable e DataView](./dataset-datatable-dataview/index.md)
- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
