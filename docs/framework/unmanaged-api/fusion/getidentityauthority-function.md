---
title: Funzione GetIdentityAuthority
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f29246bdb929c8eaf1ebce726164d5cd2269b9f1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796864"
---
# <a name="getidentityauthority-function"></a>Funzione GetIdentityAuthority
Ottiene un puntatore a un'istanza di [IIdentityAuthority](iidentityauthority-interface.md) che gestisce le chiavi per gli oggetti di codice.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a>Parametri  
 `ppIIdentityAuthority`  
 out Puntatore restituito `IIdentityAuthority` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IIdentityAuthority](iidentityauthority-interface.md)
- [Funzioni statiche globali Fusion](fusion-global-static-functions.md)
