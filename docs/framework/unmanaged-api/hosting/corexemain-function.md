---
title: Funzione _CorExeMain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f5c0909db10c7bf8e15a7af998b78e0a193a908
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corexemain-function"></a>Funzione _CorExeMain
Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e inizia l'esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a>Note  
 Questa funzione viene chiamata dal caricatore in processi creati dagli assembly eseguibile gestito. Per gli assembly DLL, il caricatore chiama la [CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) funzione alternativa.  
  
 Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file di immagine.  
  
 In Windows 98, Windows ME, Windows NT e Windows 2000, la `_CorExeMain` funzione viene chiamata indirettamente tramite una correzione nel caricatore del sistema operativo. In tutte le altre versioni di Windows, viene chiamato direttamente dal caricatore del sistema operativo.  
  
 Per ulteriori informazioni, vedere la sezione osservazioni nel [CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
