---
title: Metodo ICorDebugInternalFrame2::IsCloserToLeaf
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120900"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>Metodo ICorDebugInternalFrame2::IsCloserToLeaf
Controlla se il `this` frame interno è più simile alla foglia a oggetto ICorDebugFrame specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFrameToCompare`  
 [in] Un puntatore al confronto `ICorDebugFrame` oggetto.  
  
 `pIsCloser`  
 [out] `true` se il `this` frame interno è più simile alla foglia a frame specificato da `pFrameToCompare`; in caso contrario, `false`.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il confronto è stato eseguito correttamente.|  
|E_FAIL|Non è stato possibile eseguire il confronto.|  
|E_INVALIDARG|`pFrameToCompare` o `pIsCloser` è null.|  
  
## <a name="remarks"></a>Note  
 `IsCloserToLeaf` può essere utilizzato per implementare un criterio per interfoliazione frame interni con altri frame nello stack.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
