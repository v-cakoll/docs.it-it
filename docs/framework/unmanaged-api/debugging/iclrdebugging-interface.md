---
title: Interfaccia ICLRDebugging
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging
helpviewer_keywords: ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac3e061b95faafeec3c3d233ab54f128a23c3264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugging-interface"></a>Interfaccia ICLRDebugging
Fornisce metodi che gestiscono il caricamento e lo scaricamento di moduli per il debug.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[OpenVirtualProcess (metodo)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|Ottiene l'interfaccia "ICorDebugProcess" che corrisponde a un modulo common language runtime (CLR) caricato nel processo.|  
|[CanUnloadNow (metodo)](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|Determina se una libreria che ha fornita un [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interfaccia è ancora in uso o può essere scaricato.|  
  
## <a name="remarks"></a>Note  
 È possibile ottenere un'istanza di `ICLRDebugging` interfaccia utilizzando il [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) (funzione).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
