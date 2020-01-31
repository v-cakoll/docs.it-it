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
ms.openlocfilehash: c25f26bb0f1f34e3799bab4bec7e697d393cccb4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784519"
---
# <a name="icordebugblockingobjectenumnext-method"></a>Metodo ICorDebugBlockingObjectEnum::Next
Ottiene il numero specificato di oggetti [CorDebugBlockingObject](cordebugblockingobject-structure.md) dall'enumerazione, a partire dalla posizione corrente.  
  
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
 out Matrice di puntatori a oggetti [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 `pceltFetched`  
 out Puntatore al numero di oggetti recuperati.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli HRESULT specifici seguenti.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il metodo è stato eseguito correttamente.|  
|S_FALSE|`pceltFetched` non è uguale a `celt`.|  
  
## <a name="remarks"></a>Note  
 Questo metodo funziona come un tipico enumeratore COM.  
  
 I valori della matrice di input devono essere di almeno dimensioni `celt`. La matrice verrà compilata con i valori `celt` successivi nell'enumerazione o con tutti i valori rimanenti se il numero di `celt` rimane. Quando termina, questo metodo `pceltFetched` verrà compilato con il numero di valori recuperati. Se `values` contiene puntatori o puntatori non validi a un buffer di dimensioni minori di `celt`o se `pceltFetched` è un puntatore non valido, il risultato sarà indefinito.  
  
> [!NOTE]
> Sebbene non sia necessario rilasciare la struttura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , è necessario rilasciare l'interfaccia "ICorDebugValue" all'interno di essa.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
