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
ms.openlocfilehash: e77344a99189ec8e234129262d45698c794dc249
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788520"
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
  
## <a name="remarks"></a>Note  
 Questo metodo è simile al metodo [ICorDebugFrame:: GetCode](icordebugframe-getcode-method.md) , ad eccezione del fatto che accede facoltativamente al codice definito dalla richiesta ReJIT del profiler. La chiamata di questo metodo con un valore `flags` di `ILCODE_ORIGINAL_IL` equivale alla chiamata a [GetCode](icordebugframe-getcode-method.md); Se il metodo è instrumentato, il relativo IL non sarà accessibile. `ILCODE_REJIT_IL` consente al debugger di accedere al linguaggio intermedio definito dalla richiesta ReJIT del profiler. Se il linguaggio intermedio non è instrumentato, `ppCode` è **null**e il metodo restituisce `S_OK`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [ReJIT: Guida alle procedure](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
