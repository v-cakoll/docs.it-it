---
title: PeerSecuritySettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48a9cc5a7a05b47a5589d1bf9a730184fb7f0543
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
