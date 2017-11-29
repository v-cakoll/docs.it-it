---
title: AppDomainInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97818cf1fc6fa1c59b8b0eeaab69a73b21360151
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="appdomaininfo"></a>AppDomainInfo
Informazioni sul dominio applicazione  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
### <a name="name"></a>Nome  
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
