---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: f9e1c043579f632f16a7cf36bf34c2467a743e47
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50189563"
---
# <a name="tcpconnectionpoolsettings"></a>TcpConnectionPoolSettings
TcpConnectionPoolSettings  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class TcpConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe TcpConnectionPoolSettings non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe TcpConnectionPoolSettings dispone delle proprietà seguenti:  
  
### <a name="groupname"></a>GroupName  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Periodo massimo di inattività della connessione prima che venga interrotta.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di connessioni in uscita per ogni endpoint.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
