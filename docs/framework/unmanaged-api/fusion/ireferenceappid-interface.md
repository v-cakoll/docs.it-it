---
title: Interfaccia IReferenceAppId
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796377"
---
# <a name="ireferenceappid-interface"></a>Interfaccia IReferenceAppId
Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione a cui fa `IReferenceAppId`riferimento questo oggetto.|  
|`IReferenceAppId::put_CodeBase`|Imposta l'identificatore del codice per l'applicazione a cui fa `IReferenceAppId`riferimento questo oggetto.|  
|`IReferenceAppId::EnumAppPath`|Ottiene un puntatore a interfaccia a `IEnumReferenceIdentity` un'istanza di `IReferenceIdentity` che contiene le istanze di che `IReferenceAppId`rappresentano i membri di questo oggetto.|  
|`IReferenceAppId::get_SubscriptionId`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a `IReferenceAppId`questa.|  
|`IReferenceAppId::put_SubscriptionId`|Imposta l'identificatore del token per una sottoscrizione a `IReferenceAppId` questo oggetto sul valore stringa specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IEnumReferenceIdentity](ienumreferenceidentity-interface.md)
- [Interfaccia IReferenceIdentity](ireferenceidentity-interface.md)
