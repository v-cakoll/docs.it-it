---
title: Metodo ICorDebugILFrame4::GetCodeEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb50459e36cfeb76a0c9a1e1cd4544260d484f45
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926803"
---
# <a name="icordebugilframe4getcodeex-method"></a>Metodo ICorDebugILFrame4::GetCodeEx
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Recupera un puntatore al codice eseguito da questo stack frame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `flags`  
 in Membro di enumerazione [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) che specifica se il linguaggio intermedio (il) definito dalla richiesta ReJIT del profiler è incluso nel frame.  
  
 `ppCode`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta il codice in esecuzione nel stack frame.  
  
## <a name="remarks"></a>Note  
 Questo metodo è simile al metodo [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) , ad eccezione del fatto che accede facoltativamente al codice definito dalla richiesta ReJIT del profiler. La chiamata di `ILCODE_ORIGINAL_IL` questo metodo `flags` con un valore equivale alla chiamata a [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); se il metodo è instrumentato, il relativo il non sarà accessibile. `ILCODE_REJIT_IL` consente al debugger di accedere al linguaggio intermedio definito dalla richiesta ReJIT del profiler. Se il linguaggio intermedio non è instrumentato, `ppCode` è **null**e il metodo `S_OK`restituisce.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT Guida alle procedure](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
