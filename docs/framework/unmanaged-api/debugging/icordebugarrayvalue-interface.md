---
title: Interfaccia ICorDebugArrayValue
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue interface
helpviewer_keywords:
- ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type:
- apiref
ms.openlocfilehash: bd1e86b83c43af20604416f158ab9e74f399821b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894960"
---
# <a name="icordebugarrayvalue-interface"></a>Interfaccia ICorDebugArrayValue

Sottoclasse di ICorDebugHeapValue che rappresenta una matrice unidimensionale o multidimensionale.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBaseIndicies](icordebugarrayvalue-getbaseindicies-method.md)|Ottiene l'indice di base di ogni dimensione nella matrice.|  
|[Metodo GetCount](icordebugarrayvalue-getcount-method.md)|Ottiene il numero totale di elementi nella matrice.|  
|[Metodo GetDimensions](icordebugarrayvalue-getdimensions-method.md)|Ottiene le dimensioni della matrice.|  
|[Metodo GetElement](icordebugarrayvalue-getelement-method.md)|Ottiene un valore che rappresenta l'elemento specificato nella matrice.|  
|[Metodo GetElementAtPosition](icordebugarrayvalue-getelementatposition-method.md)|Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come matrice unidimensionale in base zero.|  
|[Metodo GetElementType](icordebugarrayvalue-getelementtype-method.md)|Ottiene il tipo semplice degli elementi nella matrice.|  
|[Metodo GetRank](icordebugarrayvalue-getrank-method.md)|Ottiene il numero di dimensioni nella matrice.|  
|[Metodo HasBaseIndicies](icordebugarrayvalue-hasbaseindicies-method.md)|Determina se la matrice dispone di indici di base.|  
  
## <a name="remarks"></a>Osservazioni  
 `ICorDebugArrayValue`supporta matrici unidimensionali e multidimensionali.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
