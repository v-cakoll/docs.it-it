---
title: Interfaccia ICorDebugGCReferenceEnum
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f09a8974dc1e8cb20185975c42c1cb3ad86a5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647161"
---
# <a name="icordebuggcreferenceenum-interface"></a>Interfaccia ICorDebugGCReferenceEnum
Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Ottiene il numero specificato di [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) istanze che contengono informazioni sugli oggetti che verranno sottoposti a garbage collection.|  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugGCReferenceEnum` interfaccia implementa l'interfaccia "ICorDebugEnum".  
  
 Un' `ICorDebugGCReferenceEnum` istanza viene popolata con [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) istanze chiamando il [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) (metodo). [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) gli oggetti possono essere enumerati chiamando il [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) (metodo).  
  
 Il [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) gli oggetti nella raccolta popolata da questo metodo rappresentano tre tipi di oggetti:  
  
- Oggetti da tutte le chiamate negli stack gestiti. Ciò include i riferimenti in tempo reale nel codice gestito, nonché gli oggetti creati da common language runtime.  
  
- Oggetti dalla tabella di handle. Ciò include riferimenti sicuri (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.  
  
- Oggetti dalla coda del finalizzatore. Coda del finalizzatore radici oggetti fino a quando non è eseguito il finalizzatore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
