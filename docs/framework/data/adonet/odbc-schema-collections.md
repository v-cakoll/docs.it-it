---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: f0240e99d2420b0956d3c144f837b39e094bb78a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794725"
---
# <a name="odbc-schema-collections"></a>Raccolte di schemi ODBC

Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.

## <a name="microsoft-sql-server-odbc-driver"></a>Driver ODBC di Microsoft SQL Server

Oltre alle raccolte di schemi comuni, il driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici:

- Tabelle

- Indexes

- Colonne

- Procedure

- ProcedureColumns

- ProcedureParameters

- Visualizzazioni

### <a name="tables-and-views"></a>Tables e Views

|ColumnName|Tipo di dati|
|----------------|--------------|
|TABLE_CAT|String|
|TABLE_SCHEM|String|
|TABLE_NAME|String|
|TABLE_TYPE|String|
|REMARKS|String|

### <a name="indexes"></a>Indexes

|ColumnName|Tipo di dati|
|----------------|--------------|
|TABLE_CAT|String|
|TABLE_SCHEM|String|
|TABLE_NAME|String|
|NON_UNIQUE|Int16|
|INDEX_QUALIFIER|String|
|INDEX_NAME|String|
|TYPE|Int16|
|ORDINAL_POSITION|Int16|
|COLUMN_NAME|String|
|ASC_OR_DESC|String|
|CARDINALITY|Int32|
|PAGES|Int32|
|FILTER_CONDITION|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

### <a name="columns"></a>Colonne

|ColumnName|Tipo di dati|
|----------------|--------------|
|TABLE_CAT|String|
|TABLE_SCHEM|String|
|TABLE_NAME|String|
|COLUMN_NAME|String|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|
|SS_TYPE_CATALOG|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

### <a name="procedures"></a>Procedure

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|NUM_INPUT_PARAMS|Int32|
|NUM_OUTPUT_PARAMS|Int32|
|NUM_RESULT_SETS|Int32|
|REMARKS|String|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|
|SS_TYPE_CATALOG|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|
|SS_TYPE_CATALOG|String|
|SS_TYPE_SCHEMA|String|
|SS_DATA_TYPE|Byte|

## <a name="microsoft-oracle-odbc-driver"></a>Driver Microsoft ODBC per Oracle

Oltre alle raccolte di schemi comuni, il driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici:

- Tabelle

- Colonne

- Procedure

- ProcedureColumns

- ProcedureParameters

- Visualizzazioni

- Indexes

### <a name="tables-and-views"></a>Tables e Views

|ColumnName|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|TABLE_TYPE|String|
|REMARKS|String|

### <a name="columns"></a>Colonne

|ColumnName|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|COLUMN_NAME|String|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedure

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|REMARKS|String|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

## <a name="microsoft-jet-odbc-driver"></a>Driver ODBC per Microsoft Jet

Oltre alle raccolte di schemi comuni, il driver ODBC per Microsoft Jet supporta le raccolte di schemi specifici seguenti:

- Tabelle

- Indexes

- Colonne

- Procedure

- ProcedureColumns

- ProcedureParameters

- Visualizzazioni

### <a name="tables-and-views"></a>Tables e Views

|ColumnName|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|TABLE_TYPE|String|
|REMARKS|String|

### <a name="columns"></a>Colonne

|ColumnName|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|String|
|TABLE_OWNER|String|
|TABLE_NAME|String|
|COLUMN_NAME|String|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedure

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|REMARKS|String|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|String|
|PROCEDURE_OWNER|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

### <a name="procedureparameters"></a>ProcedureParameters

|ColumnName|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|String|
|PROCEDURE_SCHEM|String|
|PROCEDURE_NAME|String|
|COLUMN_NAME|String|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|String|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|String|
|COLUMN_DEF|String|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|String|

## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](ado-net-overview.md)
