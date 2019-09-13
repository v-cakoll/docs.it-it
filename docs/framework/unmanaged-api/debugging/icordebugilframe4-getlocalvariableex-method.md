---
title: Metodo ICorDebugILFrame4::GetLocalVariableEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetCodeEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0c8676f8-ca0d-4998-b64d-fefac7e38912
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4eaaa23a810a23852dc5ef88d61c6a5d0f0ccd
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926815"
---
# <a name="icordebugilframe4getlocalvariableex-method"></a>Metodo ICorDebugILFrame4::GetLocalVariableEx
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Recupera il valore della variabile locale in questo stack frame del linguaggio intermedio e facoltativamente accede a una variabile aggiunta nella strumentazione ReJIT del profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetLocalVariableEx(  
   [in] ILCodeKind flags,   
   [in] DWORD dwIndex,   
   [out] ICorDebugValue **ppValue  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `flags`  
 in Membro di enumerazione [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) che specifica se una variabile aggiunta nella strumentazione ReJIT del profiler è inclusa nel frame.  
  
 `dwIndex`  
 [in] Indice della variabile locale nello stack frame del linguaggio intermedio.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato.  
  
## <a name="remarks"></a>Note  
 Questo metodo è simile al metodo [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) , ad eccezione del fatto che accede facoltativamente a una variabile aggiunta nella strumentazione ReJIT del profiler. La chiamata di `ILCODE_ORIGINAL_IL` questo metodo `flags` con un valore equivale alla chiamata a [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); se il metodo è instrumentato con variabili locali aggiuntive, non è possibile accedere a tali variabili. `ILCODE_REJIT_IL` consente al debugger di accedere alle variabili locali aggiunte nella strumentazione ReJIT del profiler. Se il linguaggio intermedio non è instrumentato, il metodo restituisce `E_INVALIDARG`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ReJIT Guida alle procedure](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
