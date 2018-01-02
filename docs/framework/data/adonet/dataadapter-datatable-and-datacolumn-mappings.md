---
title: Mapping di DataAdapter, DataTable e DataColumn
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3df07f8b7bf71d658e9073a8aeb3d51dee087544
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Mapping di DataAdapter, DataTable e DataColumn
Oggetto **DataAdapter** contiene una raccolta di zero o più <xref:System.Data.Common.DataTableMapping> gli oggetti relativi **TableMappings** proprietà. Oggetto **DataTableMapping** fornisce un mapping master tra i dati restituiti da una query su un'origine dati e un <xref:System.Data.DataTable>. Il **DataTableMapping** nome può essere passato al posto del **DataTable** nome per il **riempimento** metodo il **DataAdapter**. Nell'esempio seguente viene creato un **DataTableMapping** denominato **AuthorsMapping** per il **autori** tabella.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Oggetto **DataTableMapping** consente di utilizzare nomi di colonna in un **DataTable** diversi da quelli presenti nel database. Il **DataAdapter** utilizza il mapping per la corrispondenza delle colonne quando viene aggiornata la tabella.  
  
 Se non si specifica un **TableName** o un **DataTableMapping** nome quando si chiama il **riempimento** o **aggiornamento** metodo il  **DataAdapter**, **DataAdapter** Cerca un **DataTableMapping** denominato "Table". Se tale **DataTableMapping** non esiste, il **TableName** del **DataTable** sarà "Table". È possibile specificare un valore predefinito **DataTableMapping** creando un **DataTableMapping** con il nome "Table".  
  
 L'esempio di codice seguente crea un **DataTableMapping** (dal <xref:System.Data.Common> dello spazio dei nomi) e lo rende il mapping predefinito per l'oggetto specificato **DataAdapter** denominandolo "Table". Viene quindi eseguito il mapping di colonne della prima tabella nel risultato della query (il **clienti** tabella il **Northwind** database) a un set di nomi più descrittivi nel **Customers di Northwind**  tabella il <xref:System.Data.DataSet>. Per le colonne di cui non viene eseguito il mapping, viene usato il nome della colonna nell'origine dati.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =   
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 In situazioni più avanzate, è possibile che si desidera che lo stesso **DataAdapter** per supportare il caricamento di diverse tabelle con mapping diversi. A tale scopo, è sufficiente aggiungere altri **DataTableMapping** oggetti.  
  
 Quando il **riempimento** metodo verrà passato un'istanza di un **set di dati** e **DataTableMapping** nome, se esiste un mapping con quel nome è utilizzato in caso contrario, un  **DataTable** nome che viene usato.  
  
 Gli esempi seguenti creano un **DataTableMapping** con un nome di **clienti** e **DataTable** nome di **BizTalkSchema**. Nell'esempio viene quindi eseguito il mapping le righe restituite dall'istruzione SELECT per la **BizTalkSchema** **DataTable**.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =   
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
>  Se non viene indicato il nome della colonna di origine per il mapping di una colonna o il nome della tabella di origine per il mapping di una tabella, vengono generati automaticamente nomi predefiniti. Se nessuna colonna di origine viene fornita per il mapping di una colonna, il mapping della colonna viene assegnato il nome predefinito incrementale **SourceColumn** *N,* a partire da **SourceColumn1**. Se viene specificato alcun nome di tabella di origine per il mapping di una tabella, il mapping di tabella viene assegnato il nome predefinito incrementale **SourceTable** *N*, a partire da **SourceTable1**.  
  
> [!NOTE]
>  Si consiglia di evitare la convenzione di denominazione **SourceColumn** *N* per il mapping di una colonna, o **SourceTable** *N* per una tabella mapping, poiché il nome sia in conflitto con un nome di mapping di colonna predefinito esistente nel **ColumnMappingCollection** o nome della tabella mapping nel **DataTableMappingCollection** . Se il nome specificato esiste già, verrà generata un'eccezione.  
  
## <a name="handling-multiple-result-sets"></a>Gestione di più set di risultati  
 Se il **SelectCommand** restituisce più tabelle, **riempimento** genera automaticamente i nomi di tabella con valori incrementali per le tabelle il **set di dati**, che inizia con il specificato nome di tabella e continuando nel formato **TableName** *N*, a partire da **TableName1**. È possibile utilizzare i mapping di tabella per il mapping del nome della tabella generato automaticamente in un nome che si desidera specificare per la tabella di **DataSet**. Ad esempio, per un **SelectCommand** che restituisce due tabelle, **clienti** e **ordini**, eseguire la chiamata seguente a **riempimento**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Cui vengono create due tabelle di **DataSet**: **clienti** e **Customers1**. È possibile utilizzare i mapping di tabella per assicurarsi che la seconda tabella è denominata **ordini** anziché **Customers1**. A tale scopo, eseguire il mapping di tabella di origine della **Customers1** per il **DataSet** tabella **ordini**, come illustrato nell'esempio seguente.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>Vedere anche  
 [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
