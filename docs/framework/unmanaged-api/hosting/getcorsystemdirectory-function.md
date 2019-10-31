---
title: Funzione GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: 63fb505a92683fda21b6e71a6ca891ca35afba1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136416"
---
# <a name="getcorsystemdirectory-function"></a>Funzione GetCORSystemDirectory
Restituisce la directory di installazione del Common Language Runtime (CLR) che viene caricata nel processo. La directory di installazione è completamente qualificata, ad esempio "c:\Windows\Microsoft.net\framework\v1.0.3705".  
  
 Questa funzione è deprecata. Viene sostituito dal metodo [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) fornito nella .NET Framework 4.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Parametri  
 `pbuffer`  
 out Buffer in cui il runtime restituisce una stringa che contiene il nome completo della directory di installazione per il runtime caricato nel processo. Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installato nel computer.  
  
 `cchBuffer`  
 in Dimensione, in byte, del `pbuffer`.  
  
 `dwLength`  
 out Numero di caratteri restituiti in `pbuffer`.  
  
## <a name="remarks"></a>Note  
  
> [!CAUTION]
> Non utilizzare questa funzione nei processi che eseguono la versione 4 di CLR. Se nel computer è installata una versione precedente di CLR, questa funzione restituisce la directory di installazione per tale versione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
