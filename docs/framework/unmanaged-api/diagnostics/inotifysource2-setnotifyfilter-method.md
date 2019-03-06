---
title: Metodo INotifySource2::SetNotifyFilter
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e5e2d0ed5ba5411f637c8370d366a96f0e028838
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484621"
---
# <a name="inotifysource2setnotifyfilter-method"></a>Metodo INotifySource2::SetNotifyFilter
Assegna un filtro di notifica per l'uso con questa origine.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `in_NotifyFilter`  
 [in] Una combinazione bit per bit del [NOTIFY_FILTER](../../../../docs/framework/unmanaged-api/diagnostics/notify-filter-enumeration.md) valori di enumerazione che identificano i callback per l'API del debugger.  
  
 `in_pUserThreadFilter`  
 [in] Un puntatore a un [USER_THREAD](../../../../docs/framework/unmanaged-api/diagnostics/user-thread-structure.md) struttura che identifica i thread per l'API del debugger.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2.idl  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia INotifySource2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [Interfaccia INotifyConnection2](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [Interfaccia INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
