---
title: ICorDebugArrayValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue interface
helpviewer_keywords: ICorDebugArrayValue interface [.NET Framework debugging]
ms.assetid: dc437751-7093-44e2-bfdc-191d9ce3c192
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13e226ccdcd6becc98d524c429b5cadae8d19c3e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvalue-interface1"></a>ICorDebugArrayValue Interface1
Sottoclasse di ICorDebugHeapValue che rappresenta una matrice unidimensionale o multidimensionale.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetBaseIndicies (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getbaseindicies-method.md)|Ottiene l'indice di base di ciascuna dimensione della matrice.|  
|[GetCount (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getcount-method.md)|Ottiene il numero totale di elementi nella matrice.|  
|[GetDimensions (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getdimensions-method.md)|Ottiene le dimensioni della matrice.|  
|[GetElement (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelement-method.md)|Ottiene un valore che rappresenta l'elemento specificato nella matrice.|  
|[GetElementAtPosition (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementatposition-method.md)|Ottiene l'elemento in corrispondenza della posizione specificata, considerando la matrice come una matrice unidimensionale in base zero.|  
|[GetElementType (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getelementtype-method.md)|Ottiene il tipo semplice degli elementi nella matrice.|  
|[GetRank (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-getrank-method.md)|Ottiene il numero di dimensioni nella matrice.|  
|[HasBaseIndicies (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-hasbaseindicies-method.md)|Determina se la matrice include gli indici di base.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugArrayValue`supporta matrici unidimensionali e multidimensionali.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
