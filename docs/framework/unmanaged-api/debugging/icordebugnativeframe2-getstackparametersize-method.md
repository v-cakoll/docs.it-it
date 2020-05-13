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
ms.openlocfilehash: b88b3907eb555050de93f35411629b2bd30c7375
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212945"
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
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|La dimensione dello stack è stata restituita correttamente.|  
|S_FALSE|`GetStackParameterSize`è stato chiamato su una piattaforma non x86.|  
|E_FAIL|`The size of the parameters could not be returned`.|  
|E_INVALIDARG|`pSize`È `null` .|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Osservazioni  
 I metodi [ICorDebugStackWalk](icordebugstackwalk-interface.md) non regolano il puntatore dello stack per i parametri che vengono inseriti nello stack. In alternativa, è possibile usare il valore restituito da `GetStackParameterSize` per regolare il puntatore dello stack per il seeding di un oggetto di rimozione nativo, che si adatta ai parametri.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
