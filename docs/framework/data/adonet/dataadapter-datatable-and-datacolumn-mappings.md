---
title: Mapping di DataAdapter, DataTable e DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: eb6841dd24c4c7587cc2424cc1e606194da34585
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944066"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Mapping di DataAdapter, DataTable e DataColumn
Un **DataAdapter** contiene una raccolta di zero o più <xref:System.Data.Common.DataTableMapping> oggetti nella relativa proprietà **TableMappings** . Un **DataTableMapping** fornisce un mapping master tra i dati restituiti da una query su un'origine dati e un oggetto <xref:System.Data.DataTable>. Il nome di **DataTableMapping** può essere passato al posto del nome della **DataTable** al metodo **Fill** di **DataAdapter**. Nell'esempio seguente viene creato un **DataTableMapping** denominato **AuthorsMapping** per la tabella **authors** .  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Un **DataTableMapping** consente di utilizzare nomi di colonna in un **oggetto DataTable** diversi da quelli presenti nel database. **DataAdapter** utilizza il mapping per trovare la corrispondenza con le colonne quando viene aggiornata la tabella.  
  
 Se non si specifica un nome **di tabella** o di **DataTableMapping** quando si chiama il metodo **Fill** o **Update** di **DataAdapter**, **DataAdapter** Cerca un **DataTableMapping** denominato "Table". Se **DataTableMapping** non esiste, il **TableName** della **DataTable** è "Table". È possibile specificare un **DataTableMapping** predefinito creando un **DataTableMapping** con il nome "Table".  
  
 Nell'esempio di codice seguente viene creato un oggetto DataTableMapping <xref:System.Data.Common> (dallo spazio dei nomi) e il mapping predefinito per l'oggetto **DataAdapter** specificato viene denominato "Table". Nell'esempio viene quindi eseguito il mapping delle colonne della prima tabella nel risultato della query , ovvero la tabella Customers del database **Northwind** , a un set di nomi descrittivi nella tabella **Northwind** <xref:System.Data.DataSet>Customers del. Per le colonne di cui non viene eseguito il mapping, viene usato il nome della colonna nell'origine dati.  
  
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
  
 In situazioni più avanzate, è possibile che si desideri che lo stesso **DataAdapter** supporti il caricamento di tabelle diverse con mapping diversi. A tale scopo, è sufficiente aggiungere altri oggetti **DataTableMapping** .  
  
 Quando al metodo **Fill** viene passata un'istanza di un **set di dati** e un nome di **DataTableMapping** , se esiste un mapping con tale nome, viene utilizzato. in caso contrario, viene usato un **oggetto DataTable** con tale nome.  
  
 Negli esempi seguenti viene creato un **DataTableMapping** con il nome **Customers** e il nome **DataTable** **BizTalkSchema**. Nell'esempio viene quindi eseguito il mapping delle righe restituite dall'istruzione SELECT alla **DataTable** **BizTalkSchema** .  
  
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
> Se non viene indicato il nome della colonna di origine per il mapping di una colonna o il nome della tabella di origine per il mapping di una tabella, vengono generati automaticamente nomi predefiniti. Se per un mapping di colonna non viene fornita alcuna colonna di origine, al mapping delle colonne viene assegnato il nome predefinito incrementale **SourceColumn** *N,* a partire da **SourceColumn1**. Se non viene fornito alcun nome di tabella di origine per un mapping di tabella, al mapping della tabella viene assegnato il nome predefinito incrementale **SourceTable** *N*, a partire da **SourceTable1**.  
  
> [!NOTE]
> Si consiglia di evitare la convenzione di denominazione di **SourceColumn** *n* per un mapping di colonna o di **SourceTable** *n* per un mapping di tabella, perché il nome fornito potrebbe entrare in conflitto con un nome di mapping di colonna predefinito esistente nel  **ColumnMappingCollection** o nome del mapping di tabellain DataTableMappingCollection. Se il nome specificato esiste già, verrà generata un'eccezione.  
  
## <a name="handling-multiple-result-sets"></a>Gestione di più set di risultati  
 Se **SelectCommand** restituisce più tabelle, **Fill** genera automaticamente i nomi di tabella con valori incrementali per le tabelle nel **set di dati**, iniziando con il nome della tabella specificato e continuando nel formato **TableName** *N*, a partire da **TableName1**. È possibile utilizzare i mapping di tabella per eseguire il mapping del nome di tabella generato automaticamente a un nome che si desidera specificare per la tabella nel **set di dati**. Ad esempio, per un **SelectCommand** che restituisce due tabelle, **Customers** e **Orders**, eseguire la chiamata seguente a **Fill**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Nel **set di dati**vengono create due tabelle: **Customers** e **Customers1**. È possibile utilizzare i mapping delle tabelle per assicurarsi che la seconda tabella sia denominata Orders anziché **Customers1**. A tale scopo, eseguire il mapping della tabella di origine di **Customers1** agli **ordini**della tabella del **set di dati** , come illustrato nell'esempio seguente.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>Vedere anche

- [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
