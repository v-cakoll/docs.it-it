---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47de8c2449c46b12b8d10ac2a5269a18d1454f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="onewaybindingelement"></a>OneWayBindingElement
OneWayBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe OneWayBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe OneWayBindingElement dispone delle proprietà seguenti:  
  
### <a name="channelpoolsettings"></a>ChannelPoolSettings  
 Tipo di dati: ChannelPoolSettings  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni del pool di canali.  
  
### <a name="maxacceptedchannels"></a>MaxAcceptedChannels  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di canali accettati.  
  
### <a name="packetroutable"></a>PacketRoutable  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore che indica se il pacchetto è instradabile.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
