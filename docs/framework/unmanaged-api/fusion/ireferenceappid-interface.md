---
title: Interfaccia IReferenceAppId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22ac2d75632b3c670d7c185cbbf5081732dcaffc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ireferenceappid-interface"></a>Interfaccia IReferenceAppId
Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Imposta l'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Ottiene un puntatore a interfaccia a un `IEnumReferenceIdentity` istanza contenente il `IReferenceIdentity` istanze che rappresentano i membri di questo `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di token per una sottoscrizione a questo `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Imposta l'identificatore del token per una sottoscrizione a questo `IReferenceAppId` al valore stringa specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Interfaccia IEnumReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [Interfaccia IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
