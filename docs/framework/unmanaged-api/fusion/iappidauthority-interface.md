---
title: Interfaccia IAppIdAuthority
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206655"
---
# <a name="iappidauthority-interface"></a>Interfaccia IAppIdAuthority
Fornisce metodi che generano e confrontare le chiavi per le identità dell'applicazione e i riferimenti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Ottiene un valore che indica se le due [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) istanze sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreReferencesEqual`|Ottiene un valore che indica se le due [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) istanze sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Ottiene un valore che indica se le due definizioni di stringa specificato sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Ottiene un valore che indica se i due riferimenti di stringa specificato sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::CreateDefinition`|Ottiene un puntatore a interfaccia a un nuovo `IDefinitionAppId` istanza che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::CreateReference`|Ottiene un puntatore di interfaccia di un nuovo `IReferenceAppId` che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::DefinitionToText`|Ottiene una versione stringa dell'oggetto specificato `IDefinitionAppId`, usando i valori di flag specificato.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Ottiene un valore che indica se l'oggetto specificato `IDefinitionAppId` e `IReferenceAppId` rappresentano lo stesso assembly.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Ottiene un valore che indica se la stringa di definizione specificato e una stringa di riferimento rappresentano lo stesso assembly.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IDefinitionAppId` istanza.|  
|`IAppIdAuthority::GenerateReferenceKey`|Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IReferenceAppId` istanza.|  
|`IAppIdAuthority::HashDefinition`|Ottiene una chiave hash per l'oggetto specificato `IDefinitionAppId` istanza.|  
|`IAppIdAuthority::HashReference`|Ottiene una chiave hash per l'oggetto specificato `IReferenceAppId` istanza.|  
|`IAppIdAuthority::ReferenceToText`|Ottiene una versione stringa dell'oggetto specificato `IReferenceAppId`, usando i valori di flag specificato.|  
|`IAppIdAuthority::TextToDefinition`|Ottiene un puntatore a interfaccia per un `IDefinitionAppId` istanza che rappresenta l'assembly fa riferimento la chiave della stringa specificata.|  
|`IAppIdAuthority::TextToReference`|Ottiene un puntatore a interfaccia per un `IReferenceAppId` istanza che rappresenta l'assembly fa riferimento la chiave della stringa specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
