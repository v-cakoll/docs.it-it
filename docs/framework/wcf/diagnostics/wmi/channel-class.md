---
title: Classe Channel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a>Classe Channel
Canale  
  
## <a name="syntax"></a>Sintassi  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe Channel non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe Channel presenta le proprietà seguenti.  
  
### <a name="localaddress"></a>LocalAddress  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Endpoint locale del canale.  
  
### <a name="ref"></a>ref  
 Tipo di dati: endpoint  
  
 Tipo di accesso: sola lettura  
  
 Riferimento all'endpoint a cui si connette il canale.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Indirizzo remoto associato al canale.  
  
### <a name="sessionid"></a>SessionId  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 ID della sessione corrente, se presente.  
  
### <a name="type"></a>Tipo  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Tipo del canale.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.ChannelBase>
