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
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784669"
---
# <a name="icordebugassembly-interface"></a>Interfaccia ICorDebugAssembly

Rappresenta un assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateModules](icordebugassembly-enumeratemodules-method.md)|Ottiene un enumeratore per i moduli contenuti nell'assembly.|  
|[Metodo GetAppDomain](icordebugassembly-getappdomain-method.md)|Ottiene un puntatore a interfaccia per il dominio dell'applicazione che contiene questa istanza di `ICorDebugAssembly`.|  
|[Metodo GetCodeBase](icordebugassembly-getcodebase-method.md)|Non implementato nella versione corrente del .NET Framework.|  
|[Metodo GetName](icordebugassembly-getname-method.md)|Ottiene il nome dell'assembly.|  
|[Metodo GetProcess](icordebugassembly-getprocess-method.md)|Ottiene l'istanza di ICorDebugProcess in cui è in esecuzione l'assembly.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
