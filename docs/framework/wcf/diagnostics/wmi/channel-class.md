---
title: Classe Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: 4b7c66560c0c136a258c527d8a681d491eb50aae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485801"
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
