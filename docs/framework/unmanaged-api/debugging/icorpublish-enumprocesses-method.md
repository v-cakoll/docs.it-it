---
title: Metodo ICorPublish::EnumProcesses
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.EnumProcesses
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7e0af492cbec401d7470502de807033f21e39f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishenumprocesses-method"></a>Metodo ICorPublish::EnumProcesses
Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `Type`  
 Il valore di [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumerazione che specifica il tipo di processo da recuperare. Nella versione corrente, è valido solo COR_PUB_MANAGEDONLY.  
  
 `ppIEnum`  
 Un puntatore all'indirizzo di un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) istanza che è l'enumeratore dei processi.  
  
## <a name="remarks"></a>Note  
 Raccolta dell'enumeratore dei processi è basato su uno snapshot dei processi in esecuzione quando il `EnumProcesses` metodo viene chiamato. L'enumeratore non includerà alcun processo che termina prima o dopo `EnumProcesses` viene chiamato.  
  
 Il `EnumProcesses` metodo può essere chiamato più volte su questo [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) istanza per creare un nuovo insieme di processi aggiornato. Le raccolte esistenti non saranno interessate dalle chiamate successive del `EnumProcesses` metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Corpub. idl, CorPub.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
