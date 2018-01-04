---
title: Metodo ResolveTypeLib
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ResolveTypeLib
api_location: tlbref.dll
f1_keywords: ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b668610f50c32373790130def17928b8b3b3d8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="resolvetypelib-method"></a>Metodo ResolveTypeLib
Risolve il nome semplice di una libreria dei tipi restituendo il percorso completo.  
  
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
 [in] Oggetto [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) che contiene il nome semplice della libreria dei tipi.  
  
 `tlbid`  
 [in] GUID assegnato alla libreria dei tipi nel Registro di sistema.  
  
 `lcid`  
 [in] L'ID di localizzazione della libreria dei tipi.  
  
 `wMajorVersion`  
 [in] Il numero di versione principale della libreria dei tipi. Ad esempio, per la versione *x. y*, il numero di versione principale è *x*.  
  
 `wMinorVersion`  
 [in] Il numero di versione secondaria della libreria dei tipi. Ad esempio, per la versione *x. y*, il numero di versione secondaria è *y*.  
  
 `syskind`  
 [in] Oggetto [SYSKIND](http://msdn.microsoft.com/en-us/662048b2-59a8-48ca-9e4f-2f9a5306faa1) flag che identifica il sistema operativo. Valori comuni sono SYS_WIN32 e SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Un puntatore a un [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) che contiene il percorso completo della libreria dei tipi denominato nel `bstrSimpleName` parametro.  
  
## <a name="remarks"></a>Note  
 Il `ResolveTypeLib` metodo viene chiamato dal [funzione LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) durante [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) l'elaborazione.  
  
 Le implementazioni personalizzate di questa interfaccia devono restituire un [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) che contiene il percorso completo della libreria dei tipi denominato nel `bstrSimpleName` parametro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef.idl, TlbRef. H  
  
 **Libreria:** TlbRef. lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzioni di supporto Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx dell'](http://msdn.microsoft.com/en-us/56a7f9e1-810b-4a42-aa4d-691f4304f5ef)
