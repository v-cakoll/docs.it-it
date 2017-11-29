---
title: Metodo IMetaDataDispenserEx::FindAssembly
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.FindAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a70d1e2b3636a405fe28b84c2e76dd7264df4f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="c3eaf-102">Metodo IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="c3eaf-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="c3eaf-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-103">This method is not implemented.</span></span> <span data-ttu-id="c3eaf-104">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3eaf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3eaf-105">Syntax</span></span>  
  
```  
HRESULT FindAssembly(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3eaf-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3eaf-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="c3eaf-107">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="c3eaf-108">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="c3eaf-109">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="c3eaf-110">[in] L'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="c3eaf-111">[out] Il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c3eaf-112">[in] Le dimensioni, in byte, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="c3eaf-113">[out] Il numero di caratteri effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="c3eaf-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3eaf-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3eaf-114">Requirements</span></span>  
 <span data-ttu-id="c3eaf-115">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3eaf-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3eaf-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c3eaf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3eaf-117">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3eaf-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3eaf-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3eaf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3eaf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3eaf-119">See Also</span></span>  
 [<span data-ttu-id="c3eaf-120">IMetaDataDispenserEx (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3eaf-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="c3eaf-121">IMetaDataDispenser (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3eaf-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
