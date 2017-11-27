---
title: Funzione GetAppIdAuthority
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type: COM
f1_keywords: GetAppIdAuthority
helpviewer_keywords: GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8a403b4e77a847321d0fe884c5a5d274f0538a64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="getappidauthority-function"></a>Funzione GetAppIdAuthority
Ottiene un puntatore a un [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) che gestisce le chiavi per le identità delle applicazioni e i riferimenti.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppIAppIdAuthority`  
 [out] L'oggetto restituito `IAppIdAuthority` puntatore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IAppIdAuthority (interfaccia)](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
