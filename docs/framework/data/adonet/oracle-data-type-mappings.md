---
title: Mappings1 tipo di dati Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: 9057a19abb1abc22924b5542f06e21a57a36ed94
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856335"
---
# <a name="oracle-data-type-mappings"></a>Mapping dei tipi di dati Oracle
Nella tabella seguente sono elencati i tipi di dati Oracle e i relativi mapping al tipo <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Tipo di dati Oracle|Tipo di dati .NET Framework restituito da OracleDataReader.GetValue|Tipo di dati OracleClient restituito da OracleDataReader.GetOracleValue|Note|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il **numero** tipo di dati ed è progettato in modo che le <xref:System.Data.OracleClient.OracleDataReader> restituisce un **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un valore a virgola mobile. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**NUMERO INTERO**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il **Number (38)** tipo di dati ed è progettato in modo che le <xref:System.Data.OracleClient.OracleDataReader> restituisce un **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un valore intero. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECONDO**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMERO**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** tipo di dati non è supportato per il <xref:System.Data.OracleClient.OracleDataReader> oggetto.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP CON FUSO ORARIO LOCALE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP CON FUSO ORARIO**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**INTERO SENZA SEGNO**|**Numero**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il **Number (38)** tipo di dati ed è progettato in modo che le <xref:System.Data.OracleClient.OracleDataReader> restituisce un **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un valore intero senza segno. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 Nella tabella seguente sono elencati i tipi di dati Oracle e i tipi di dati .NET Framework (**System.Data.DbType** e <xref:System.Data.OracleClient.OracleType>) da usare durante l'associazione come parametri.  
  
|Tipo di dati Oracle|Enumerazione DbType da associare come parametro|Enumerazione OracleType da associare come parametro|Note|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle consente solo l'associazione di un **BFILE** come una **BFILE** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si prova a eseguire l'associazione non -**BFILE** di valore, come **byte[].{0** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**BLOB**|Oracle consente solo l'associazione di un **BLOB** come una **BLOB** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si prova a eseguire l'associazione non -**BLOB** di valore, come **byte[].{0** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Nell'oggetto CLOB**|Oracle consente solo l'associazione di un **CLOB** come una **CLOB** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si prova a eseguire l'associazione non -**CLOB** di valore, come **System. String** o <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**L'accesso Single, Double, Decimal**|**Float, Double, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Determina la **System.Data.DBType** e <xref:System.Data.OracleClient.OracleType>.|  
|**NUMERO INTERO**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Determina la **System.Data.DBType** e <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**INTERVAL DAY TO SECONDO**|**Oggetto**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle consente solo l'associazione di un **NCLOB** come una **NCLOB** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si prova a eseguire l'associazione non -**NCLOB** di valore, come **System. String** o <xref:System.Data.OracleClient.OracleString>.|  
|**NUMERO**|**VarNumeric**|**Numero**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Binary**|**Non elaborati**||  
|**REF CURSOR**||**cursore**|Per altre informazioni, vedere [REF CURSOR Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**TIMESTAMP CON FUSO ORARIO LOCALE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**TIMESTAMP CON FUSO ORARIO**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**INTERO SENZA SEGNO**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Determina la **System.Data.DBType** e <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Il **InputOutput**, **Output**, e **ReturnValue** **ParameterDirection** i valori utilizzati dal <xref:System.Data.OracleClient.OracleParameter.Value%2A> proprietà il <xref:System.Data.OracleClient.OracleParameter> oggetto sono tipi di dati .NET Framework, a meno che il valore di input è un tipo di dati Oracle (ad esempio <xref:System.Data.OracleClient.OracleNumber> o <xref:System.Data.OracleClient.OracleString>). Ciò non si applica a **REF CURSOR**, **BFILE**, o **LOB** i tipi di dati.  
  
## <a name="see-also"></a>Vedere anche  
 [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
