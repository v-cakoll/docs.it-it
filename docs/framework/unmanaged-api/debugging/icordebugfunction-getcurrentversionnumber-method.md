---
title: Metodo ICorDebugFunction::GetCurrentVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetCurrentVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea615eacb30fd4e7a0fd7d730094c2ab4f9dc285
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988728"
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a>Metodo ICorDebugFunction::GetCurrentVersionNumber
Ottiene il numero di versione dell'ultima modifica apportata alla funzione rappresentata da questo oggetto ICorDebugFunction.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnCurrentVersion`  
 [out] Un puntatore a un valore intero che indica il numero di versione dell'ultima modifica apportata a questa funzione.  
  
## <a name="remarks"></a>Note  
 Il numero di versione dell'ultima modifica apportata a questa funzione può essere maggiore del numero di versione della funzione stessa. Usare la [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) metodo o il [GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metodo per recuperare il numero di versione della funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
