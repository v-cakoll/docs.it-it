---
title: Aggiunta di vincoli esistenti a un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 90aa1e5dceb3cac87d330837496b9dc467dc1876
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43489890"
---
# <a name="adding-existing-constraints-to-a-dataset"></a>Aggiunta di vincoli esistenti a un dataset
Il **riempire** metodo per il **DataAdapter** riempie un <xref:System.Data.DataSet> solo con le colonne della tabella e le righe da un'origine dati; tuttavia i vincoli vengano in genere impostati dall'origine dati, il **riempire** metodo non aggiunge queste informazioni sullo schema per il **set di dati** per impostazione predefinita. Per popolare una **set di dati** con informazioni di vincolo di chiave primaria esistente da un'origine dati, è possibile chiamare il **FillSchema** metodo per il **DataAdapter**, o impostare il **MissingSchemaAction** proprietà delle **DataAdapter** al **AddWithKey** prima di chiamare **riempire**. In tal modo, la chiave primaria vincoli nel **set di dati** riflettano quelli nell'origine dati. Informazioni sul vincolo di chiave esterna non è inclusi e deve essere creati in modo esplicito, come illustrato nella [vincoli DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).  
  
 Aggiunta di informazioni sullo schema da un **set di dati** prima di compilarlo con i dati assicura che i vincoli di chiave primari siano inclusi con il <xref:System.Data.DataTable> gli oggetti nel **set di dati**. Di conseguenza, quando ulteriori chiamate per compilare il **set di dati** vengono eseguite, il database primario informazioni della colonna chiave viene usate per associare nuove righe dall'origine dati con le righe correnti in ogni **DataTable**e i dati correnti in le tabelle viene sovrascritto con i dati dall'origine dati. Senza le informazioni sullo schema, vengono aggiunte le nuove righe dall'origine dati per il **set di dati**, generando righe duplicate.  
  
> [!NOTE]
>  Se una colonna in un'origine dati viene identificata come con incremento automatico, il **FillSchema** metodo, o il **riempimento** metodo con un **MissingSchemaAction** di  **AddWithKey**, viene creata una **DataColumn** con un **AutoIncrement** impostata su `true`. Tuttavia, è necessario impostare il **AutoIncrementStep** e **AutoIncrementSeed** valori manualmente. Per altre informazioni sulle colonne con incremento automatico, vedere [creazione di colonne AutoIncrement](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).  
  
 Usando **FillSchema** impostazione o il **MissingSchemaAction** al **AddWithKey** necessaria un'elaborazione aggiuntiva nell'origine dati per determinare le informazioni di colonna chiave primaria. Questa ulteriore elaborazione può ridurre le prestazioni. Se le informazioni sulla chiave primaria sono note in fase di progettazione, è consigliabile specificare la colonna o le colonne della chiave primaria in modo esplicito per migliorare le prestazioni. Per informazioni sull'impostazione esplicita delle informazioni sulla chiave primarie per una tabella, vedere [definizione di chiavi primarie](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).  
  
 Esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema da un **set di dati** utilizzando **FillSchema**.  
  
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
  
 Esempio di codice seguente viene illustrato come aggiungere informazioni sullo schema da un **set di dati** usando la **MissingSchemaAction. AddWithKey** proprietà del **riempire** (metodo).  
  
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
 Se il **DataAdapter** rileva più set di risultati restituito dalle **SelectCommand**, verrà create più tabelle nel **set di dati**. Le tabelle viene assegnato un nome predefinito incrementale in base zero **tabella** *N*, che inizia con **tabella** anziché con "Table0". Se un nome di tabella viene passato come argomento per il **FillSchema** metodo, le tabelle viene assegnato un nome incrementale in base zero del **NomeTabella** *N*, che inizia con **NomeTabella** anziché con "TableName0".  
  
> [!NOTE]
>  Se il **FillSchema** metodo per il **OleDbDataAdapter** oggetto viene chiamato per un comando che restituisce più set di risultati, vengono restituite solo le informazioni dello schema dal primo set di risultati. Quando la restituzione di informazioni sullo schema per il risultato di più set mediante il **OleDbDataAdapter**, si consiglia di specificare una **MissingSchemaAction** dei **AddWithKey** e ottenere le informazioni sullo schema quando si chiama il **riempire** (metodo).  
  
## <a name="see-also"></a>Vedere anche  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
