---
title: Funzione GetTypeLibInfo
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d12cbb66464baba4ee706ccb076764fbf025fc5f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148538"
---
# <a name="gettypelibinfo-function"></a>Funzione GetTypeLibInfo
Restituisce informazioni sulla libreria dei tipi specificata esaminando relativa [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) struttura.  
  
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
  
## <a name="parameters"></a>Parametri  
 `szFile`  
 [in] Il nome di file della libreria dei tipi.  
  
 `pTypeLibID`  
 [out] Il GUID della libreria dei tipi.  
  
 `pTypeLibLCID`  
 [out] L'ID di localizzazione della libreria dei tipi.  
  
 `pTypeLibPlatform`  
 [out] Oggetto [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag che identifica il sistema operativo di destinazione della libreria dei tipi. I valori comuni sono SYS_WIN32 e SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] Il numero di versione principale della libreria dei tipi. Ad esempio, per la versione *x. y*, il numero di versione principale viene *x*.  
  
 `pTypeLibMinorVer`  
 [out] Il numero di versione secondaria della libreria dei tipi. Ad esempio, per la versione *x. y*, è il numero di versione secondaria *y*.  
  
## <a name="remarks"></a>Note  
 Il `GetTypeLibInfo` funzione viene chiamata dal [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Questo strumento genera una libreria dei tipi che descrive i tipi in un assembly di common language runtime (CLR).  
  
 Se qualsiasi parametro è null, la funzione restituisce un `HRESULT` di `E_POINTER`. In caso contrario restituirà `S_OK`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef.h  
  
 **Libreria:** TlbRef.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [Funzione LoadTypeLibEx dell'](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
