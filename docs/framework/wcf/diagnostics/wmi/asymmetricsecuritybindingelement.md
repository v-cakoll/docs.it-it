---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075057"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement
AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe AsymmetricSecurityBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe AsymmetricSecurityBindingElement dispone delle proprietà seguenti:  
  
### <a name="messageprotectionorder"></a>MessageProtectionOrder  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Ordine di crittografia e firma dei messaggi per questa associazione.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Indica se l'associazione richiede la conferma della firma.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
