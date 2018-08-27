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
ms.openlocfilehash: be2558e760be8519e528baeff438273c8871f320
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924469"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="25bd3-102">Metodo ResolveTypeLib</span><span class="sxs-lookup"><span data-stu-id="25bd3-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="25bd3-103">Risolve il nome semplice di una libreria dei tipi, restituendo il relativo percorso completo.</span><span class="sxs-lookup"><span data-stu-id="25bd3-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25bd3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25bd3-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="25bd3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25bd3-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="25bd3-106">[in] Oggetto [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il nome della libreria dei tipi semplice.</span><span class="sxs-lookup"><span data-stu-id="25bd3-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="25bd3-107">[in] GUID assegnato alla libreria dei tipi nel Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="25bd3-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="25bd3-108">[in] L'ID di localizzazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="25bd3-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="25bd3-109">[in] Il numero di versione principale della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="25bd3-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="25bd3-110">Ad esempio, per la versione *x. y*, il numero di versione principale viene *x*.</span><span class="sxs-lookup"><span data-stu-id="25bd3-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="25bd3-111">[in] Il numero di versione secondaria della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="25bd3-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="25bd3-112">Ad esempio, per la versione *x. y*, è il numero di versione secondaria *y*.</span><span class="sxs-lookup"><span data-stu-id="25bd3-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="25bd3-113">[in] Oggetto [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag che identifica l'ambiente operativo.</span><span class="sxs-lookup"><span data-stu-id="25bd3-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="25bd3-114">I valori comuni sono SYS_WIN32 e SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="25bd3-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="25bd3-115">[out] Un puntatore a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominato nel `bstrSimpleName` parametro.</span><span class="sxs-lookup"><span data-stu-id="25bd3-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25bd3-116">Note</span><span class="sxs-lookup"><span data-stu-id="25bd3-116">Remarks</span></span>  
 <span data-ttu-id="25bd3-117">Il `ResolveTypeLib` metodo viene chiamato dal [LoadTypeLibWithResolver (funzione)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) durante [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="25bd3-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="25bd3-118">Le implementazioni personalizzate di questa interfaccia devono restituire un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominato nel `bstrSimpleName` parametro.</span><span class="sxs-lookup"><span data-stu-id="25bd3-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25bd3-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25bd3-119">Requirements</span></span>  
 <span data-ttu-id="25bd3-120">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25bd3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25bd3-121">**Intestazione:** TlbRef.idl, TlbRef. H</span><span class="sxs-lookup"><span data-stu-id="25bd3-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="25bd3-122">**Libreria:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="25bd3-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="25bd3-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25bd3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25bd3-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25bd3-124">See Also</span></span>  
 [<span data-ttu-id="25bd3-125">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="25bd3-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="25bd3-126">LoadTypeLibEx dell'</span><span class="sxs-lookup"><span data-stu-id="25bd3-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
