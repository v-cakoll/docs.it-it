---
title: Metodo ICorDebugValue::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb0030a25dd48ab4236ec2b51891e0ac41aac902
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612619"
---
# <a name="icordebugvaluegetsize-method"></a>Metodo ICorDebugValue::GetSize
Ottiene la dimensione, espressa in byte, dell'oggetto "ICorDebugValue".  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pSize`  
 [out] Le dimensioni, in byte, dell'oggetto valore.  
  
## <a name="remarks"></a>Note  
 Se il tipo del valore è un tipo riferimento, questo metodo restituisce la dimensione del puntatore anziché le dimensioni dell'oggetto.  
  
 Il `ICorDebugValue::GetSize` restituzione del metodo `COR_E_OVERFLOW` per gli oggetti di dimensioni superiori a 4 GB su piattaforme a 64 bit. Usare la [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) metodo invece per gli oggetti che sono maggiori di 4 GB.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
