---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 58bf07b0429ca2435b5aae3683ef69951a10003e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185183"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement
PeerTransportBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
