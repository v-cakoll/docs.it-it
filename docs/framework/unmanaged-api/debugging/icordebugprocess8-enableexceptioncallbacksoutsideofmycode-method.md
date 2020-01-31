---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: 2c0da899b3f6f3c229c6f5e5b4cafe48fdc19742
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792162"
---
# <a name="icordebugprocess8enableexceptioncallbacksoutsideofmycode-method"></a>Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
[Supportato in .NET Framework 4,6 e versioni successive]  
  
 Abilita o disabilita alcuni tipi di callback di eccezione [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT EnableExceptionCallbacksOutsideOfMyCode(  
   [in] BOOL enableExceptionsOutsideOfJMC  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `enableExceptionsOutsideOfJMC`  
 [in]  
  
## <a name="remarks"></a>Note  
 Se il valore di `enableExceptionsOutsideOfJMC` è `false`:  
  
- Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non darà luogo a un callback al debugger.  
  
- Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND darà luogo a un callback al debugger se l'eccezione non raggiunge mai il codice utente (ovvero, il percorso dall'origine di un'eccezione a un gestore di eccezioni non ha metodi contrassegnati JustMyCode o JMC).  
  
 Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess8](icordebugprocess8-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
