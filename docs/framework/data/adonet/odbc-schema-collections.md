---
title: Raccolte di schemi ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772047"
---
# <a name="odbc-schema-collections"></a>Raccolte di schemi ODBC

Contenuto della sezione viene descritto il supporto delle raccolte di schemi per driver ODBC per Microsoft SQL Server, Oracle e Microsoft Jet.

## <a name="microsoft-sql-server-odbc-driver"></a>Driver ODBC di Microsoft SQL Server

Il Driver ODBC di Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:

- Tabelle

- Indexes

- Colonne

- Procedure

- ProcedureColumns

- ProcedureParameters

- Visualizzazioni

### <a name="tables-and-views"></a>Tables e Views

|Nome colonna|Tipo di dati|
|----------------|--------------|
|TABLE_CAT|Stringa|
|TABLE_SCHEM|Stringa|
|TABLE_NAME|Stringa|
|TABLE_TYPE|Stringa|
|REMARKS|Stringa|

### <a name="indexes"></a>Indexes

|Nome colonna|Tipo di dati|
|----------------|--------------|
|TABLE_CAT|Stringa|
|TABLE_SCHEM|Stringa|
|TABLE_NAME|Stringa|
|NON_UNIQUE|Int16|
|INDEX_QUALIFIER|Stringa|
|INDEX_NAME|Stringa|
|TYPE|Int16|
|ORDINAL_POSITION|Int16|
|COLUMN_NAME|Stringa|
|ASC_OR_DESC|Stringa|
|CARDINALITY|Int32|
|PAGES|Int32|
|FILTER_CONDITION|Stringa|
|SS_TYPE_SCHEMA|Stringa|
|SS_DATA_TYPE|Byte|

### <a name="columns"></a>Colonne

|Nome colonna|Tipo di dati|
|----------------|--------------|
|TABLE_CAT|Stringa|
|TABLE_SCHEM|Stringa|
|TABLE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
|COLUMN_DEF|Stringa|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Stringa|
|SS_TYPE_CATALOG|Stringa|
|SS_TYPE_SCHEMA|Stringa|
|SS_DATA_TYPE|Byte|

### <a name="procedures"></a>Procedure

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|Stringa|
|PROCEDURE_SCHEM|Stringa|
|PROCEDURE_NAME|Stringa|
|NUM_INPUT_PARAMS|Int32|
|NUM_OUTPUT_PARAMS|Int32|
|NUM_RESULT_SETS|Int32|
|REMARKS|Stringa|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|Stringa|
|PROCEDURE_SCHEM|Stringa|
|PROCEDURE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
|COLUMN_DEF|Stringa|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Stringa|
|SS_TYPE_CATALOG|Stringa|
|SS_TYPE_SCHEMA|Stringa|
|SS_DATA_TYPE|Byte|

### <a name="procedureparameters"></a>ProcedureParameters

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|Stringa|
|PROCEDURE_SCHEM|Stringa|
|PROCEDURE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
|COLUMN_DEF|Stringa|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Stringa|
|SS_TYPE_CATALOG|Stringa|
|SS_TYPE_SCHEMA|Stringa|
|SS_DATA_TYPE|Byte|

## <a name="microsoft-oracle-odbc-driver"></a>Driver Microsoft ODBC per Oracle

Il Driver ODBC di Microsoft SQL Server Oracle supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:

- Tabelle

- Colonne

- Procedure

- ProcedureColumns

- ProcedureParameters

- Visualizzazioni

- Indexes

### <a name="tables-and-views"></a>Tables e Views

|Nome colonna|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|Stringa|
|TABLE_OWNER|Stringa|
|TABLE_NAME|Stringa|
|TABLE_TYPE|Stringa|
|REMARKS|Stringa|

### <a name="columns"></a>Colonne

|Nome colonna|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|Stringa|
|TABLE_OWNER|Stringa|
|TABLE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedure

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Stringa|
|PROCEDURE_OWNER|Stringa|
|PROCEDURE_NAME|Stringa|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|REMARKS|Stringa|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Stringa|
|PROCEDURE_OWNER|Stringa|
|PROCEDURE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
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

|Nome colonna|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|Stringa|
|TABLE_OWNER|Stringa|
|TABLE_NAME|Stringa|
|TABLE_TYPE|Stringa|
|REMARKS|Stringa|

### <a name="columns"></a>Colonne

|Nome colonna|Tipo di dati|
|----------------|--------------|
|TABLE_QUALIFIER|Stringa|
|TABLE_OWNER|Stringa|
|TABLE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
|ORDINAL_POSITION|Int32|

### <a name="procedures"></a>Procedure

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Stringa|
|PROCEDURE_OWNER|Stringa|
|PROCEDURE_NAME|Stringa|
|NUM_INPUT_PARAMS|Int16|
|NUM_OUTPUT_PARAMS|Int16|
|NUM_RESULT_SETS|Int16|
|REMARKS|Stringa|
|PROCEDURE_TYPE|Int16|

### <a name="procedurecolumns"></a>ProcedureColumns

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_QUALIFIER|Stringa|
|PROCEDURE_OWNER|Stringa|
|PROCEDURE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|PRECISION|Int32|
|LENGTH|Int32|
|SCALE|Int16|
|RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
|OVERLOAD|Int32|
|ORDINAL_POSITION|Int32|

### <a name="procedureparameters"></a>ProcedureParameters

|Nome colonna|Tipo di dati|
|----------------|--------------|
|PROCEDURE_CAT|Stringa|
|PROCEDURE_SCHEM|Stringa|
|PROCEDURE_NAME|Stringa|
|COLUMN_NAME|Stringa|
|COLUMN_TYPE|Int16|
|DATA_TYPE|Int16|
|TYPE_NAME|Stringa|
|COLUMN_SIZE|Int32|
|BUFFER_LENGTH|Int32|
|DECIMAL_DIGITS|Int16|
|NUM_PREC_RADIX|Int16|
|NULLABLE|Int16|
|REMARKS|Stringa|
|COLUMN_DEF|Stringa|
|SQL_DATA_TYPE|Int16|
|SQL_DATETIME_SUB|Int16|
|CHAR_OCTET_LENGTH|Int32|
|ORDINAL_POSITION|Int32|
|IS_NULLABLE|Stringa|

## <a name="see-also"></a>Vedere anche

- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
