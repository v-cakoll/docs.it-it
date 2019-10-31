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
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136509"
---
# <a name="flockclrversioncallback-function-pointer"></a>Puntatore alla funzione FLockClrVersionCallback
Punta a una funzione chiamata da Common Language Runtime (CLR) per indicare che l'inizializzazione è stata avviata o completata.  
  
 Questo puntatore a funzione è stato deprecato in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a>Note  
 Questa funzione viene implementata dall'host.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorWks. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
