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
ms.openlocfilehash: 7ba9f68e102696da107b5cb782c76cb55ed95ee6
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441968"
---
# <a name="inotifysource2setnotifyfilter-method"></a>Metodo INotifySource2::SetNotifyFilter
Assegna un filtro di notifica per l'utilizzo con questa origine.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `in_NotifyFilter`  
 in Combinazione bit per bit dei valori di enumerazione [NOTIFY_FILTER](notify-filter-enumeration.md) che identificano i callback per l'API del debugger.  
  
 `in_pUserThreadFilter`  
 in Puntatore a una struttura [USER_THREAD](user-thread-structure.md) che identifica i thread per l'API del debugger.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia INotifySource2](inotifysource2-interface.md)
- [Interfaccia INotifyConnection2](inotifyconnection2-interface.md)
- [Interfaccia INotifySink2](inotifysink2-interface.md)
