---
title: Metodo ICorDebugGuidToTypeEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGuidToTypeEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 277661c8c5490b5c1f68cb8fdaf1eff5a020250f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugguidtotypeenumnext-method"></a>Metodo ICorDebugGuidToTypeEnum::Next
Ottiene il numero specificato di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) istanze che eseguono il mapping di GUID al tipo di informazioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `celt`  
 [in] Il numero di oggetti di mapping di tipo GUID devono essere recuperate.  
  
 `values`  
 [out] Matrice di puntatori, ognuno dei quali punta a un [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) oggetto che esegue il mapping di un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID oggetto ICorDebugType corrispondente.  
  
 `pceltFetched`  
 [out] Un puntatore al numero di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) oggetti effettivamente restituiti nella `values`.  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugGuidToTypeEnum (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
