---
title: Metodo INotifySink2::OnSyncCallReturn
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
ms.openlocfilehash: ff1dabcfc366607639cd98be4392f8dd59dc83a1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442007"
---
# <a name="inotifysink2onsynccallreturn-method"></a>Metodo INotifySink2::OnSyncCallReturn
Viene richiamato quando una chiamata restituisce.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `in_CallID`  
 in ID della chiamata restituita da. Vedere [struttura CALL_ID](call-id-structure.md).  
  
 `in_pBuffer`  
 in Buffer di chiamata.  
  
 `in_BufferSize`  
 in Dimensioni del buffer di chiamata, in byte.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia INotifySink2](inotifysink2-interface.md)
- [Interfaccia INotifySource2](inotifysource2-interface.md)
- [Interfaccia INotifyConnection2](inotifyconnection2-interface.md)
