---
title: NamedPipeConnectionPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079bccb8-54b5-4436-a43d-5567763f72ce
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 601ccd5589da759606365570538e0df902e4fbe2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="namedpipeconnectionpoolsettings"></a>NamedPipeConnectionPoolSettings
NamedPipeConnectionPoolSettings  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 Tipo di accesso: sola lettura  
  
 Nome del gruppo del pool di connessioni utilizzato dall'elemento di associazione.  
  
### <a name="idletimeout"></a>IdleTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Periodo massimo di inattività della connessione prima che venga interrotta.  
  
### <a name="maxoutboundconnectionsperendpoint"></a>MaxOutboundConnectionsPerEndpoint  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di connessioni in uscita per ogni endpoint sul client.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
