---
title: Metodo IGCThreadControl::ThreadIsBlockingForSuspension
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.ThreadIsBlockingForSuspension
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 815ed06cb5772e7d04002f9d0d31bd971f2d345a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a>Metodo IGCThreadControl::ThreadIsBlockingForSuspension
Notifica all'host che il thread che effettua la chiamata sta per bloccare, ad esempio per un'operazione di garbage collection o un'altra sospensione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a>Note  
 L'host può scegliere all'interno di `ThreadIsBlockingForSuspension` callback se ripianificare un thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IGCThreadControl (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
