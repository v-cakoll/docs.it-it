---
title: Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a284d7277aa2f8c474ca4aab3dd6208bc3b2bb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
Chiamato da [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare una determinata area di memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `address`  
 [in] L'indirizzo iniziale dell'area di memoria che è stato possibile enumerare.  
  
 `size`  
 [in] Le dimensioni in byte, dell'area di memoria.  
  
## <a name="remarks"></a>Note  
 Il `ICLRDataEnumMemoryRegions::EnumMemoryRegions` metodo chiamerà il metodo di callback dopo ogni tentativo di enumerare un'area di memoria. L'enumerazione continuerà anche se questo metodo restituisce un HRESULT che indica un errore.  
  
 Le aree segnalate da questo callback possono essere duplicati o le aree di sovrapposizione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData.idl, Clrdata. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRDataEnumMemoryRegionsCallback](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
