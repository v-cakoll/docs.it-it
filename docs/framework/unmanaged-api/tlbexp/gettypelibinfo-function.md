---
title: Funzione GetTypeLibInfo
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
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f6b1ad18809b46b7a2b38137231028f696d51b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="gettypelibinfo-function"></a>Funzione GetTypeLibInfo
Restituisce informazioni sulla libreria dei tipi specificata esaminando il [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) struttura.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szFile`  
 [in] Il nome del file della libreria dei tipi.  
  
 `pTypeLibID`  
 [out] Il GUID della libreria dei tipi.  
  
 `pTypeLibLCID`  
 [out] L'ID di localizzazione della libreria dei tipi.  
  
 `pTypeLibPlatform`  
 [out] Oggetto [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) flag che identifica il sistema operativo di destinazione per la libreria dei tipi. Valori comuni sono SYS_WIN32 e SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] Il numero di versione principale della libreria dei tipi. Ad esempio, per la versione *x. y*, il numero di versione principale è *x*.  
  
 `pTypeLibMinorVer`  
 [out] Il numero di versione secondaria della libreria dei tipi. Ad esempio, per la versione *x. y*, il numero di versione secondaria è *y*.  
  
## <a name="remarks"></a>Note  
 Il `GetTypeLibInfo` funzione viene chiamata il [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Questo strumento genera una libreria dei tipi che descrive i tipi in un assembly di common language runtime (CLR).  
  
 Se qualsiasi parametro è null, la funzione restituisce un `HRESULT` di `E_POINTER`. In caso contrario restituirà `S_OK`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. H  
  
 **Libreria:** TlbRef. lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Funzione LoadTypeLibEx dell'](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
