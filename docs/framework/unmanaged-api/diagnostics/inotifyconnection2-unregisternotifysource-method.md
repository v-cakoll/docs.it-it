---
title: Metodo INotifyConnection2::UnregisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 9d0fcdcd4fe1561f7565586e3327c6d3d7e0fe0a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442046"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>Metodo INotifyConnection2::UnregisterNotifySource
Rimuove un oggetto origine notifica specificato dalla connessione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `in_pNotifySource`  
 in Oggetto notifica di cui annullare la registrazione.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia INotifyConnection2](inotifyconnection2-interface.md)
- [Interfaccia INotifySource2](inotifysource2-interface.md)
- [Interfaccia INotifySink2](inotifysink2-interface.md)
- [Metodo RegisterNotifySource](inotifyconnection2-registernotifysource-method.md)
