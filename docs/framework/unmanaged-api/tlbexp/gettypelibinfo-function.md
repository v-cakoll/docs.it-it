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
ms.openlocfilehash: d8ea7df9396e9199d04ad5609daa9d2b01761f36
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798887"
---
# <a name="gettypelibinfo-function"></a>Funzione GetTypeLibInfo
Restituisce informazioni sulla libreria dei tipi specificata esaminando la relativa struttura [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Nome del file della libreria dei tipi.  
  
 `pTypeLibID`  
 out GUID della libreria dei tipi.  
  
 `pTypeLibLCID`  
 out ID di localizzazione della libreria dei tipi.  
  
 `pTypeLibPlatform`  
 out Flag [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) che identifica il sistema operativo di destinazione per la libreria dei tipi. I valori comuni sono SYS_WIN32 e SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 out Numero di versione principale della libreria dei tipi. Per la versione *x. y*, ad esempio, il numero di versione principale è *x*.  
  
 `pTypeLibMinorVer`  
 out Numero della versione secondaria della libreria dei tipi. Per la versione *x. y*, ad esempio, il numero di versione secondario è *y*.  
  
## <a name="remarks"></a>Note  
 La `GetTypeLibInfo` funzione viene chiamata da [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../tools/tlbexp-exe-type-library-exporter.md). Questo strumento genera una libreria dei tipi che descrive i tipi in un assembly Common Language Runtime (CLR).  
  
 Se un parametro è null, la funzione restituisce un `HRESULT` di `E_POINTER`. In caso contrario, restituirà `S_OK`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. h  
  
 **Libreria** TlbRef.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di supporto Tlbexp](index.md)
- [LoadTypeLibEx (funzione)](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
