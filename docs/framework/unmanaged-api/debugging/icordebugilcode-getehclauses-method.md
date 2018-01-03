---
title: Metodo ICorDebugILCode::GetEHClauses
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILCode.GetEHClauses
api_location: mscordbi.dll
api_type: COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32b3a7bf7edaf15e44ea65e2d3b4f5037add8d09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilcodegetehclauses-method"></a>Metodo ICorDebugILCode::GetEHClauses
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Restituisce un puntatore a un elenco di clausole di gestione delle eccezioni (EH) definite per questo linguaggio intermedio (IL).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cClauses`  
 [in] Capacità di memoria della matrice `clauses`. Per altre informazioni, vedere la sezione Osservazioni.  
  
 `pcClauses`  
 [out] Numero di clausole le cui informazioni vengono scritte nella matrice `clauses`.  
  
 clausole  
 [out] Matrice di [CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) oggetti che contengono informazioni sulle clausole definite per questo livello di integrità di gestione delle eccezioni.  
  
## <a name="remarks"></a>Note  
 Se `cClauses` è 0 e `pcClauses` è non**null**, `pcClauses` è impostato sul numero di clausole di gestione delle eccezioni disponibile. Se `cClauses` è diverso da zero, rappresenta la capacità di memoria della matrice `clauses`. Quando il metodo restituisce un valore, `clauses` contiene un massimo di `cClauses` elementi e `pcClauses` viene impostato sul numero di clausole effettivamente scritte nella matrice `clauses`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [Struttura CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
