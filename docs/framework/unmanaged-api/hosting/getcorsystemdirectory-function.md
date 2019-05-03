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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 567e6533a9a9ac718f8b5acac769295c104f7f3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628099"
---
# <a name="getcorsystemdirectory-function"></a>Funzione GetCORSystemDirectory
Restituisce la directory di installazione di common language runtime (CLR) che viene caricato nel processo. La directory di installazione è completo, ad esempio, "c:\windows\microsoft.net\framework\v1.0.3705".  
  
 Questa funzione è deprecata. Viene sostituito dal [GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) metodo fornito nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a>Parametri  
 `pbuffer`  
 [out] Un buffer in cui il runtime restituisce una stringa che contiene il nome completo della directory di installazione per il runtime che viene caricato nel processo. Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriato per la versione più recente del runtime installata nel computer.  
  
 `cchBuffer`  
 [in] Le dimensioni, in byte, di `pbuffer`.  
  
 `dwLength`  
 [out] Il numero di caratteri restituiti nella `pbuffer`.  
  
## <a name="remarks"></a>Note  
  
> [!CAUTION]
>  Non usare questa funzione nei processi che eseguono la versione 4 di CLR. Se nel computer è installata una versione precedente di Common Language Runtime, questa funzione restituisce la directory di installazione per la versione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
