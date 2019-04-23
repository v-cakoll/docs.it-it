---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: ba9031dad96f12c7c48b03f1da4af1b3adc6dd4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980435"
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
  
 Tipo di accesso: Sola lettura  
  
 Indirizzo IP su cui il nodo del peer è in attesa di messaggi.  
  
### <a name="port"></a>Porta  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Porta di interfaccia di rete su cui l'associazione elabora messaggi del canale del peer.  
  
### <a name="security"></a>Sicurezza  
 Tipo di dati: PeerSecuritySettings  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni di sicurezza del trasporto peer.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
