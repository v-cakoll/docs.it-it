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
ms.openlocfilehash: 91ab2f71e7fb74f8e0e517b566d46d61c316ebe2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796833"
---
# <a name="iappidauthority-interface"></a>Interfaccia IAppIdAuthority
Fornisce metodi che generano e confrontano le chiavi per le identità e i riferimenti dell'applicazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Ottiene un valore che indica se le due istanze di [IDefinitionAppId](idefinitionappid-interface.md) specificate sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreReferencesEqual`|Ottiene un valore che indica se le due istanze di [IReferenceAppId](ireferenceappid-interface.md) specificate sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Ottiene un valore che indica se le due definizioni di stringa specificate sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Ottiene un valore che indica se i due riferimenti di stringa specificati sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::CreateDefinition`|Ottiene un puntatore a interfaccia a un'istanza `IDefinitionAppId` appena generata che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::CreateReference`|Ottiene un puntatore a interfaccia a un oggetto `IReferenceAppId` appena creato che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::DefinitionToText`|Ottiene una versione in formato stringa dell' `IDefinitionAppId`oggetto specificato, utilizzando i valori di flag specificati.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Ottiene un valore che indica se l'oggetto `IDefinitionAppId` specificato `IReferenceAppId` e rappresenta lo stesso assembly.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Ottiene un valore che indica se la stringa di definizione e la stringa di riferimento specificate rappresentano lo stesso assembly.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Ottiene una chiave di stringa che rappresenta l' `IDefinitionAppId` istanza di specificata.|  
|`IAppIdAuthority::GenerateReferenceKey`|Ottiene una chiave di stringa che rappresenta l' `IReferenceAppId` istanza di specificata.|  
|`IAppIdAuthority::HashDefinition`|Ottiene una chiave hash per l'istanza `IDefinitionAppId` di specificata.|  
|`IAppIdAuthority::HashReference`|Ottiene una chiave hash per l'istanza `IReferenceAppId` di specificata.|  
|`IAppIdAuthority::ReferenceToText`|Ottiene una versione in formato stringa dell' `IReferenceAppId`oggetto specificato, utilizzando i valori di flag specificati.|  
|`IAppIdAuthority::TextToDefinition`|Ottiene un puntatore a interfaccia a `IDefinitionAppId` un'istanza di che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.|  
|`IAppIdAuthority::TextToReference`|Ottiene un puntatore a interfaccia a `IReferenceAppId` un'istanza di che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
