---
title: Mapping di DataAdapter, DataTable e DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151559"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Mapping di DataAdapter, DataTable e DataColumn
Oggetto **DataAdapter** contiene una raccolta <xref:System.Data.Common.DataTableMapping> di zero o più oggetti nella relativa **TableMappings** proprietà. Oggetto **DataTableMapping** fornisce un mapping master tra i dati restituiti <xref:System.Data.DataTable>da una query su un'origine dati e un oggetto . Il **DataTableMapping** nome al posto del **DataTable** nome al **Fill** metodo il **DataAdapter**. Nell'esempio seguente viene creato un **oggetto DataTableMapping** denominato **AuthorsMapping** per la tabella **Authors.**  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Oggetto **DataTableMapping** consente di utilizzare nomi di colonna in un **DataTable** diversi da quelli nel database. Il **DataAdapter** utilizza il mapping in modo che corrisponda alle colonne quando la tabella viene aggiornata.  
  
 Se non si specifica un **TableName** o un nome **DataTableMapping** quando si chiama il metodo **Fill** o **Update** di **DataAdapter**, **DataAdapter** cerca un **DataTableMapping** denominato "Table". Se tale **DataTableMapping** non esiste, il **TableName** del **DataTable** è "Table". È possibile specificare un valore predefinito **DataTableMapping** creando un **DataTableMapping** con il nome "Table".  
  
 Esempio di codice seguente crea un <xref:System.Data.Common> **DataTableMapping** (dallo spazio dei nomi) e lo rende il mapping predefinito per il **DataAdapter** specificato denominandolo "Table". Nell'esempio viene quindi eseguito il mapping delle colonne della prima tabella del risultato della query (la tabella <xref:System.Data.DataSet> **Customers** del database **Northwind)** a un set di nomi più descrittivi nella tabella Northwind **Customers** della sezione . Per le colonne di cui non viene eseguito il mapping, viene usato il nome della colonna nell'origine dati.  
  
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
  
 In situazioni più avanzate, è possibile decidere che si desidera che lo stesso **DataAdapter** supporti il caricamento di tabelle diverse con mapping diversi. A tale scopo, è sufficiente aggiungere ulteriori **DataTableMapping** oggetti.  
  
 Quando il **Fill** metodo viene passata un'istanza di un **DataSet** e un **DataTableMapping** nome, se esiste un mapping con tale nome viene utilizzato; in caso contrario, viene utilizzato un **oggetto DataTable** con tale nome.  
  
 Negli esempi seguenti viene creato un **DataTableMapping** con un nome **Customers** e un nome **DataTable** **BizTalkSchema**. Nell'esempio viene quindi eseguito il mapping delle righe restituite dall'istruzione SELECT a **BizTalkSchema** **DataTable**.  
  
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
> Se non viene indicato il nome della colonna di origine per il mapping di una colonna o il nome della tabella di origine per il mapping di una tabella, vengono generati automaticamente nomi predefiniti. Se non viene fornita alcuna colonna di origine per un mapping di colonna, al mapping di colonna viene assegnato un nome predefinito incrementale **di SourceColumn** *N,* a partire da **SourceColumn1**. Se non viene fornito alcun nome di tabella di origine per un mapping di tabella, al mapping delle tabelle viene assegnato un nome predefinito incrementale **SourceTable** *N*, a partire da **SourceTable1**.  
  
> [!NOTE]
> È consigliabile evitare la convenzione di denominazione di **SourceColumn** *N* per un mapping di colonna o **SourceTable** *N* per un mapping di tabella, poiché il nome fornito potrebbe entrare in conflitto con un nome di mapping di colonna predefinito esistente in **ColumnMappingCollection** o nel nome del mapping di tabella in **DataTableMappingCollection**. Se il nome specificato esiste già, verrà generata un'eccezione.  
  
## <a name="handling-multiple-result-sets"></a>Gestione di più set di risultati  
 Se **SelectCommand** restituisce più tabelle, **Fill** genera automaticamente nomi di tabella con valori incrementali per le tabelle nel **DataSet**, a partire dal nome della tabella specificata e continuando nel formato **NomeTabella** *N*, a partire da **NomeTabella1**. È possibile utilizzare i mapping delle tabelle per eseguire il mapping del nome della tabella generata automaticamente a un nome che si desidera specificare per la tabella nel **DataSet**. Ad esempio, per un **SelectCommand** che restituisce due tabelle, **Customers** e **Orders**, eseguire la seguente chiamata a **Fill**.  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 Nel **DataSet**: **Customers** e **Customers1**vengono create due tabelle. È possibile utilizzare i mapping di tabella per assicurarsi che la seconda tabella sia denominata **Orders** anziché **Customers1**. A tale scopo, eseguire il mapping della tabella di origine di **Customers1** alla tabella **DataSet** **Orders**, come illustrato nell'esempio seguente.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>Vedere anche

- [DataAdapter e DataReader](dataadapters-and-datareaders.md)
- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
