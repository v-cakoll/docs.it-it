---
title: Metodo INotifyConnection2::RegisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442072"
---
# <a name="inotifyconnection2registernotifysource-method"></a>Metodo INotifyConnection2::RegisterNotifySource
Installa un'origine di notifica specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `in_pNotifySource`  
 in Specifica l'oggetto da utilizzare come origine della notifica.  
  
 `out_ppNotifySink`  
 out Riceve l'oggetto da utilizzare come sink di notifica.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia INotifyConnection2](inotifyconnection2-interface.md)
- [Interfaccia INotifySource2](inotifysource2-interface.md)
- [Interfaccia INotifySink2](inotifysink2-interface.md)
- [Metodo UnregisterNotifySource](inotifyconnection2-unregisternotifysource-method.md)
