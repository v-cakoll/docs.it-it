---
title: Interfaccia ICLRStrongName2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d4e1274f675ae9289faa6c530d34cd61d033aa07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongname2-interface"></a>Interfaccia ICLRStrongName2
Fornisce la possibilità di creare nomi sicuri tramite il gruppo di SHA-2 degli algoritmi di Hash di protezione (SHA-256, SHA-384 e SHA-512).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo StrongNameGetPublicKeyEx](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.|  
|[Metodo StrongNameSignatureVerificationEx2](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|Verifica la firma di un assembly con nome sicuro e fornisce il mapping tra la chiave ECMA a una chiave reale.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
