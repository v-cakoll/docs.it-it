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
ms.openlocfilehash: 64f1e2a8f05616c7ca84bc130428629b1176e985
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006181"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="9678b-102">Metodo IMetaDataDispenserEx::FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="9678b-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="9678b-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="9678b-103">This method is not implemented.</span></span> <span data-ttu-id="9678b-104">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9678b-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9678b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9678b-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="9678b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9678b-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="9678b-107">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9678b-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="9678b-108">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9678b-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="9678b-109">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9678b-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="9678b-110">in Nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="9678b-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="9678b-111">in Assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="9678b-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="9678b-112">out Nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9678b-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9678b-113">in Dimensione, in byte, di `szName` .</span><span class="sxs-lookup"><span data-stu-id="9678b-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="9678b-114">out Numero di caratteri effettivamente restituiti in `szName` .</span><span class="sxs-lookup"><span data-stu-id="9678b-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9678b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9678b-115">Requirements</span></span>  
 <span data-ttu-id="9678b-116">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9678b-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9678b-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9678b-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9678b-118">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9678b-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9678b-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9678b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9678b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9678b-120">See also</span></span>

- [<span data-ttu-id="9678b-121">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="9678b-121">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="9678b-122">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="9678b-122">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
