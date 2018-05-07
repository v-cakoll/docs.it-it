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
ms.openlocfilehash: a82f092a0f10fd621ac4facdee201fa239e1c1b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
#### <a name="parameters"></a>Parametri  
 `flags`  
 [in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) membro di enumerazione che specifica se una variabile aggiunta nella strumentazione ReJIT del profiler è incluso nel frame.  
  
 `dwIndex`  
 [in] Indice della variabile locale nello stack frame del linguaggio intermedio.  
  
 `ppValue`  
 [out] Un puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato.  
  
## <a name="remarks"></a>Note  
 Questo metodo è simile al [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) metodo, ad eccezione del fatto che si accede, facoltativamente, una variabile aggiunta nella strumentazione ReJIT del profiler. Chiamare questo metodo con un `flags` valore `ILCODE_ORIGINAL_IL` è equivalente alla chiamata [GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md); se il metodo è instrumentato con variabili locali aggiuntive, tali variabili non sono accessibili. `ILCODE_REJIT_IL` consente al debugger di accedere alle variabili locali aggiunte nella strumentazione ReJIT del profiler. Se il linguaggio intermedio non è instrumentato, il metodo restituisce `E_INVALIDARG`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: Una Guida dettagliata](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
