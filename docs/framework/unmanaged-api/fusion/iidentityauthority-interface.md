---
title: Interfaccia IIdentityAuthority
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 692ac4ef4fe8ea64c6a63dc2f02cc04244a842c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432528"
---
# <a name="iidentityauthority-interface"></a>Interfaccia IIdentityAuthority
Gestisce le chiavi di identità per gli oggetti di codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IIdentityAuthority::AreDefinitionsEqual`|Ottiene un valore che indica se le due [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) istanze sono uguali.|  
|`IIdentityAuthority::AreReferencesEqual`|Ottiene un valore che indica se le due [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) istanze sono uguali.|  
|`IIdentityAuthority::AreTextualDefinitionsEqual`|Ottiene un valore che indica se le due rappresentazioni identità definizione di stringa specificato sono uguali.|  
|`IIdentityAuthority::AreTextualReferencesEqual`|Ottiene un valore che indica se le due rappresentazioni identità di riferimento di stringa specificato sono uguali.|  
|`IIdentityAuthority::CreateDefinition`|Ottiene un puntatore a un nuovo `IDefinitionIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.|  
|`IIdentityAuthority::CreateReference`|Ottiene un puntatore a un nuovo `IReferenceIdentity` istanza che rappresenta l'oggetto di codice nell'ambito corrente.|  
|`IIdentityAuthority::DefinitionToText`|Ottiene una stringa formattata di versione dell'oggetto specificato `IDefinitionIdentity`.|  
|`IIdentityAuthority::DefinitionToTextBuffer`|Riempie i buffer di caratteri "wide" specificato con una versione stringa dell'oggetto specificato `IDefinitionIdentity`.|  
|`IIdentityAuthority::DoesDefinitionMatchReference`|Ottiene un valore che indica se l'oggetto specificato `IDefinitionIdentity` e `IReferenceIdentity` istanze fanno riferimento allo stesso oggetto di codice.|  
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|Ottiene un valore che indica se le stringhe specificate fanno riferimento allo stesso oggetto di codice.|  
|`IIdentityAuthority::GenerateDefinitionKey`|Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IDefinitionIdentity`.|  
|`IIdentityAuthority::GenerateReferenceKey`|Ottiene un puntatore a una chiave di stringa appena creata per l'oggetto specificato `IReferenceIdentity`.|  
|`IIdentityAuthority::HashDefinition`|Ottiene un valore hash per l'oggetto specificato `IDefinitionIdentity`.|  
|`IIdentityAuthority::HashReference`|Ottiene un valore hash per l'oggetto specificato `IreferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToText`|Ottiene una stringa formattata di versione dell'oggetto specificato `IReferenceIdentity`.|  
|`IIdentityAuthority::ReferenceToTextBuffer`|Riempie i buffer di caratteri "wide" specificato con una versione stringa dell'oggetto specificato `IReferenceIdentity`.|  
|`IIdentityAuthority::TextToDefinition`|Ottiene un puntatore a interfaccia a un `IDefinitionIdentity` stringa formattata di istanza generato dall'oggetto specificato.|  
|`IIdentityAuthority::TextToReference`|Ottiene un puntatore a interfaccia a un `IReferenceIdentity` stringa formattata di istanza generato dall'oggetto specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
