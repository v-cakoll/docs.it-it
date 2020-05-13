---
title: Metodo ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
ms.openlocfilehash: 291b384d6f0c8c1404b380c653693ec65fcfc960
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213413"
---
# <a name="icordebugprocess5enumeratehandles-method"></a>Metodo ICorDebugProcess5::EnumerateHandles
Ottiene un enumeratore per gli handle di oggetto in un processo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parametri  
 `types`  
 in Combinazione bit per bit di valori [CorGCReferenceType](corgcreferencetype-enumeration.md) che specifica il tipo di handle da includere nella raccolta.  
  
 `ppENum`  
 out Puntatore all'indirizzo di un [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) che rappresenta un enumeratore per gli oggetti di cui eseguire il Garbage Collector.  
  
## <a name="remarks"></a>Osservazioni  
 `EnumerateHandles`è una funzione helper che supporta l'ispezione della tabella dell'handle. È simile al metodo [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) , ad eccezione del fatto che anziché popolare una raccolta [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md) con tutti gli oggetti da sottoporre a Garbage Collection, include solo gli oggetti che hanno handle dalla tabella di handle.  
  
 Il `types` parametro specifica i tipi di handle da includere nella raccolta. `types`può essere uno dei tre membri seguenti dell'enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) :  
  
- `CorHandleStrongOnly`(gestisce solo i riferimenti sicuri).  
  
- `CorHandleWeakOnly`(gestisce solo i riferimenti deboli).  
  
- `CorHandleAll`(tutti gli handle).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
