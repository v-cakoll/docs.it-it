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
ms.openlocfilehash: 50aebb09924b93a622e5b7d84e65e41ee91f6018
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006194"
---
# <a name="imetadatadispenserexfindassembly-method"></a><span data-ttu-id="548ed-102">Metodo IMetaDataDispenserEx::FindAssembly</span><span class="sxs-lookup"><span data-stu-id="548ed-102">IMetaDataDispenserEx::FindAssembly Method</span></span>
<span data-ttu-id="548ed-103">Questo metodo non è implementato.</span><span class="sxs-lookup"><span data-stu-id="548ed-103">This method is not implemented.</span></span> <span data-ttu-id="548ed-104">Se chiamato, restituisce E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="548ed-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548ed-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="548ed-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="548ed-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="548ed-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="548ed-107">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="548ed-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="548ed-108">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="548ed-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="548ed-109">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="548ed-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="548ed-110">in Assembly da trovare.</span><span class="sxs-lookup"><span data-stu-id="548ed-110">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="548ed-111">out Nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="548ed-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="548ed-112">in Dimensione, in byte, di `szName` .</span><span class="sxs-lookup"><span data-stu-id="548ed-112">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="548ed-113">out Numero di caratteri effettivamente restituiti in `szName` .</span><span class="sxs-lookup"><span data-stu-id="548ed-113">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="548ed-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="548ed-114">Requirements</span></span>  
 <span data-ttu-id="548ed-115">**Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="548ed-115">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="548ed-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="548ed-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="548ed-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="548ed-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="548ed-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="548ed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548ed-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="548ed-119">See also</span></span>

- [<span data-ttu-id="548ed-120">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="548ed-120">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="548ed-121">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="548ed-121">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
