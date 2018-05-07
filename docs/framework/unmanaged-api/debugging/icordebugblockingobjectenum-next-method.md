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
ms.openlocfilehash: b4336978825fbf7844b3ceaf179954f28660f08c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugblockingobjectenumnext-method"></a>Metodo ICorDebugBlockingObjectEnum::Next
Ottiene il numero specificato di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) oggetti nell'enumerazione, a partire dalla posizione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
#### <a name="parameters"></a>Parametri  
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
 Questo metodo funziona come un enumeratore COM tipico.  
  
 I valori della matrice di input devono essere almeno di dimensioni `celt`. La matrice verrà compilata con uno successivo `celt` valori nell'enumerazione o con tutti gli altri valori se meno di `celt` rimangono. Quando termina, questo metodo `pceltFetched` verrà compilata con il numero di valori che sono stati recuperati. Se `values` contiene i puntatori non validi o punta a un buffer di dimensioni inferiori a quelle `celt`, o se `pceltFetched` è un puntatore non valido, il risultato è indefinito.  
  
> [!NOTE]
>  Sebbene il [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) struttura non deve essere rilasciato, l'interfaccia "ICorDebugValue" all'interno devono essere rilasciate.  
  
-  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
