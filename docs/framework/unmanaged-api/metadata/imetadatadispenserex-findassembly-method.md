---
title: Metodo IMetaDataDispenserEx::FindAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssembly
helpviewer_keywords:
- FindAssembly method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssembly method [.NET Framework metadata]
ms.assetid: 3afe7252-5f28-48d9-a74d-1927566c404c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d204ec29304fe0c4596950cd17c48d0c1d2ac616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050155"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="1b90d-102">Metodo IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="1b90d-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="1b90d-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="1b90d-103">This method is not implemented.</span></span> <span data-ttu-id="1b90d-104">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="1b90d-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b90d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b90d-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="1b90d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b90d-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="1b90d-107">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1b90d-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="1b90d-108">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1b90d-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="1b90d-109">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="1b90d-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="1b90d-110">[in] L'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="1b90d-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="1b90d-111">[out] Il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1b90d-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1b90d-112">[in] Le dimensioni, in byte, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="1b90d-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="1b90d-113">[out] Il numero di caratteri effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="1b90d-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b90d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b90d-114">Requirements</span></span>  
 <span data-ttu-id="1b90d-115">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b90d-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b90d-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1b90d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b90d-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1b90d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1b90d-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b90d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b90d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b90d-119">See also</span></span>

- [<span data-ttu-id="1b90d-120">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="1b90d-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="1b90d-121">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="1b90d-121">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
