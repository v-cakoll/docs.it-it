---
title: Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: e6cdc924df126e56d2e7c8c9cb8762ee88712fcc
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860692"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a>Metodo ICLRDataEnumMemoryRegions::EnumMemoryRegions
Enumera le aree di memoria specificate.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `callback`  
 in Puntatore a un'istanza di [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) che viene chiamata da questo metodo per ogni area di memoria enumerata per notificare al debugger il risultato.  
  
 L'enumerazione delle aree di memoria continua anche se il callback indica un errore.  
  
 `miniDumpFlags`  
 [in] Non utilizzato.  
  
 `clrFlags`  
 in Valore dell'enumerazione [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) che specifica le aree di memoria da enumerare.  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo usa l'istanza di [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) specificata per notificare al chiamante i risultati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** ClrData. idl, ClrData. h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRDataEnumMemoryRegions](iclrdataenummemoryregions-interface.md)
