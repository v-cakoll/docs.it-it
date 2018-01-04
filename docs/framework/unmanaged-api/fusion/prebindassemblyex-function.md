---
title: Funzione PreBindAssemblyEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PreBindAssemblyEx
api_location: fusion.dll
api_type: DLLExport
f1_keywords: PreBindAssemblyEx
helpviewer_keywords: PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05977db8e01d00af6e160cb2993867cf83eb24c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="prebindassemblyex-function"></a>Funzione PreBindAssemblyEx
Ottiene il nome visualizzato di post-criteri per un assembly.  
  
 Questa funzione supporta l'infrastruttura .NET Framework e non deve essere utilizzato direttamente dal codice.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parametri  
 `pAppCtx`  
 [in] Identifica il contesto dell'applicazione.  
  
 `pName`  
 [in] Identifica il nome dell'assembly.  
  
 `pAsmParent`  
 [in] Identifica l'assembly padre. Questo parametro viene ignorato.  
  
 `pwzRuntimeVersion`  
 [in] Identifica la versione di runtime.  
  
 `ppNamePostPolicy`  
 [out] Contiene il nome visualizzato di post-criteri.  
  
 `pvReserved`  
 [in] Riservato per l'estensibilità futura. `pvReserved`deve essere un riferimento null.  
  
## <a name="remarks"></a>Note  
 Il `ppNamePostPolicy` parametro di output viene impostato solo se la funzione restituisce HRESULT FUSION_E_REF_DEF_MISMATCH. In caso contrario, è null.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Fusion. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni statiche globali Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
