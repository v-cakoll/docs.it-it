---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7fc720f4f0be25a0cec25d979942af8472efa4ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="symmetricsecuritybindingelement"></a>SymmetricSecurityBindingElement
SymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```  
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe SymmetricSecurityBindingElement non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe SymmetricSecurityBindingElement dispone delle proprietà seguenti:  
  
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
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
