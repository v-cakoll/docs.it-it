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
ms.openlocfilehash: 582e28c18f36b253425b1e0a2034cdd262fddd57
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213738"
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
 in Membro di enumerazione [ILCodeKind](ilcodekind-enumeration.md) che specifica se il linguaggio intermedio (il) definito dalla richiesta ReJIT del profiler è incluso nel frame.  
  
 `ppCode`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta il codice in esecuzione nel stack frame.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è simile al metodo [ICorDebugFrame:: GetCode](icordebugframe-getcode-method.md) , ad eccezione del fatto che accede facoltativamente al codice definito dalla richiesta ReJIT del profiler. La chiamata di questo metodo con un `flags` valore `ILCODE_ORIGINAL_IL` equivale alla chiamata a [GetCode](icordebugframe-getcode-method.md); se il metodo è instrumentato, il relativo il non sarà accessibile. `ILCODE_REJIT_IL` consente al debugger di accedere al linguaggio intermedio definito dalla richiesta ReJIT del profiler. Se il linguaggio intermedio non è instrumentato, `ppCode` è **null**e il metodo restituisce `S_OK` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [ReJIT: Guida alle procedure](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
