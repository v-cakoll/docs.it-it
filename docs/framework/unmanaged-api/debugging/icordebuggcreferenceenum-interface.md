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
ms.openlocfilehash: f01c27376191c3a2dddf56dae4b26c8b5193c73e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788646"
---
# <a name="icordebuggcreferenceenum-interface"></a>Interfaccia ICorDebugGCReferenceEnum
Fornisce un enumeratore per gli oggetti che verranno sottoposti a operazioni di Garbage Collection.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](icordebuggcreferenceenum-next-method.md)|Ottiene il numero specificato di istanze di [COR_GC_REFERENCE](cor-gc-reference-structure.md) che contengono informazioni sugli oggetti che verranno sottoposti a Garbage Collection.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugGCReferenceEnum` implementa l'interfaccia "ICorDebugEnum".  
  
 Un'istanza di `ICorDebugGCReferenceEnum` viene popolata con [COR_GC_REFERENCE](cor-gc-reference-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateGCReferences](icordebugprocess5-enumerategcreferences-method.md) . È possibile enumerare gli oggetti [COR_GC_REFERENCE](cor-gc-reference-structure.md) chiamando il metodo [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .  
  
 Gli oggetti [COR_GC_REFERENCE](cor-gc-reference-structure.md) nella raccolta popolata da questo metodo rappresentano tre tipi di oggetti:  
  
- Oggetti da tutti gli stack gestiti. Sono inclusi i riferimenti Live nel codice gestito e gli oggetti creati dal Common Language Runtime.  
  
- Oggetti dalla tabella di handle. Sono inclusi i riferimenti sicuri (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.  
  
- Oggetti dalla coda del finalizzatore. Il finalizzatore Accoda oggetti radice fino all'esecuzione del finalizzatore.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
