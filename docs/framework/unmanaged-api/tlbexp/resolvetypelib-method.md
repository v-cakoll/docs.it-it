---
title: Metodo ResolveTypeLib
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f274befe78e45be3e53335572fd9c1e0b401fd3
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040183"
---
# <a name="resolvetypelib-method"></a>Metodo ResolveTypeLib
Risolve il nome semplice di una libreria dei tipi restituendo il percorso completo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a>Parametri  
 `bstrSimpleName`  
 in [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il nome semplice della libreria dei tipi.  
  
 `tlbid`  
 in GUID assegnato alla libreria dei tipi nel registro di sistema.  
  
 `lcid`  
 in ID di localizzazione della libreria dei tipi.  
  
 `wMajorVersion`  
 in Numero di versione principale della libreria dei tipi. Per la versione *x. y*, ad esempio, il numero di versione principale è *x*.  
  
 `wMinorVersion`  
 in Numero della versione secondaria della libreria dei tipi. Per la versione *x. y*, ad esempio, il numero di versione secondario è *y*.  
  
 `syskind`  
 in Flag [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) che identifica l'ambiente operativo. I valori comuni sono SYS_WIN32 e SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 out Puntatore a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominata nel `bstrSimpleName` parametro.  
  
## <a name="remarks"></a>Note  
 Il `ResolveTypeLib` metodo viene chiamato dalla [funzione LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) durante l'elaborazione di [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) .  
  
 Le implementazioni personalizzate di questa interfaccia devono restituire un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominata nel `bstrSimpleName` parametro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. idl, TlbRef. h  
  
 **Libreria** TlbRef.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
