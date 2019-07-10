---
title: Metodo ICorDebugBlockingObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd82418da26ab0cd32b007b4613d588dfa695eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745297"
---
# <a name="icordebugblockingobjectenumnext-method"></a>Metodo ICorDebugBlockingObjectEnum::Next
Ottiene il numero specificato di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) oggetti dall'enumerazione, iniziando in corrispondenza della posizione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
 [in] Il numero di oggetti da recuperare.  
  
 `values`  
 [out] Una matrice di puntatori a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) oggetti.  
  
 `pceltFetched`  
 [out] Puntatore al numero di oggetti che sono stati recuperati.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli HRESULT specifici seguenti.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|S_FALSE|`pceltFetched` non è uguale a `celt`.|  
  
## <a name="remarks"></a>Note  
 Questo metodo funziona come un tipico enumeratore COM.  
  
 I valori della matrice di input devono essere almeno di dimensioni `celt`. La matrice verrà riempita con uno successivo `celt` i valori nell'enumerazione o con tutti gli altri valori se meno `celt` rimangono. Quando termina, questo metodo `pceltFetched` verrà riempito con il numero di valori che sono stati recuperati. Se `values` contiene i puntatori non validi o punta a un buffer di dimensioni inferiori a quelle `celt`, o se `pceltFetched` è un puntatore non valido, il risultato è indefinito.  
  
> [!NOTE]
>  Anche se il [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) struttura non dovrà essere rilasciato, è necessario che l'interfaccia "ICorDebugValue" TestExecution da rilasciare.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
