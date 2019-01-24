---
title: NamedPipeConnectionPoolSettings
ms.date: 03/30/2017
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
ms.openlocfilehash: 3dddfa878e3cb5bd89fb76009d0dba530debb297
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725077"
---
# <a name="namedpipeconnectionpoolsettings"></a>NamedPipeConnectionPoolSettings
NamedPipeConnectionPoolSettings  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class NamedPipeConnectionPoolSettings  
{  
  string GroupName;  
  datetime IdleTimeout;  
  sint32 MaxOutboundConnectionsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe NamedPipeConnectionPoolSettings non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe NamedPipeConnectionPoolSettings dispone delle proprietà seguenti:  
  
### <a name="groupname"></a>GroupName  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: Sola lettura  
  
 Periodo massimo di inattività della connessione prima che venga interrotta.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di connessioni in uscita per ogni endpoint sul client.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
