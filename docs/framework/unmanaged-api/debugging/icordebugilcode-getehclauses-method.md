---
title: Metodo ICorDebugILCode::GetEHClauses
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: ac9a4e4b54b302afeae4ede1dd574c15ded3ff12
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788610"
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
  
## <a name="parameters"></a>Parametri  
 `cClauses`  
 [in] Capacità di memoria della matrice `clauses`. Per altre informazioni, vedere la sezione Osservazioni.  
  
 `pcClauses`  
 [out] Numero di clausole le cui informazioni vengono scritte nella matrice `clauses`.  
  
 clausole  
 out Matrice di oggetti [CorDebugEHClause](cordebugehclause-structure.md) che contengono informazioni sulle clausole di gestione delle eccezioni definite per questo il.  
  
## <a name="remarks"></a>Note  
 Se `cClauses` è 0 e `pcClauses` è diverso da**null**, `pcClauses` viene impostato sul numero di clausole di gestione delle eccezioni disponibili. Se `cClauses` è diverso da zero, rappresenta la capacità di memoria della matrice `clauses`. Quando il metodo restituisce un valore, `clauses` contiene un massimo di `cClauses` elementi e `pcClauses` viene impostato sul numero di clausole effettivamente scritte nella matrice `clauses`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILCode](icordebugilcode-interface.md)
- [Struttura CorDebugEHClause](cordebugehclause-structure.md)
- [Interfacce di debug](debugging-interfaces.md)
