---
title: Metodo IAssemblyCacheItem::Commit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCacheItem.Commit
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5a25f24fd1f09ebc1cda0442e41fde9eef059d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycacheitemcommit-method"></a>Metodo IAssemblyCacheItem::Commit
Esegue il commit il riferimento di assembly memorizzati nella cache in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwFlags`  
 [in] Flag definiti in Fusion.  
  
 `pulDisposition`  
 [out, facoltativo] Un valore che indica il risultato dell'operazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IAssemblyCacheItem (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
