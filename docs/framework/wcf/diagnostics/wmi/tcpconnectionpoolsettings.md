---
title: TcpConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 19acfba3-c057-4dbc-bac7-8674d7844d83
ms.openlocfilehash: 4e89dbe35a5232c612555b273c3d771aad42aeb0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584805"
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
  
 Tipo di accesso: Sola lettura  
  
 Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Periodo massimo di inattività della connessione prima che venga interrotta.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di connessioni in uscita per ogni endpoint.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
