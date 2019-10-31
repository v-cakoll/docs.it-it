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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131656"
---
# <a name="ireferenceappid-interface"></a>Interfaccia IReferenceAppId
Rappresenta un riferimento all'identificatore univoco per l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.|  
|`IReferenceAppId::put_CodeBase`|Imposta l'identificatore del codice per l'applicazione a cui fa riferimento questo `IReferenceAppId`.|  
|`IReferenceAppId::EnumAppPath`|Ottiene un puntatore a interfaccia a un'istanza `IEnumReferenceIdentity` contenente le istanze di `IReferenceIdentity` che rappresentano i membri di questa `IReferenceAppId`.|  
|`IReferenceAppId::get_SubscriptionId`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a questo `IReferenceAppId`.|  
|`IReferenceAppId::put_SubscriptionId`|Imposta l'identificatore del token per una sottoscrizione di questo `IReferenceAppId` sul valore stringa specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IEnumReferenceIdentity](ienumreferenceidentity-interface.md)
- [Interfaccia IReferenceIdentity](ireferenceidentity-interface.md)
