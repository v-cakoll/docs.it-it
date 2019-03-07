---
title: Metodo IMetaDataDispenserEx::FindAssemblyModule
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ccb6331399ef3479e43bdb9dc4a72b5fd196672c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495338"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="7baaf-102">Metodo IMetaDataDispenserEx::FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="7baaf-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="7baaf-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="7baaf-103">This method is not implemented.</span></span> <span data-ttu-id="7baaf-104">Se chiamato, viene restituito E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="7baaf-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7baaf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7baaf-105">Syntax</span></span>  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7baaf-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7baaf-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="7baaf-107">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7baaf-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="7baaf-108">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7baaf-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="7baaf-109">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="7baaf-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="7baaf-110">[in] Il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="7baaf-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="7baaf-111">[in] L'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="7baaf-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="7baaf-112">[out] Il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="7baaf-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7baaf-113">[in] Le dimensioni, in byte, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="7baaf-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="7baaf-114">[out] Il numero di caratteri effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="7baaf-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7baaf-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7baaf-115">Requirements</span></span>  
 <span data-ttu-id="7baaf-116">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7baaf-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7baaf-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7baaf-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7baaf-118">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7baaf-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7baaf-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7baaf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7baaf-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7baaf-120">See also</span></span>
- [<span data-ttu-id="7baaf-121">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="7baaf-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="7baaf-122">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="7baaf-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
