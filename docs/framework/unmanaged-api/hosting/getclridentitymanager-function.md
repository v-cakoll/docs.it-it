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
ms.openlocfilehash: 8b1e918edf641d38dd6b91d790bcaff8020293a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493266"
---
# <a name="getclridentitymanager-function"></a>Funzione GetCLRIdentityManager
Ottiene un puntatore a un'interfaccia che consente all'Common Language Runtime (CLR) di gestire le identità.  
  
 Questa funzione è stata deprecata nel .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `riid`  
 in Oggetto `REFIID` (un identificatore di interfaccia) che specifica l'interfaccia da ottenere. Questo valore deve essere IID_ICLRAssemblyIdentityManager o IID_ICLRHostBindingPolicyManager.  
  
 `ppManager`  
 out Puntatore all'indirizzo di un oggetto [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) o [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .  
  
## <a name="remarks"></a>Osservazioni  
 Chiamare la funzione [GetRealProcAddress](getrealprocaddress-function.md) per ottenere un puntatore alla `GetCLRIdentityManager` funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorWks. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](deprecated-clr-hosting-functions.md)
