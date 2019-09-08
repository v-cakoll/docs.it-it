---
title: Mapping dei tipi di dati Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: be478741069e9edd406d73c0b75d5960b9909896
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783426"
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
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il tipo di dati **Number** ed è progettato in modo <xref:System.Data.OracleClient.OracleDataReader> che restituisce un oggetto **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> invece di un valore a virgola mobile. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il tipo di dati **Number (38)** ed è progettato in modo <xref:System.Data.OracleClient.OracleDataReader> che restituisca un valore **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un valore integer. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**INTERVALLO DA ANNO A MESE**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVALLO DA GIORNO A SECONDO**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMERO**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Il tipo di dati **ref CURSOR** di Oracle non è supportato <xref:System.Data.OracleClient.OracleDataReader> dall'oggetto.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP CON FUSO ORARIO LOCALE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP CON FUSO ORARIO**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**INTERO SENZA SEGNO**|**Numero**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il tipo di dati **Number (38)** ed è progettato in modo <xref:System.Data.OracleClient.OracleDataReader> che restituisca un valore **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un Unsigned Integer. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 Nella tabella seguente sono elencati i tipi di dati Oracle e i tipi di dati .NET Framework (**System. Data. DbType** e <xref:System.Data.OracleClient.OracleType>) da usare per l'associazione come parametri.  
  
|Tipo di dati Oracle|Enumerazione DbType da associare come parametro|Enumerazione OracleType da associare come parametro|Note|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle consente solo l'associazione di un **BFILE** come parametro **BFILE** . .NET provider di dati per Oracle non ne crea automaticamente uno se si tenta di associare un valore non**BFILE** , ad esempio **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**BLOB**|Oracle consente solo l'associazione di un **BLOB** come parametro **BLOB** . .NET provider di dati per Oracle non ne crea automaticamente uno se si tenta di associare un valore non**BLOB** , ad esempio **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle consente solo l'associazione di un oggetto **CLOB** come parametro **CLOB** . .NET provider di dati per Oracle non ne crea automaticamente uno se si tenta di associare un valore non**CLOB** , ad esempio **System. String** o <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Singola, doppia, decimale**|**Float, Double, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>determina **System. Data. DbType** e <xref:System.Data.OracleClient.OracleType>.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>determina **System. Data. DbType** e <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVALLO DA ANNO A MESE**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**INTERVALLO DA GIORNO A SECONDO**|**Oggetto**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle consente solo l'associazione di un oggetto **NCLOB** come parametro **NCLOB** . .NET provider di dati per Oracle non ne crea automaticamente uno se si tenta di associare un valore diverso da**NCLOB** , ad esempio **System. String** o <xref:System.Data.OracleClient.OracleString>.|  
|**NUMERO**|**VarNumeric**|**Numero**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Binary**|**Non elaborati**||  
|**REF CURSOR**||**Cursore**|Per ulteriori informazioni, vedere [Ref cursors Oracle](oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**TIMESTAMP CON FUSO ORARIO LOCALE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**TIMESTAMP CON FUSO ORARIO**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**INTERO SENZA SEGNO**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, UInt32, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>determina **System. Data. DbType** e <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 <xref:System.Data.OracleClient.OracleParameter.Value%2A> I **valori InputOutput**, **output**e **returnValue** **ParameterDirection** utilizzati dalla proprietà dell' oggettosono.NETFrameworktipididati,amenocheilvalorediinputnonsiauntipodidatiOracle(per<xref:System.Data.OracleClient.OracleParameter> esempio, <xref:System.Data.OracleClient.OracleNumber> o <xref:System.Data.OracleClient.OracleString>). Questa operazione non si applica ai tipi di dati **ref CURSOR**, **BFILE**o **LOB** .  
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](oracle-and-adonet.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
