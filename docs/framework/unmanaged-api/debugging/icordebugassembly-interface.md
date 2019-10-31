---
title: Interfaccia ICorDebugAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
ms.openlocfilehash: dea3231e3bbb361b56254756c6d99b115f73e792
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133965"
---
# <a name="icordebugassembly-interface"></a>Interfaccia ICorDebugAssembly

Rappresenta un assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateModules](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|Ottiene un enumeratore per i moduli contenuti nell'assembly.|  
|[Metodo GetAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questa istanza di `ICorDebugAssembly`.|  
|[Metodo GetCodeBase](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|Non implementato nella versione corrente del .NET Framework.|  
|[Metodo GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|Ottiene il nome dell'assembly.|  
|[Metodo GetProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|Ottiene l'istanza di ICorDebugProcess in cui è in esecuzione l'assembly.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
