---
title: Funzione GetCLRIdentityManager
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e18172ecf2d4300ae42cc42ecdb1783744cac105
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490427"
---
# <a name="getclridentitymanager-function"></a>Funzione GetCLRIdentityManager
Ottiene un puntatore a un'interfaccia che consente a common language runtime (CLR) per gestire le identità.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `riid`  
 [in] Oggetto `REFIID` (un identificatore di interfaccia) che specifica quale interfaccia da ottenere. Questo valore deve essere IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.  
  
 `ppManager`  
 [out] Un puntatore per l'indirizzo di una un' [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md) o un' [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) oggetto.  
  
## <a name="remarks"></a>Note  
 Chiamare il [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) per ottenere un puntatore a funzione di `GetCLRIdentityManager` (funzione).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorWks.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
