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
ms.openlocfilehash: 967c0e18b354e6e1cd0d87900e3cde85991c0862
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794320"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>Metodo ICorDebugInternalFrame2::GetFrameAddress
Restituisce l'indirizzo dello stack del frame interno.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAddress`  
 out Puntatore al `CORDB_ADDRESS` per il frame interno.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|L'indirizzo del frame interno è stato restituito correttamente.|  
|E_FAIL|Non è stato possibile restituire l'indirizzo del frame interno.|  
|E_INVALIDARG|`pAddress` è `null`.|  
  
## <a name="remarks"></a>Note  
 Il valore restituito in `pAddress` può essere usato per determinare la posizione del frame interno rispetto ad altri frame nello stack. Anche nei computer basati su IA-64, il frame interno risiede solo nello stack e non esiste alcun puntatore corrispondente a un archivio di backup.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
