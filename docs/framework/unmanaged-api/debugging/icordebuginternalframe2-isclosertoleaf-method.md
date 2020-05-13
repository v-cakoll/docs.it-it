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
ms.openlocfilehash: 4a01ccd4e5cb9aadc6a693b2c6ceaff31c114bbc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209890"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>Metodo ICorDebugInternalFrame2::IsCloserToLeaf
Controlla se il `this` frame interno è più vicino alla foglia rispetto all'oggetto ICorDebugFrame specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFrameToCompare`  
 in Puntatore all'oggetto di confronto `ICorDebugFrame` .  
  
 `pIsCloser`  
 [out] `true` Se il `this` frame interno è più vicino alla foglia rispetto al frame specificato da `pFrameToCompare` ; in caso contrario, `false` .  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Il confronto è stato eseguito correttamente.|  
|E_FAIL|Non è stato possibile eseguire il confronto.|  
|E_INVALIDARG|`pFrameToCompare` o `pIsCloser` è null.|  
  
## <a name="remarks"></a>Osservazioni  
 `IsCloserToLeaf`può essere usato per implementare un criterio per l'interfoliazione di frame interni con altri frame nello stack.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
