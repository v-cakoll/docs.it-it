---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 09bfaa3ab4f2aceb3e80644953a87686fca9830c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
