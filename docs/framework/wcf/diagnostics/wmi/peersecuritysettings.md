---
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: 1c33e1ce710fea3b1698a6dab47a199e40388f5a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963007"
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
  
 Tipo di accesso: Sola lettura  
  
 Se un endpoint configurato con l'associazione utilizza meccanismi di sicurezza a livello di messaggio o di trasporto.  
  
### <a name="transport"></a>Trasporto  
 Tipo di dati: PeerTransportSecuritySettings  
  
 Tipo di accesso: Sola lettura  
  
 Impostazioni di sicurezza del trasporto.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.PeerSecuritySettings>
