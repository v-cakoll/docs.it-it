---
title: Metodo ICorDebugModule::IsInMemory
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d79a8b0c3c56ffe2b8f57ec26f5942ee0d681194
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187590"
---
# <a name="icordebugmoduleisinmemory-method"></a>Metodo ICorDebugModule::IsInMemory
Ottiene un valore che indica se questo modulo esiste solo in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pInMemory`  
 [out] `true` se questo modulo esiste solo in memoria; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Common language runtime (CLR) supporta il caricamento dei moduli da flussi di byte non elaborati. Questi moduli sono denominati *i moduli in memoria* e non esistono sul disco.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
