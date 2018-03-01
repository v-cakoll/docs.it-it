---
title: Interfaccia IEnumReferenceIdentity
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
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d1af31c72770947c33f358a9689bac6fd95ef53c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ienumreferenceidentity-interface"></a>Interfaccia IEnumReferenceIdentity
Funge da un enumeratore per una raccolta di `IReferenceIdentity` oggetti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Ottiene un puntatore a interfaccia a un nuovo `IEnumReferenceIdentity` che contiene gli stessi membri di questo `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Ottiene il numero specificato di `IReferenceIdentity` oggetti, a partire dalla posizione corrente.|  
|`IEnumReferenceIdentity::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Interfaccia IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
