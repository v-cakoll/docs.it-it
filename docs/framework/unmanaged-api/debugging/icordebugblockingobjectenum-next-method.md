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
ms.openlocfilehash: 3a1c4a931a61186c4737aada47ceb861e7848e7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122839"
---
# <a name="icordebugblockingobjectenumnext-method"></a>Metodo ICorDebugBlockingObjectEnum::Next
Ottiene il numero specificato di oggetti [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) dall'enumerazione, a partire dalla posizione corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>Parametri  
 `celt`  
 in Numero di oggetti da recuperare.  
  
 `values`  
 out Matrice di puntatori a oggetti [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .  
  
 `pceltFetched`  
 out Puntatore al numero di oggetti recuperati.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli HRESULT specifici seguenti.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|S_FALSE|`pceltFetched` non è uguale a `celt`.|  
  
## <a name="remarks"></a>Note  
 Questo metodo funziona come un tipico enumeratore COM.  
  
 I valori della matrice di input devono essere di almeno dimensioni `celt`. La matrice verrà compilata con i valori `celt` successivi nell'enumerazione o con tutti i valori rimanenti se il numero di `celt` rimane. Quando termina, questo metodo `pceltFetched` verrà compilato con il numero di valori recuperati. Se `values` contiene puntatori o puntatori non validi a un buffer di dimensioni minori di `celt`o se `pceltFetched` è un puntatore non valido, il risultato sarà indefinito.  
  
> [!NOTE]
> Sebbene non sia necessario rilasciare la struttura [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) , è necessario rilasciare l'interfaccia "ICorDebugValue" all'interno di essa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
