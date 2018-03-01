---
title: Interfaccia IReferenceIdentity
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c9696687f292d7dcaa3d430c1e269f0fedb05e98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ireferenceidentity-interface"></a>Interfaccia IReferenceIdentity
Rappresenta un riferimento alla firma univoca di un oggetto di codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ottiene un puntatore a interfaccia a un nuovo `IReferenceIdentity` istanza è uguale a `IReferenceIdentity`, tranne le modifiche di attributo specificato.|  
|`IReferenceIdentity::EnumAttributes`|Ottiene un puntatore a interfaccia a un `IEnumIDENTITY_ATTRIBUTE` istanza che contiene gli attributi associati a questo `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Ottiene il valore dell'attributo nello spazio dei nomi specificato con il nome specificato.|  
|`IReferenceIdentity::SetAttribute`|Imposta l'attributo con lo spazio dei nomi specificato e il nome specificato per il valore specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Interfaccia IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
