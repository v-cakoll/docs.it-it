---
title: Interfaccia ICorDebugManagedCallback3
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
ms.openlocfilehash: b97f29b94ed4fad6892697ca1c7ed4a20c99c03e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793278"
---
# <a name="icordebugmanagedcallback3-interface"></a>Interfaccia ICorDebugManagedCallback3
Fornisce un metodo di callback che indica che è stata generata una notifica di debugger personalizzata abilitata.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CustomNotification](icordebugmanagedcallback3-customnotification-method.md)|Indica che è stata generata una notifica del debugger personalizzata abilitata.|  
  
## <a name="remarks"></a>Note  
 Questa interfaccia è un'estensione logica delle interfacce [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
- [Interfaccia ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
