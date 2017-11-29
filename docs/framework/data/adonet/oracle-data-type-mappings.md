---
title: Mappings1 tipo di dati Oracle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 746013a11d10162a78116ff41d0b09d942f7651b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-data-type-mappings"></a>Mapping dei tipi di dati Oracle
Nella tabella seguente sono elencati i tipi di dati Oracle e i relativi mapping al tipo <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Tipo di dati Oracle|Tipo di dati .NET Framework restituito da OracleDataReader.GetValue|Tipo di dati OracleClient restituito da OracleDataReader.GetOracleValue|Note|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**OGGETTO CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il **numero** tipo di dati ed è progettato in modo che il <xref:System.Data.OracleClient.OracleDataReader> restituisce un **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un valore a virgola mobile. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**VALORE INTEGER**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il **Number (38)** tipo di dati ed è progettato in modo che il <xref:System.Data.OracleClient.OracleDataReader> restituisce un **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un valore intero. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**INTERVALLO DI ANNO E MESE**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**GIORNO DI INTERVALLO AL SECONDO**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMERO**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NON ELABORATO**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** tipo di dati non è supportato per il <xref:System.Data.OracleClient.OracleDataReader> oggetto.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP CON FUSO ORARIO LOCALE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP CON FUSO ORARIO**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**INTERO SENZA SEGNO**|**Numero**|<xref:System.Data.OracleClient.OracleNumber>|Questo tipo di dati è un alias per il **Number (38)** tipo di dati ed è progettato in modo che il <xref:System.Data.OracleClient.OracleDataReader> restituisce un **System. Decimal** o <xref:System.Data.OracleClient.OracleNumber> anziché un valore intero senza segno. L'utilizzo del tipo di dati .NET Framework può provocare un overflow.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 Nella tabella seguente sono elencati i tipi di dati Oracle e i tipi di dati .NET Framework (**DbType** e <xref:System.Data.OracleClient.OracleType>) da utilizzare durante l'associazione come parametri.  
  
|Tipo di dati Oracle|Enumerazione DbType da associare come parametro|Enumerazione OracleType da associare come parametro|Note|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle consente solo di associare un **BFILE** come un **BFILE** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si tenta di associare un non -**BFILE** valore, ad esempio **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**BLOB**|Oracle consente solo di associare un **BLOB** come un **BLOB** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si tenta di associare un non -**BLOB** valore, ad esempio **byte []** o <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**OGGETTO CLOB**||**Oggetto CLOB**|Oracle consente solo di associare un **CLOB** come un **CLOB** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si tenta di associare un non -**CLOB** valore, ad esempio **System. String** o <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Determina il **DbType** e <xref:System.Data.OracleClient.OracleType>.|  
|**VALORE INTEGER**|**SByte, Int16, Int32, Int64, decimale**|**SByte, Int16, Int32, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Determina il **DbType** e <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVALLO DI ANNO E MESE**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**GIORNO DI INTERVALLO AL SECONDO**|**Oggetto**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle consente solo di associare un **NCLOB** come un **NCLOB** parametro. Il Provider di dati .NET per Oracle non ne crea automaticamente uno se si tenta di associare un non -**NCLOB** valore, ad esempio **System. String** o <xref:System.Data.OracleClient.OracleString>.|  
|**NUMERO**|**VarNumeric**|**Numero**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**NON ELABORATO**|**Binary**|**Non elaborato**||  
|**REF CURSOR**||**Cursore**|Per ulteriori informazioni, vedere [REF CURSOR Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**ROWID**||  
|**TIMESTAMP**|**DateTime**|**Timestamp**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**TIMESTAMP CON FUSO ORARIO LOCALE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**TIMESTAMP CON FUSO ORARIO**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> è disponibile solo se si usa il software Oracle 9i sia per il client che per il server.|  
|**INTERO SENZA SEGNO**|**Byte, UInt16, UInt32, UInt64, decimale**|**Byte, UInt16, Uint32, numero**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Determina il **DbType** e <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Il **InputOutput**, **Output**, e **ReturnValue** **ParameterDirection** i valori utilizzati dal <xref:System.Data.OracleClient.OracleParameter.Value%2A> proprietà del <xref:System.Data.OracleClient.OracleParameter> oggetto sono tipi di dati .NET Framework, a meno che il valore di input è un tipo di dati Oracle (ad esempio, <xref:System.Data.OracleClient.OracleNumber> o <xref:System.Data.OracleClient.OracleString>). Non si applica a **REF CURSOR**, **BFILE**, o **LOB** tipi di dati.  
  
## <a name="see-also"></a>Vedere anche  
 [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
