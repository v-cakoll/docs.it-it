---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3995b517b27a5565f7fcb9c11da27c9e1bb40887
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="channelpoolsettings"></a>ChannelPoolSettings
ChannelPoolSettings  
  
## <a name="syntax"></a>Sintassi  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ChannelPoolSettings non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ChannelPoolSettings dispone delle proprietà seguenti:  
  
### <a name="idletimeout"></a>IdleTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Periodo massimo di inattività della connessione prima che venga interrotta.  
  
### <a name="leasetimeout"></a>LeaseTimeout  
 Tipo di dati: DateTime  
  
 Tipo di accesso: sola lettura  
  
 Limite massimo di tempo per il completamento dell'operazione di lease prima del timeout.  
  
### <a name="maxoutboundchannelsperendpoint"></a>MaxOutboundChannelsPerEndpoint  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di canali in uscita per ogni endpoint.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
