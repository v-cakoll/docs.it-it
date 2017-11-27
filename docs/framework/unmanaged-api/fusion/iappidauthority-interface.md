---
title: Interfaccia IAppIdAuthority
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppIdAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IAppIdAuthority
helpviewer_keywords: IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07bfd26a43d264babc9854b0fd0da909dd329405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iappidauthority-interface"></a>Interfaccia IAppIdAuthority
Fornisce metodi che generano e confrontare le chiavi per le identità delle applicazioni e i riferimenti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Ottiene un valore che indica se le due [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) istanze sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreReferencesEqual`|Ottiene un valore che indica se le due [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) istanze sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Ottiene un valore che indica se le due definizioni di stringa specificato sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Ottiene un valore che indica se i due riferimenti di stringa specificato sono uguali. È possibile passare il valore del flag IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION per ignorare le rispettive informazioni sulla versione.|  
|`IAppIdAuthority::CreateDefinition`|Ottiene un puntatore a interfaccia a un oggetto appena generato `IDefinitionAppId` istanza che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::CreateReference`|Ottiene un puntatore a interfaccia a un oggetto appena creato `IReferenceAppId` che rappresenta l'assembly nell'ambito corrente.|  
|`IAppIdAuthority::DefinitionToText`|Ottiene una versione stringa dell'oggetto specificato `IDefinitionAppId`, utilizzando i valori di flag specificato.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Ottiene un valore che indica se l'oggetto specificato `IDefinitionAppId` e `IReferenceAppId` rappresentano lo stesso assembly.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Ottiene un valore che indica se la stringa di definizione specificato e una stringa di riferimento rappresentano lo stesso assembly.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IDefinitionAppId` istanza.|  
|`IAppIdAuthority::GenerateReferenceKey`|Ottiene una chiave di stringa che rappresenta l'oggetto specificato `IReferenceAppId` istanza.|  
|`IAppIdAuthority::HashDefinition`|Ottiene una chiave hash per l'oggetto specificato `IDefinitionAppId` istanza.|  
|`IAppIdAuthority::HashReference`|Ottiene una chiave hash per l'oggetto specificato `IReferenceAppId` istanza.|  
|`IAppIdAuthority::ReferenceToText`|Ottiene una versione stringa dell'oggetto specificato `IReferenceAppId`, utilizzando i valori di flag specificato.|  
|`IAppIdAuthority::TextToDefinition`|Ottiene un puntatore a interfaccia a un `IDefinitionAppId` istanza che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.|  
|`IAppIdAuthority::TextToReference`|Ottiene un puntatore a interfaccia a un `IReferenceAppId` istanza che rappresenta l'assembly a cui fa riferimento la chiave di stringa specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Fusion (interfacce)](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
