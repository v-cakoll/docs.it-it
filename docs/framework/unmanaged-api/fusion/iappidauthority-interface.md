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
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127125"
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
|`IAppIdAuthority::CreateDefinition`|Ottiene un puntatore a interfaccia a un'istanza di `IDefinitionAppId` appena generata che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::CreateReference`|Ottiene un puntatore a interfaccia a un `IReferenceAppId` appena creato che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::DefinitionToText`|Ottiene una versione in formato stringa del `IDefinitionAppId`specificato, utilizzando i valori di flag specificati.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Ottiene un valore che indica se il `IDefinitionAppId` e il `IReferenceAppId` specificati rappresentano lo stesso assembly.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Ottiene un valore che indica se la stringa di definizione e la stringa di riferimento specificate rappresentano lo stesso assembly.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Ottiene una chiave di stringa che rappresenta l'istanza di `IDefinitionAppId` specificata.|  
|`IAppIdAuthority::GenerateReferenceKey`|Ottiene una chiave di stringa che rappresenta l'istanza di `IReferenceAppId` specificata.|  
|`IAppIdAuthority::HashDefinition`|Ottiene una chiave hash per l'istanza di `IDefinitionAppId` specificata.|  
|`IAppIdAuthority::HashReference`|Ottiene una chiave hash per l'istanza di `IReferenceAppId` specificata.|  
|`IAppIdAuthority::ReferenceToText`|Ottiene una versione in formato stringa del `IReferenceAppId`specificato, utilizzando i valori di flag specificati.|  
|`IAppIdAuthority::TextToDefinition`|Ottiene un puntatore a interfaccia a un'istanza di `IDefinitionAppId` che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.|  
|`IAppIdAuthority::TextToReference`|Ottiene un puntatore a interfaccia a un'istanza di `IReferenceAppId` che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
