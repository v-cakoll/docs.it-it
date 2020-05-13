---
title: Metodo ICorDebugInternalFrame2::GetFrameAddress
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 51c8f9a2b66d7b2553949056f7cdbedcf5ea37d6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209916"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>Metodo ICorDebugInternalFrame2::GetFrameAddress
Restituisce l'indirizzo dello stack del frame interno.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAddress`  
 out Puntatore a `CORDB_ADDRESS` per il frame interno.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|L'indirizzo del frame interno è stato restituito correttamente.|  
|E_FAIL|Non è stato possibile restituire l'indirizzo del frame interno.|  
|E_INVALIDARG|`pAddress` è `null`.|  
  
## <a name="remarks"></a>Osservazioni  
 Il valore restituito in `pAddress` può essere utilizzato per determinare la posizione del frame interno rispetto ad altri frame nello stack. Anche nei computer basati su IA-64, il frame interno risiede solo nello stack e non esiste alcun puntatore corrispondente a un archivio di backup.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
