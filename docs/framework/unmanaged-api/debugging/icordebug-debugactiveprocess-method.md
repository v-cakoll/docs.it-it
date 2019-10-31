---
title: Metodo ICorDebug::DebugActiveProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 5b988b110100cd159b8e262573df409847d635c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134121"
---
# <a name="icordebugdebugactiveprocess-method"></a>Metodo ICorDebug::DebugActiveProcess
Connette il debugger a un processo esistente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `id`  
 in ID del processo a cui deve essere collegato il debugger.  
  
 `win32Attach`  
 in Valore booleano impostato su `true` se il debugger deve comportarsi come debugger Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false`.  
  
 `ppProcess`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato collegato il debugger.  
  
## <a name="remarks"></a>Note  
 Il debug di interoperabilità non è supportato in piattaforme Win9x e non x86, ad esempio piattaforme basate su IA-64 e AMD64.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
