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
ms.openlocfilehash: 017c14e9170087f3c3c9de64f50d165fc91aa297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782409"
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
 in Membro di enumerazione [ILCodeKind](ilcodekind-enumeration.md) che specifica se una variabile aggiunta nella strumentazione ReJIT del profiler è inclusa nel frame.  
  
 `dwIndex`  
 [in] Indice della variabile locale nello stack frame del linguaggio intermedio.  
  
 `ppValue`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugValue" che rappresenta il valore recuperato.  
  
## <a name="remarks"></a>Note  
 Questo metodo è simile al metodo [GetLocalVariable](icordebugilframe-getlocalvariable-method.md) , ad eccezione del fatto che accede facoltativamente a una variabile aggiunta nella strumentazione ReJIT del profiler. La chiamata di questo metodo con un valore `flags` di `ILCODE_ORIGINAL_IL` equivale alla chiamata a [GetLocalVariable](icordebugilframe-getlocalvariable-method.md); Se il metodo è instrumentato con variabili locali aggiuntive, non è possibile accedere a tali variabili. `ILCODE_REJIT_IL` consente al debugger di accedere alle variabili locali aggiunte nella strumentazione ReJIT del profiler. Se il linguaggio intermedio non è instrumentato, il metodo restituisce `E_INVALIDARG`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [ReJIT: Guida alle procedure](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
