---
title: Metodo ICorDebugNativeFrame2::GetStackParameterSize
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: 4dd9760c347bbc23f3e8225c1ff748c6b7b8bfe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096531"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>Metodo ICorDebugNativeFrame2::GetStackParameterSize
Restituisce la dimensione cumulativa dei parametri nello stack nei sistemi operativi x86.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a>Parametri  
 `pSize`  
 out Puntatore alla dimensione cumulativa dei parametri nello stack.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|La dimensione dello stack è stata restituita correttamente.|  
|S_FALSE|`GetStackParameterSize` è stato chiamato su una piattaforma non x86.|  
|E_FAIL|`The size of the parameters could not be returned`|  
|E_INVALIDARG|`pSize` è `null`.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 I metodi [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) non regolano il puntatore dello stack per i parametri che vengono inseriti nello stack. In alternativa, è possibile usare il valore restituito da `GetStackParameterSize` per regolare il puntatore dello stack per il seeding di una rimozione nativa, che si adatta ai parametri.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugNativeFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
