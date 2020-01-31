---
title: Interfaccia ICorDebugHeapValue3
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: ddfe8cee8fdbca910ffa4f6989b1359ae5f7b11f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794374"
---
# <a name="icordebugheapvalue3-interface"></a>Interfaccia ICorDebugHeapValue3
Espone le proprietà del blocco di monitoraggio di oggetti. Questa interfaccia estende le interfacce ICorDebugHeapValue e ICorDebugHeapValue2.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetThreadOwningMonitorLock](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|Restituisce il thread gestito proprietario del blocco di monitoraggio su questo oggetto.|  
|[Metodo GetMonitorEventWaitList](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|Fornisce un elenco ordinato di thread accodati per l'evento associato a un blocco di monitoraggio.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
