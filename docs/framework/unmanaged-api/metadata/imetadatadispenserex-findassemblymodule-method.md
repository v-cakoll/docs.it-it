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
ms.openlocfilehash: 365bea0bdd32fa1b408ba0bfdf100cc443b5d419
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446225"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="10ed1-102">Metodo IMetaDataDispenserEx::FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="10ed1-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="10ed1-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="10ed1-103">This method is not implemented.</span></span> <span data-ttu-id="10ed1-104">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="10ed1-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ed1-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10ed1-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="10ed1-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="10ed1-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="10ed1-107">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="10ed1-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="10ed1-108">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="10ed1-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="10ed1-109">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="10ed1-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="10ed1-110">[in] Il nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="10ed1-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="10ed1-111">[in] L'assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="10ed1-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="10ed1-112">[out] Il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="10ed1-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="10ed1-113">[in] Le dimensioni, in byte, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="10ed1-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="10ed1-114">[out] Il numero di caratteri effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="10ed1-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10ed1-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="10ed1-115">Requirements</span></span>  
 <span data-ttu-id="10ed1-116">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10ed1-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ed1-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="10ed1-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10ed1-118">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="10ed1-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10ed1-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ed1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ed1-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ed1-120">See Also</span></span>  
 [<span data-ttu-id="10ed1-121">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="10ed1-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="10ed1-122">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="10ed1-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
