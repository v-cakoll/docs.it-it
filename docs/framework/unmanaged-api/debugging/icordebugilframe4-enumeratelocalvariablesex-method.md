---
title: Metodo ICorDebugILFrame4::EnumerateLocalVariablesEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
ms.openlocfilehash: aef28af3eff6aba03003f156b9226b61a8e72d5b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213751"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a>Metodo ICorDebugILFrame4::EnumerateLocalVariablesEx
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Ottiene un enumeratore per le variabili locali nel frame e, facoltativamente, include le variabili aggiunte nella strumentazione ReJIT del profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `flags`  
 in Membro di enumerazione [ILCodeKind](ilcodekind-enumeration.md) che specifica se le variabili aggiunte nella strumentazione ReJIT del profiler sono incluse nel frame.  
  
 `ppValueEnum`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugValueEnum" che rappresenta l'enumeratore per le variabili locali in questo frame.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo è simile al metodo [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) , ad eccezione del fatto che accede facoltativamente alle variabili aggiunte nella strumentazione ReJIT del profiler. L'impostazione `flags` di su `ILCODE_ORIGINAL_IL` equivale alla chiamata di [ICorDebugILFrame:: EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md). Impostare `flags` su `ILCODE_REJIT_IL` consente al debugger di accedere alle variabili locali aggiunte nella strumentazione ReJIT del profiler. Se il linguaggio intermedio (IL) non è instrumentato, l'enumerazione è vuota e il metodo restituisce `S_OK`.  
  
 L'enumeratore potrebbe non includere tutte le variabili locali nel metodo in esecuzione, in quanto alcune potrebbero essere inattive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugILFrame4](icordebugilframe4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [ReJIT: Guida alle procedure](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
