---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 92aca4c790607de91314aacf6414d0dfacea9a9f
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50045730"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings
PeerSecuritySettings  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
