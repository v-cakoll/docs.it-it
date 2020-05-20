---
title: Metodo INotifySink2::OnSyncCallOut
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
ms.openlocfilehash: ce0e192a9d7d5abf56a55f844cf886c386f1c563
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441994"
---
# <a name="inotifysink2onsynccallout-method"></a>Metodo INotifySink2::OnSyncCallOut
Viene richiamato quando una chiamata è out.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `in_CallID`  
 in ID della chiamata in uscita. Vedere [struttura CALL_ID](call-id-structure.md).  
  
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
