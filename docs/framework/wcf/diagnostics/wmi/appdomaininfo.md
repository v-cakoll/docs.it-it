---
title: AppDomainInfo
ms.date: 03/30/2017
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
ms.openlocfilehash: 0b7f8aadbd9a9dfcdd33fc65be3a5a41ea95f5be
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170224"
---
# <a name="appdomaininfo"></a>AppDomainInfo
Informazioni sul dominio applicazione  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe AppDomainInfo non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe AppDomainInfo presenta le proprietà seguenti:  
  
### <a name="appdomainid"></a>AppDomainId  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 ID del dominio applicazione.  
  
### <a name="isdefault"></a>IsDefault  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Indica se il dominio applicazione è quello predefinito.  
  
### <a name="logmalformedmessages"></a>LogMalformedMessages  
 Tipo di dati: booleano  
  
 Tipo di accesso: in lettura/scrittura  
  
 Valore che specifica se i messaggi in formato non valido vengono registrati.  
  
### <a name="logmessagesatservicelevel"></a>LogMessagesAtServiceLevel  
 Tipo di dati: booleano  
  
 Tipo di accesso: in lettura/scrittura  
  
 Valore che specifica se i messaggi vengono registrati a livello di servizio (prima della crittografia e delle trasformazioni relative al trasporto).  
  
### <a name="logmessagesattransportlevel"></a>LogMessagesAtTransportLevel  
 Tipo di dati: booleano  
  
 Tipo di accesso: in lettura/scrittura  
  
 Valore che specifica se i messaggi vengono registrati a livello di trasporto.  
  
### <a name="messageloggingtracelisteners"></a>MessageLoggingTraceListeners  
 Tipo di dati: matrice di TraceListener  
  
 Tipo di accesso: sola lettura  
  
 Raccolta di listener di traccia in attesa sull'origine di traccia System.Wmi.MessageLogging.  
  
### <a name="name"></a>nome  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome del dominio applicazione.  
  
### <a name="performancecounters"></a>PerformanceCounters  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Ambito dei contatori delle prestazioni attivi nel dominio applicazione.  
  
### <a name="processid"></a>ProcessId  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 ID del processo.  
  
### <a name="serviceconfigpath"></a>ServiceConfigPath  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Percorso della configurazione del servizio.  
  
### <a name="tracelevel"></a>TraceLevel  
 Tipo di dati: stringa  
  
 Tipo di accesso: in lettura/scrittura  
  
 Livello di traccia dell'origine di traccia di System.Wmi.  
  
### <a name="servicemodeltracelisteners"></a>ServiceModelTraceListeners  
 Tipo di dati: matrice di TraceListener  
  
 Tipo di accesso: sola lettura  
  
 Raccolta di listener in attesa sull'origine di traccia System.ServiceModel.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|
