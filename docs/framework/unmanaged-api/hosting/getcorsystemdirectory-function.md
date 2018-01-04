---
title: Funzione GetCORSystemDirectory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetCORSystemDirectory
helpviewer_keywords: GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02b695ac7f75dd38da8cd06e1444af4ae425ebd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getcorsystemdirectory-function"></a>Funzione GetCORSystemDirectory
Restituisce la directory di installazione di common language runtime (CLR) che viene caricato nel processo. La directory di installazione è completo, ad esempio, "c:\windows\microsoft.net\framework\v1.0.3705".  
  
 Questa funzione è deprecata. Viene sostituito dal [GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) fornito nel metodo il [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
#### <a name="parameters"></a>Parametri  
 `pbuffer`  
 [out] Un buffer in cui il runtime restituisce una stringa che contiene il nome completo della directory di installazione per il runtime che viene caricato nel processo. Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriata per la versione più recente del runtime installata nel computer.  
  
 `cchBuffer`  
 [in] Le dimensioni, in byte, di `pbuffer`.  
  
 `dwLength`  
 [out] Il numero di caratteri restituiti in `pbuffer`.  
  
## <a name="remarks"></a>Note  
  
> [!CAUTION]
>  Non utilizzare questa funzione in processi che eseguono la versione 4 di CLR. Se una versione precedente di CLR è installata nel computer, questa funzione restituisce la directory di installazione per tale versione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di hosting CLR deprecate](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
