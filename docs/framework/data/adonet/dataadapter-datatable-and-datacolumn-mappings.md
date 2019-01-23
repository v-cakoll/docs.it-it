---
title: Mapping di DataAdapter, DataTable e DataColumn
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6aaaa126a0b19300abc2c10b88b0e4ff39a3ad66
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530433"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>Mapping di DataAdapter, DataTable e DataColumn
Oggetto **DataAdapter** contiene una raccolta di zero o più <xref:System.Data.Common.DataTableMapping> oggetti nel relativo **TableMappings** proprietà. Oggetto **DataTableMapping** fornisce un mapping master tra i dati restituiti da una query su un'origine dati e un <xref:System.Data.DataTable>. Il **DataTableMapping** nome può essere passato al posto del **DataTable** nome per il **riempire** metodo il **DataAdapter**. L'esempio seguente crea una **DataTableMapping** denominata **AuthorsMapping** per il **autori** tabella.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 Oggetto **DataTableMapping** consente di usare i nomi delle colonne in un **DataTable** che sono diversi da quelli presenti nel database. Il **DataAdapter** Usa il mapping per associare le colonne quando viene aggiornata la tabella.  
  
 Se non si specifica un **TableName** o un **DataTableMapping** assegnare un nome quando si chiama il **riempire** o **Update** metodo il  **DataAdapter**, il **DataAdapter** Cerca un **DataTableMapping** denominato "Table". Se tale **DataTableMapping** non esiste, il **NomeTabella** del **DataTable** sarà "Table". È possibile specificare un valore predefinito **DataTableMapping** mediante la creazione di un **DataTableMapping** con il nome "Table".  
  
 L'esempio di codice seguente crea una **DataTableMapping** (dalle <xref:System.Data.Common> dello spazio dei nomi) e lo rende il mapping predefinito per l'oggetto specificato **DataAdapter** denominandolo "Table". Nell'esempio viene quindi eseguito il mapping di colonne della prima tabella nel risultato della query (il **clienti** tabella del **Northwind** database) a un set di nomi più descrittivi nel **Northwind Customers**  tabella di <xref:System.Data.DataSet>. Per le colonne di cui non viene eseguito il mapping, viene usato il nome della colonna nell'origine dati.  
  
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
  
 In situazioni più avanzate, è possibile decidere che si desidera lo stesso **DataAdapter** per supportare il caricamento di tabelle diverse con mapping diversi. A tale scopo, è sufficiente aggiungere ulteriori **DataTableMapping** oggetti.  
  
 Quando il **riempire** metodo viene passato un'istanza di un **DataSet** e un **DataTableMapping** nome, se esiste un mapping con lo stesso nome, viene utilizzata; in caso contrario, un  **DataTable** con tale nome viene usato.  
  
 Nell'esempio seguente viene creata una **DataTableMapping** con il nome **clienti** e un **DataTable** nome del **BizTalkSchema**. Nell'esempio viene quindi eseguito il mapping le righe restituite dall'istruzione SELECT per la **BizTalkSchema** **DataTable**.  
  
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
>  Se non viene indicato il nome della colonna di origine per il mapping di una colonna o il nome della tabella di origine per il mapping di una tabella, vengono generati automaticamente nomi predefiniti. Se nessuna colonna di origine viene fornita per il mapping di colonna, il mapping della colonna viene assegnato il nome predefinito incrementale **SourceColumn** *N* partire **SourceColumn1**. Se viene specificato alcun nome di tabella di origine per il mapping di tabella, il mapping di tabella viene assegnato il nome predefinito incrementale **SourceTable** *N*, che inizia con **SourceTable1**.  
  
> [!NOTE]
>  Si consiglia di evitare la convenzione di denominazione **SourceColumn** *N* per il mapping di colonna, o **SourceTable** *N* per una tabella il mapping, poiché il nome immesso sia in conflitto con un nome di mapping di colonna predefinito esistente nel **ColumnMappingCollection** o della tabella mapping nella **DataTableMappingCollection** . Se il nome specificato esiste già, verrà generata un'eccezione.  
  
## <a name="handling-multiple-result-sets"></a>Gestione di più set di risultati  
 Se il **SelectCommand** restituisce più tabelle, **riempimento** genera automaticamente i nomi delle tabelle con valori incrementali per le tabelle nel **set di dati**, che inizia con il specificato nome di tabella e continuando nel modulo **NomeTabella** *N*, che inizia con **TableName1**. È possibile usare i mapping di tabella per eseguire il mapping il nome della tabella generato automaticamente a un nome che si desidera specificare per la tabella di **set di dati**. Ad esempio, per un **SelectCommand** che restituisce le due tabelle **clienti** e **ordini**, emettere la chiamata seguente a **riempire**.  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 Vengono create due tabelle nel **set di dati**: **I clienti** e **Customers1**. È possibile usare i mapping di tabella per assicurarsi che la seconda tabella è denominata **ordini** invece di **Customers1**. A tale scopo, eseguire il mapping di tabella di origine della **Customers1** per il **DataSet** tabella **ordini**, come illustrato nell'esempio seguente.  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a>Vedere anche
- [DataAdapter e DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
