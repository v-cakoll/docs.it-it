---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48364c2bcfa50476ac5f9f00f87c17f97dc14017
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement
PeerTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe PeerTransportBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe PeerTransportBindingElement dispone delle proprietà seguenti:  
  
### <a name="listenipaddress"></a>ListenIPAddress  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Indirizzo IP su cui il nodo del peer è in attesa di messaggi.  
  
### <a name="port"></a>Porta  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Porta di interfaccia di rete su cui l'associazione elabora messaggi del canale del peer.  
  
### <a name="security"></a>Sicurezza  
 Tipo di dati: PeerSecuritySettings  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni di sicurezza del trasporto peer.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
