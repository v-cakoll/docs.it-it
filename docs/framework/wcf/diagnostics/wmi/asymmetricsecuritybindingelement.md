---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196047"
---
# <a name="asymmetricsecuritybindingelement"></a>AsymmetricSecurityBindingElement
AsymmetricSecurityBindingElement  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
  
 Tipo di accesso: Sola lettura  
  
 Ordine di crittografia e firma dei messaggi per questa associazione.  
  
### <a name="requiresignatureconfirmation"></a>RequireSignatureConfirmation  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Indica se l'associazione richiede la conferma della firma.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
