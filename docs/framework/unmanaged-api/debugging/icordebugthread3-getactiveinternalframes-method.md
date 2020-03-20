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
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178457"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>Metodo ICorDebugThread3::GetActiveInternalFrames
Restituisce una matrice di frame interni ([iCorDebugInternalFrame2](icordebuginternalframe2-interface.md) oggetti) nello stack.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
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
 [in] Il numero di fotogrammi interni previsti in `ppInternalFrames`.  
  
 `pcInternalFrames`  
 [fuori] Puntatore a `ULONG32` un che contiene il numero di frame interni nello stack.  
  
 `ppInternalFrames`  
 [in, out] Puntatore all'indirizzo di una matrice di frame interni nello stack.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'oggetto [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) è stato creato correttamente.|  
|E_INVALIDARG|`cInternalFrames`non è `ppInternalFrames` zero `null`e `pcInternalFrames` `null`è , o è .|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`è inferiore al conteggio dei fotogrammi interni.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Osservazioni  
 I frame interni sono strutture di dati inserite nello stack dal runtime per archiviare i dati temporanei.  
  
 Quando si `GetActiveInternalFrames`chiama per la `cInternalFrames` prima volta , è `ppInternalFrames` necessario impostare il parametro su 0 (zero) e il parametro su null. Quando `GetActiveInternalFrames` termina `pcInternalFrames` per la prima volta, contiene il conteggio dei frame interni nello stack.  
  
 `GetActiveInternalFrames`dovrebbe quindi essere chiamato una seconda volta. È necessario passare il`pcInternalFrames`conteggio `cInternalFrames` corretto ( ) nel parametro e `ppInternalFrames`specificare un puntatore a una matrice di dimensioni appropriate in .  
  
 Utilizzare il [iCorDebugStackWalk::GetFrame](icordebugthread3-getactiveinternalframes-method.md) metodo per restituire gli stack frame effettivi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
