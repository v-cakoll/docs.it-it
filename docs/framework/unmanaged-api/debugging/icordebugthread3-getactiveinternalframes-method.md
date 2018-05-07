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
ms.openlocfilehash: 2ac87de35478e5eabdc8cdc3568baf2086923e38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
#### <a name="parameters"></a>Parametri  
 `cInternalFrames`  
 [in] Il numero di frame interni previsti in `ppInternalFrames`.  
  
 `pcInternalFrames`  
 [out] Un puntatore a un `ULONG32` che contiene il numero di frame interni nello stack.  
  
 `ppInternalFrames`  
 [in, out] Un puntatore all'indirizzo di una matrice di frame interni nello stack.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) oggetto è stato creato correttamente.|  
|E_INVALIDARG|`cInternalFrames` non è zero e `ppInternalFrames` viene `null`, o `pcInternalFrames` è `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` è minore del numero di frame interni.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Frame interni sono strutture di dati nello stack dal runtime per archiviare dati temporanei.  
  
 Quando si chiama innanzitutto `GetActiveInternalFrames`, è necessario impostare il `cInternalFrames` parametro su 0 (zero) e `ppInternalFrames` parametro su null. Quando `GetActiveInternalFrames` restituita innanzitutto, `pcInternalFrames` contiene il numero di frame interni nello stack.  
  
 `GetActiveInternalFrames` deve quindi essere chiamato una seconda volta. È necessario passare il numero appropriato (`pcInternalFrames`) nei `cInternalFrames` parametro e specificare un puntatore a una matrice di dimensione appropriate in `ppInternalFrames`.  
  
 Utilizzare il [GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) frame dello stack per restituire effettivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
