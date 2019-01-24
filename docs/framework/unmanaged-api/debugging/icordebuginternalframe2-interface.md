---
title: Interfaccia ICorDebugInternalFrame2
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd867db8886c1c74d209e080b6b810ed4adc3654
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589334"
---
# <a name="icordebuginternalframe2-interface"></a>Interfaccia ICorDebugInternalFrame2
Vengono fornite informazioni sui frame interni, compresi l'indirizzo dello stack e la posizione in relazione agli oggetti ICorDebugFrame.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetFrameAddress](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|Restituisce l'indirizzo dello stack del frame interno.|  
|[Metodo IsCloserToLeaf](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|Controlla se il `this` frame interno è più simile alla foglia a oggetto ICorDebugFrame specificato.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia estende l'interfaccia ICorDebugInternalFrame.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
