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
ms.openlocfilehash: e41bb5ca0fdd999692395239304f50a6f745a4f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088274"
---
# <a name="icordebugarrayvalue-interface"></a>Interfaccia ICorDebugArrayValue

Sottoclasse di ICorDebugHeapValue che rappresenta una matrice unidimensionale o multidimensionale.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBaseIndicies](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|Ottiene l'indice di base di ogni dimensione nella matrice.|  
|[Metodo GetCount](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|Ottiene il numero totale di elementi nella matrice.|  
|[Metodo GetDimensions](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|Ottiene le dimensioni della matrice.|  
|[Metodo GetElement](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|Ottiene un valore che rappresenta l'elemento specificato nella matrice.|  
|[Metodo GetElementAtPosition](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come matrice unidimensionale in base zero.|  
|[Metodo GetElementType](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|Ottiene il tipo semplice degli elementi nella matrice.|  
|[Metodo GetRank](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|Ottiene il numero di dimensioni nella matrice.|  
|[Metodo HasBaseIndicies](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|Determina se la matrice dispone di indici di base.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugArrayValue` supporta matrici unidimensionali e multidimensionali.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
