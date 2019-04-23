---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164684"
---
# <a name="ole-db-schema-collections"></a>Raccolte di schemi OLE DB
Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Provider OLE DB per Microsoft SQL Server  
 Il Driver OLE DB Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:  
  
-   Tabelle  
  
-   Colonne  
  
-   Procedure  
  
-   ProcedureParameters  
  
-   Catalog  
  
-   Indexes  
  
### <a name="tables"></a>Tabelle  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|TABLE_TYPE|Stringa|  
|TABLE_GUID|GUID|  
|DESCRIZIONE|Stringa|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Colonne  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|COLUMN_NAME|Stringa|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Booleano|  
|COLUMN_DEFAULT|Stringa|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Booleano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Stringa|  
|CHARACTER_SET_SCHEMA|Stringa|  
|CHARACTER_SET_NAME|Stringa|  
|COLLATION_CATALOG|Stringa|  
|COLLATION_SCHEMA|Stringa|  
|COLLATION_NAME|Stringa|  
|DOMAIN_CATALOG|Stringa|  
|DOMAIN_SCHEMA|Stringa|  
|DOMAIN_NAME|Stringa|  
|DESCRIZIONE|Stringa|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Booleano|  
  
### <a name="procedures"></a>Procedure  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Stringa|  
|PROCEDURE_SCHEMA|Stringa|  
|PROCEDURE_NAME|Stringa|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Stringa|  
|DESCRIZIONE|Stringa|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Stringa|  
|PROCEDURE_SCHEMA|Stringa|  
|PROCEDURE_NAME|Stringa|  
|PARAMETER_NAME|Stringa|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Booleano|  
|PARAMETER_DEFAULT|Stringa|  
|IS_NULLABLE|Booleano|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIZIONE|Stringa|  
|TYPE_NAME|Stringa|  
|LOCAL_TYPE_NAME|Stringa|  
  
### <a name="catalog"></a>Catalog  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|CATALOG_NAME|Stringa|  
|DESCRIZIONE|Stringa|  
  
### <a name="indexes"></a>Indexes  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|INDEX_CATALOG|Stringa|  
|INDEX_SCHEMA|Stringa|  
|INDEX_NAME|Stringa|  
|PRIMARY_KEY|Booleano|  
|UNIQUE|Booleano|  
|CLUSTERED|Booleano|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Booleano|  
|AUTO_UPDATE|Booleano|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Stringa|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimale|  
|PAGES|Int32|  
|FILTER_CONDITION|Stringa|  
|INTEGRATED|Booleano|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Provider OLE DB per Microsoft Oracle  
 Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:  
  
-   Tabelle  
  
-   Colonne  
  
-   Procedure  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Visualizzazioni  
  
-   Indexes  
  
### <a name="tables"></a>Tabelle  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|TABLE_TYPE|Stringa|  
|TABLE_GUID|GUID|  
|DESCRIZIONE|Stringa|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Colonne  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|COLUMN_NAME|Stringa|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Booleano|  
|COLUMN_DEFAULT|Stringa|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Booleano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Stringa|  
|CHARACTER_SET_SCHEMA|Stringa|  
|CHARACTER_SET_NAME|Stringa|  
|COLLATION_CATALOG|Stringa|  
|COLLATION_SCHEMA|Stringa|  
|COLLATION_NAME|Stringa|  
|DOMAIN_CATALOG|Stringa|  
|DOMAIN_SCHEMA|Stringa|  
|DOMAIN_NAME|Stringa|  
|DESCRIZIONE|Stringa|  
  
### <a name="procedures"></a>Procedure  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Stringa|  
|PROCEDURE_SCHEMA|Stringa|  
|PROCEDURE_NAME|Stringa|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Stringa|  
|DESCRIZIONE|Stringa|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Stringa|  
|PROCEDURE_SCHEMA|Stringa|  
|PROCEDURE_NAME|Stringa|  
|COLUMN_NAME|Stringa|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Booleano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIZIONE|Stringa|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Visualizzazioni  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|VIEW_DEFINITION|Stringa|  
|CHECK_OPTION|Booleano|  
|IS_UPDATABLE|Booleano|  
|DESCRIZIONE|Stringa|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|INDEX_CATALOG|Stringa|  
|INDEX_SCHEMA|Stringa|  
|INDEX_NAME|Stringa|  
|PRIMARY_KEY|Booleano|  
|UNIQUE|Booleano|  
|CLUSTERED|Booleano|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Booleano|  
|AUTO_UPDATE|Booleano|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Stringa|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimale|  
|PAGES|Int32|  
|FILTER_CONDITION|Stringa|  
|INTEGRATED|Booleano|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Provider OLE DB per Microsoft Jet  
 Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:  
  
-   Tabelle  
  
-   Colonne  
  
-   Procedure  
  
-   Visualizzazioni  
  
-   Indexes  
  
### <a name="tables"></a>Tabelle  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|TABLE_TYPE|Stringa|  
|TABLE_GUID|GUID|  
|DESCRIZIONE|Stringa|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Colonne  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|COLUMN_NAME|Stringa|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Booleano|  
|COLUMN_DEFAULT|Stringa|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Booleano|  
|DATA_TYPE|Int32|  
|TYPE_GUID|GUID|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Stringa|  
|CHARACTER_SET_SCHEMA|Stringa|  
|CHARACTER_SET_NAME|Stringa|  
|COLLATION_CATALOG|Stringa|  
|COLLATION_SCHEMA|Stringa|  
|COLLATION_NAME|Stringa|  
|DOMAIN_CATALOG|Stringa|  
|DOMAIN_SCHEMA|Stringa|  
|DOMAIN_NAME|Stringa|  
|DESCRIZIONE|Stringa|  
  
### <a name="procedures"></a>Procedure  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Stringa|  
|PROCEDURE_SCHEMA|Stringa|  
|PROCEDURE_NAME|Stringa|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Stringa|  
|DESCRIZIONE|Stringa|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Visualizzazioni  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|VIEW_DEFINITION|Stringa|  
|CHECK_OPTION|Booleano|  
|IS_UPDATABLE|Booleano|  
|DESCRIZIONE|Stringa|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|Nome colonna|Tipo di dati|  
|----------------|--------------|  
|TABLE_CATALOG|Stringa|  
|TABLE_SCHEMA|Stringa|  
|TABLE_NAME|Stringa|  
|INDEX_CATALOG|Stringa|  
|INDEX_SCHEMA|Stringa|  
|INDEX_NAME|Stringa|  
|PRIMARY_KEY|Booleano|  
|UNIQUE|Booleano|  
|CLUSTERED|Booleano|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Booleano|  
|AUTO_UPDATE|Booleano|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Stringa|  
|COLUMN_GUID|GUID|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Decimale|  
|PAGES|Int32|  
|FILTER_CONDITION|Stringa|  
|INTEGRATED|Booleano|  
  
## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
