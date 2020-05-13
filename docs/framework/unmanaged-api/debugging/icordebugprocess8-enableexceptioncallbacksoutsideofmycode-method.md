---
title: Metodo ICorDebugProcess8::EnableExceptionCallbacksOutsideOfMyCode
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: b3af44ec-7d41-425b-aed9-0c4379e5cbe9
ms.openlocfilehash: e54dd051f0dbd9c1964d381c2e05189c375fa66d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210137"
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
  
## <a name="remarks"></a>Osservazioni  
 Se il valore di `enableExceptionsOutsideOfJMC` è `false`:  
  
- Un'eccezione DEBUG_EXCEPTION_FIRST_CHANCE non darà luogo a un callback al debugger.  
  
- Un'eccezione DEBUG_EXCEPTION_CATCH_HANDLER_FOUND darà luogo a un callback al debugger se l'eccezione non raggiunge mai il codice utente (ovvero, il percorso dall'origine di un'eccezione a un gestore di eccezioni non ha metodi contrassegnati JustMyCode o JMC).  
  
 Il valore predefinito di `enableExceptionsOutsideOfJMC` è `true`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess8](icordebugprocess8-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
