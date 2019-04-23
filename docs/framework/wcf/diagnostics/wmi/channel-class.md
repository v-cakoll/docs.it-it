---
title: Classe Channel
ms.date: 03/30/2017
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
ms.openlocfilehash: f60a3946617b0994db1ba9e9ddf43be863be81f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767448"
---
# <a name="channel-class"></a>Classe Channel
Canale  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
  
 Tipo di accesso: Sola lettura  
  
 Endpoint locale del canale.  
  
### <a name="ref"></a>ref  
 Tipo di dati: Endpoint  
  
 Tipo di accesso: Sola lettura  
  
 Riferimento all'endpoint a cui si connette il canale.  
  
### <a name="remoteaddress"></a>RemoteAddress  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Indirizzo remoto associato al canale.  
  
### <a name="sessionid"></a>SessionId  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 ID della sessione corrente, se presente.  
  
### <a name="type"></a>Tipo  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Tipo del canale.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.ChannelBase>
