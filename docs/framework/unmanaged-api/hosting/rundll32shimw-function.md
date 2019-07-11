---
title: Funzione RunDll32ShimW
ms.date: 03/30/2017
api_name:
- RunDll32ShimW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- RunDll32ShimW
helpviewer_keywords:
- RunDll32ShimW function [.NET Framework hosting]
ms.assetid: 9ea07b57-96e2-44df-8711-8fe6c119087f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 569efa9d14ef10d8c5cf735091778a6c78882815
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781169"
---
# <a name="rundll32shimw-function"></a>Funzione RunDll32ShimW
Esegue il comando specificato.  
  
 Questa funzione è stata deprecata in .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RunDll32ShimW (  
    [in] HWND        hwnd,  
    [in] HINSTANCE   hinst,  
    [in] LPCWSTR     lpszCmdLine,  
    [in] int         nCmdShow  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `hwnd`  
 [in] Handle per una finestra in cui verrà visualizzato l'output del comando.  
  
 `hinst`  
 [in] Handle per la raccolta che contiene il comando.  
  
 `lpszCmdLine`  
 [in] Stringa che specifica il comando da eseguire.  
  
 `nCmdShow`  
 [in] Valore intero che specifica la modalità di visualizzazione della finestra di output.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
