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
ms.openlocfilehash: 6558d27f10e5b93dfe2c8053bb96434d49fd3c4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537209"
---
# <a name="resolvetypelib-method"></a>Metodo ResolveTypeLib
Risolve il nome semplice di una libreria dei tipi, restituendo il relativo percorso completo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bstrSimpleName`  
 [in] Oggetto [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il nome della libreria dei tipi semplice.  
  
 `tlbid`  
 [in] GUID assegnato alla libreria dei tipi nel Registro di sistema.  
  
 `lcid`  
 [in] L'ID di localizzazione della libreria dei tipi.  
  
 `wMajorVersion`  
 [in] Il numero di versione principale della libreria dei tipi. Ad esempio, per la versione *x. y*, il numero di versione principale viene *x*.  
  
 `wMinorVersion`  
 [in] Il numero di versione secondaria della libreria dei tipi. Ad esempio, per la versione *x. y*, è il numero di versione secondaria *y*.  
  
 `syskind`  
 [in] Oggetto [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag che identifica l'ambiente operativo. I valori comuni sono SYS_WIN32 e SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Un puntatore a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominato nel `bstrSimpleName` parametro.  
  
## <a name="remarks"></a>Note  
 Il `ResolveTypeLib` metodo viene chiamato dal [LoadTypeLibWithResolver (funzione)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) durante [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) l'elaborazione.  
  
 Le implementazioni personalizzate di questa interfaccia devono restituire un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominato nel `bstrSimpleName` parametro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef.idl, TlbRef.h  
  
 **Libreria:** TlbRef.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
