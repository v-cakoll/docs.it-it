---
title: Metodo INotifySink2::OnSyncCallExit
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
ms.openlocfilehash: f81ef3f5959e279b3fbbd94d6c5e8a2d86a38e7f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442020"
---
# <a name="inotifysink2onsynccallexit-method"></a>Metodo INotifySink2::OnSyncCallExit
Viene richiamato quando si esce da una chiamata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `in_CallID`  
 in ID della chiamata da chiudere. Vedere [struttura CALL_ID](call-id-structure.md).  
  
 `out_ppBuffer`  
 out Buffer di chiamata.  
  
 `out_pBufferSize`  
 out Dimensioni del buffer di chiamata, in byte.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia INotifySink2](inotifysink2-interface.md)
- [Interfaccia INotifySource2](inotifysource2-interface.md)
- [Interfaccia INotifyConnection2](inotifyconnection2-interface.md)
