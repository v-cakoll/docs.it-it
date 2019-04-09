---
title: Interfaccia IReferenceIdentity
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220162"
---
# <a name="ireferenceidentity-interface"></a>Interfaccia IReferenceIdentity
Rappresenta un riferimento a una firma univoca di un oggetto di codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ottiene un puntatore a interfaccia a una nuova `IReferenceIdentity` identica a questa istanza `IReferenceIdentity`, fatta eccezione per le modifiche di attributo specificato.|  
|`IReferenceIdentity::EnumAttributes`|Ottiene un puntatore a interfaccia a un `IEnumIDENTITY_ATTRIBUTE` istanza che contiene gli attributi associati a questo `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Ottiene il valore dell'attributo nello spazio dei nomi specificato, con il nome specificato.|  
|`IReferenceIdentity::SetAttribute`|Imposta l'attributo con lo spazio dei nomi specificato e il nome specificato al valore specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [Interfaccia IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
