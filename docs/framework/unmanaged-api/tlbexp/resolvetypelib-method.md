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
ms.openlocfilehash: 46cd8b5c22f48ba45c4da7fa8876d6807a21f2b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124147"
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
 out Puntatore a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominata nel parametro `bstrSimpleName`.  
  
## <a name="remarks"></a>Note  
 Il metodo `ResolveTypeLib` viene chiamato dalla [funzione LoadTypeLibWithResolver](loadtypelibwithresolver-function.md) durante l'elaborazione di [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../tools/tlbexp-exe-type-library-exporter.md) .  
  
 Le implementazioni personalizzate di questa interfaccia devono restituire un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominata nel parametro `bstrSimpleName`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** TlbRef. idl, TlbRef. h  
  
 **Libreria:** TlbRef. lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzioni di supporto Tlbexp](index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
