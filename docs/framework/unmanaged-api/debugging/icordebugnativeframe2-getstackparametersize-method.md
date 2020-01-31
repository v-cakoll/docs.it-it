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
ms.openlocfilehash: ca742ba9e89e1d189cfa38dead314df0d8b4e9d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792767"
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
|E_FAIL|`The size of the parameters could not be returned`.|  
|E_INVALIDARG|`pSize` è `null`.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 I metodi [ICorDebugStackWalk](icordebugstackwalk-interface.md) non regolano il puntatore dello stack per i parametri che vengono inseriti nello stack. In alternativa, è possibile usare il valore restituito da `GetStackParameterSize` per regolare il puntatore dello stack per il seeding di una rimozione nativa, che si adatta ai parametri.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
