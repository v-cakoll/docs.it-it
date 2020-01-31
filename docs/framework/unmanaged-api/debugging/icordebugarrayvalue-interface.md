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
ms.openlocfilehash: 0944f3379c18cba56ab65fe40a5b94a64d8a8991
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778195"
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
  
## <a name="remarks"></a>Note  
 `ICorDebugArrayValue` supporta matrici unidimensionali e multidimensionali.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
