---
title: Metodo ICorDebugILFrame4::GetCodeEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.GetLocalVariableEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5d1d480014e90d3fea9790b10e0dace5a0847ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parametri  
 `flags`  
 [in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) membro di enumerazione che specifica se il linguaggio intermedio (IL) definito dalla richiesta ReJIT del profiler è incluso nel frame.  
  
 `ppCode`  
 [out] Un puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta il codice che è in esecuzione questo stack frame.  
  
## <a name="remarks"></a>Note  
 Questo metodo è simile al [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) metodo, ad eccezione del fatto che si accede facoltativamente codice definito dalla richiesta ReJIT del profiler. Chiamare questo metodo con un `flags` valore `ILCODE_ORIGINAL_IL` è equivalente alla chiamata [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); se il metodo è instrumentato, relativo linguaggio intermedio non saranno più accessibile. `ILCODE_REJIT_IL` consente al debugger di accedere al linguaggio intermedio definito dalla richiesta ReJIT del profiler. Se il linguaggio intermedio non è instrumentato, `ppCode` è **null**, e il metodo restituisce `S_OK`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugILFrame4](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: Una Guida dettagliata](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
