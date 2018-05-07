---
title: Metodo ICorDebugChain::IsManaged
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c8c61cc12e438c0786b6e093b8bb1ea288a42e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchainismanaged-method"></a>Metodo ICorDebugChain::IsManaged
Ottiene un valore che indica se la catena è in esecuzione il codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pManaged`  
 [out] `true` se la catena è in esecuzione il codice gestito; in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
