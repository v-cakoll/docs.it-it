---
title: Puntatore alla funzione FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8062ab151efc6175aa68cb0563cd2ad042ee9cd8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189053"
---
# <a name="flockclrversioncallback-function-pointer"></a>Puntatore alla funzione FLockClrVersionCallback
Punta a una funzione che il common language runtime (CLR) chiama per indicare che l'inizializzazione è avviato o completato.  
  
 Questo puntatore a funzione è stato deprecato nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a>Note  
 Questa funzione viene implementata dall'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorWks.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
