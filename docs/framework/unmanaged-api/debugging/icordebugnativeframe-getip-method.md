---
title: Metodo ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: 53576ca938074fb7e5974a96bb53a84cb6ed67ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213595"
---
# <a name="icordebugnativeframegetip-method"></a>Metodo ICorDebugNativeFrame::GetIP
Ottiene la posizione di offset del codice nativo a cui è attualmente impostato il puntatore all'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnOffset`  
 out Puntatore alla posizione di offset nel codice nativo.  
  
## <a name="remarks"></a>Osservazioni  
 Se la stack frame rappresentata da questo "ICorDebugNativeFrame" è attiva, l'offset corrisponde all'indirizzo dell'istruzione successiva da eseguire. Se questo stack frame non è attivo, l'offset è l'indirizzo dell'istruzione successiva da eseguire quando il stack frame viene riattivato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
