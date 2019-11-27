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
ms.openlocfilehash: e73c95d8c720ed3263d6a66c48bdb5b5582eb686
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442188"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="9fddc-102">Metodo IMetaDataDispenserEx::FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="9fddc-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="9fddc-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="9fddc-103">This method is not implemented.</span></span> <span data-ttu-id="9fddc-104">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="9fddc-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fddc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9fddc-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="9fddc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9fddc-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="9fddc-107">in Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9fddc-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="9fddc-108">in Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9fddc-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="9fddc-109">in Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9fddc-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="9fddc-110">in Nome del modulo.</span><span class="sxs-lookup"><span data-stu-id="9fddc-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="9fddc-111">in Assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="9fddc-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="9fddc-112">out Nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9fddc-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9fddc-113">in Dimensione, in byte, del `szName`.</span><span class="sxs-lookup"><span data-stu-id="9fddc-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="9fddc-114">out Numero di caratteri effettivamente restituiti in `szName`.</span><span class="sxs-lookup"><span data-stu-id="9fddc-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fddc-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9fddc-115">Requirements</span></span>  
 <span data-ttu-id="9fddc-116">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fddc-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fddc-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9fddc-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9fddc-118">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9fddc-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9fddc-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fddc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fddc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9fddc-120">See also</span></span>

- [<span data-ttu-id="9fddc-121">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="9fddc-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="9fddc-122">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="9fddc-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
