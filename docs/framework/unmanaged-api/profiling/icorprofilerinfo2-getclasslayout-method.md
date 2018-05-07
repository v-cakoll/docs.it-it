---
title: Metodo ICorProfilerInfo2::GetClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassLayout
helpviewer_keywords:
- ICorProfilerInfo2::GetClassLayout method [.NET Framework profiling]
- GetClassLayout method, ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: a3a36987-5666-4e2f-95b5-d0cb246502ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b826e9c30fbf7007ac6b0093608ab7d926cc499
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2getclasslayout-method"></a>Metodo ICorProfilerInfo2::GetClassLayout
Ottiene le informazioni sul layout, in memoria, dei campi definiti dalla classe specificata. In altri termini, questo metodo ottiene gli offset dei campi della classe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetClassLayout(  
    [in]  ClassID classID,  
    [in, out] COR_FIELD_OFFSET rFieldOffset[],  
    [in]  ULONG cFieldOffset,  
    [out] ULONG *pcFieldOffset,  
    [out] ULONG *pulClassSize);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classID`  
 [in] ID della classe per la quale verrà recuperato il layout.  
  
 `rFieldOffset`  
 [in, out] Matrice di [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) strutture, ognuno dei quali contiene i token e gli offset dei campi della classe.  
  
 `cFieldOffset`  
 [in] Dimensione della matrice `rFieldOffset`.  
  
 `pcFieldOffset`  
 [out] Puntatore al numero complessivo di elementi disponibili. Se il parametro `cFieldOffset` è 0, questo valore indica il numero degli elementi necessari.  
  
 `pulClassSize`  
 [out] Puntatore a una posizione che contiene la dimensione, in byte, della classe.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetClassLayout` restituisce solo i campi definiti dalla classe stessa. Se anche la classe padre della classe ha definito alcuni campi, il profiler deve chiamare il metodo `GetClassLayout` sulla classe padre per ottenere quei campi.  
  
 Se si usa `GetClassLayout` con le classi di stringa, il metodo non riuscirà e invierà un codice di errore E_INVALIDARG. Utilizzare [ICorProfilerInfo2:: GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) per ottenere informazioni sul layout di una stringa. `GetClassLayout` non riuscirà, inoltre, quando chiamato con una classe della matrice.  
  
 Dopo il completamento del metodo `GetClassLayout`, è necessario verificare che il buffer `rFieldOffset` sia abbastanza grande per contenere tutte le strutture `COR_FIELD_OFFSET` disponibili. A tale scopo, confrontare il valore a cui punta il parametro `pcFieldOffset` con la dimensione del parametro `rFieldOffset` diviso la dimensione di una struttura `COR_FIELD_OFFSET`. Se il parametro `rFieldOffset` non è abbastanza grande, allocare un buffer `rFieldOffset` più grande, aggiornare `cFieldOffset` con la nuova dimensione e chiamare nuovamente il metodo `GetClassLayout`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetClassLayout` con un buffer `rFieldOffset` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcFieldOffset` e chiamare nuovamente `GetClassLayout`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
