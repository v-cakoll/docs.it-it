---
title: Funzione CreateAssemblyEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyEnum
helpviewer_keywords: CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c229496a79b146b5dcac3d06fa3efd9237e39d3a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="createassemblyenum-function"></a>Funzione CreateAssemblyEnum
Ottiene un puntatore a un [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) istanza che può enumerare gli oggetti nell'assembly con l'oggetto specificato [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parametri  
 `pEnum`  
 [out] Puntatore a una posizione di memoria che contiene la richiesta `IAssemblyEnum` puntatore.  
  
 `pUnkReserved`  
 [in] Riservato per l'estensibilità futura. `pUnkReserved`deve essere un riferimento null.  
  
 `pName`  
 [in] Il `IAssemblyName` dell'assembly richiesto. Questo nome viene utilizzato per filtrare l'enumerazione. Può essere null per enumerare tutti gli assembly nella global assembly cache.  
  
 `dwFlags`  
 [in] Flag per la modifica di comportamento dell'enumeratore. Questo parametro contiene esattamente un bit di [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumerazione.  
  
 `pvReserved`  
 [in] Riservato per l'estensibilità futura. `pvReserved`deve essere un riferimento null.  
  
## <a name="remarks"></a>Note  
 Il `dwFlags` parametro contiene esattamente un bit di `ASM_CACHE_FLAGS` enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IAssemblyEnum (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [IAssemblyName (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
