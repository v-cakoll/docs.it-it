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
ms.openlocfilehash: 2d71cebb77ed3ca586e857710667c0077f4f76ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793590"
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
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
