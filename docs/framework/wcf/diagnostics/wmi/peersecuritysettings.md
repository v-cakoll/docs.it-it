---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
author: BrucePerlerMS
ms.openlocfilehash: c74ee82d7aa3a23f0ee6a69185ad45857c31bb0b
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47087879"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>Sintassi  
  
```  
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe PeerSecuritySettings non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe PeerSecuritySettings ha le proprietà seguenti:  
  
### <a name="mode"></a>Modalità  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Se un endpoint configurato con l'associazione utilizza meccanismi di sicurezza a livello di messaggio o di trasporto.  
  
### <a name="transport"></a>Trasporto  
 Tipo di dati: PeerTransportSecuritySettings  
  
 Tipo di accesso: sola lettura  
  
 Impostazioni di sicurezza del trasporto.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.PeerSecuritySettings>
