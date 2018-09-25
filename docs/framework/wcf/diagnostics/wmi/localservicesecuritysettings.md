---
title: LocalServiceSecuritySettings
ms.date: 03/30/2017
ms.assetid: 490aa0e5-5242-4f8d-b505-5ec6287633b4
author: BrucePerlerMS
ms.openlocfilehash: c79eb11fcc1973a3ef25a78afb8b141443d865c3
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47156948"
---
# <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings
LocalServiceSecuritySettings  
  
## <a name="syntax"></a>Sintassi  
  
```  
class LocalServiceSecuritySettings  
{  
  boolean DetectReplays;  
  datetime InactivityTimeout;  
  datetime IssuedCookieLifetime;  
  sint32 MaxCachedCookies;  
  datetime MaxClockSkew;  
  sint32 MaxPendingSessions;  
  sint32 MaxStatefulNegotiations;  
  datetime NegotiationTimeout;  
  boolean ReconnectTransportOnFailure;  
  sint32 ReplayCacheSize;  
  datetime ReplayWindow;  
  datetime SessionKeyRenewalInterval;  
  datetime SessionKeyRolloverInterval;  
  datetime TimestampValidityDuration;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe LocalServiceSecuritySettings non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe LocalServiceSecuritySettings dispone delle proprietà seguenti:  
  
### <a name="detectreplays"></a>DetectReplays  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore booleano che specifica se gli attacchi di tipo replay contro il canale vengono rilevati e gestiti automaticamente.  
  
### <a name="inactivitytimeout"></a>InactivityTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di sessioni di sicurezza in sospeso supportate dal servizio.  
  
### <a name="issuedcookielifetime"></a>IssuedCookieLifetime  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 TimeSpan che specifica la durata per tutti i nuovi cookie di sicurezza.  
  
### <a name="maxcachedcookies"></a>MaxCachedCookies  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di cookie che possono essere memorizzati nella cache.  
  
### <a name="maxclockskew"></a>MaxClockSkew  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 TimeSpan che specifica la differenza massima di tempo tra gli orologi di sistema delle due parti che stanno comunicando.  
  
### <a name="maxpendingsessions"></a>MaxPendingSessions  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di connessioni in sospeso nel servizio.  
  
### <a name="maxstatefulnegotiations"></a>MaxStatefulNegotiations  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero di negoziazioni di sicurezza che possono essere attive contemporaneamente.  
  
### <a name="negotiationtimeout"></a>NegotiationTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 TimeSpan che specifica la durata massima della fase di negoziazione della protezione tra server e client.  
  
### <a name="reconnecttransportonfailure"></a>ReconnectTransportOnFailure  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore booleano che specifica se le connessioni che utilizzano WS-Reliable Messaging tentano la riconnessione in caso di errori del trasporto.  
  
### <a name="replaycachesize"></a>ReplayCacheSize  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero di parametri nonce utilizzato per il rilevamento degli attacchi di tipo replay.  
  
### <a name="replaywindow"></a>ReplayWindow  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 TimeSpan che specifica la durata di validità dei singoli nonce dei messaggi.  
  
### <a name="sessionkeyrenewalinterval"></a>SessionKeyRenewalInterval  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Timespan che specifica l'intervallo di tempo dopo il quale l'iniziatore rinnova la chiave per la sessione di sicurezza.  
  
### <a name="sessionkeyrolloverinterval"></a>SessionKeyRolloverInterval  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 TimeSpan che specifica l'intervallo di tempo per il quale la chiave della sessione precedente è valida nei messaggi in arrivo durante un rinnovo della chiave.  
  
### <a name="timestampvalidityduration"></a>TimestampValidityDuration  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 TimeSpan che specifica il periodo di validità di un timestamp.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
