---
title: Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
ms.openlocfilehash: c8313b7c97eb5d94424259dc91459f62e13368fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785599"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>Metodo ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
Chiamata eseguita da [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) per segnalare al debugger il risultato di un tentativo di enumerare un'area di memoria specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `address`  
 in Indirizzo iniziale dell'area di memoria che deve essere enumerata.  
  
 `size`  
 in Dimensione, in byte, dell'area di memoria.  
  
## <a name="remarks"></a>Note  
 Il metodo `ICLRDataEnumMemoryRegions::EnumMemoryRegions` chiamerà questo metodo di callback dopo ogni tentativo di enumerazione di un'area di memoria. L'enumerazione continuerà anche se il metodo restituisce un valore HRESULT che indica un errore.  
  
 Le aree segnalate da questo callback possono essere duplicati o aree sovrapposte.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)
