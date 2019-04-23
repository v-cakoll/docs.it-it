---
title: Metodo ICorDebugThread3::GetActiveInternalFrames
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e264f2361c739536d15fbf31d366db74e107bac2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085103"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>Metodo ICorDebugThread3::GetActiveInternalFrames
Restituisce una matrice di frame interni ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) oggetti) nello stack.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>Parametri  
 `cInternalFrames`  
 [in] Il numero di frame interni previsto in `ppInternalFrames`.  
  
 `pcInternalFrames`  
 [out] Un puntatore a un `ULONG32` che contiene il numero di frame interni dello stack.  
  
 `ppInternalFrames`  
 [in, out] Un puntatore all'indirizzo di una matrice di frame interni dello stack.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) oggetto è stato creato correttamente.|  
|E_INVALIDARG|`cInternalFrames` non è uguale a zero e `ppInternalFrames` viene `null`, o `pcInternalFrames` è `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` è minore del numero di frame interni.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Frame interni sono strutture di dati inserite nello stack dal runtime per archiviare dati temporanei.  
  
 Quando si chiama innanzitutto `GetActiveInternalFrames`, è necessario impostare la `cInternalFrames` parametro su 0 (zero) e il `ppInternalFrames` parametro su null. Quando `GetActiveInternalFrames` restituisce prima, `pcInternalFrames` contiene il numero dei frame interni dello stack.  
  
 `GetActiveInternalFrames` deve quindi essere chiamato una seconda volta. È necessario passare il numero appropriato (`pcInternalFrames`) nei `cInternalFrames` parametro, e specificare un puntatore a una matrice di dimensione appropriate in `ppInternalFrames`.  
  
 Usare la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) metodo restituisca effettivo stack frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
