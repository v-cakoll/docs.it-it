---
title: Metodo IMetaDataEmit::DefinePinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePinvokeMap
helpviewer_keywords:
- DefinePinvokeMap method [.NET Framework metadata]
- IMetaDataEmit::DefinePinvokeMap method [.NET Framework metadata]
ms.assetid: 03abf921-5154-4070-88fa-10b7092901fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6421ca47c3439d94c1ae86caaf2198298872d53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777528"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="58093-102">Metodo IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="58093-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="58093-103">Imposta le funzionalità di firma PInvoke del metodo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="58093-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58093-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58093-104">Syntax</span></span>  
  
```cpp  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58093-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58093-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="58093-106">[in] Il token per il metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="58093-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="58093-107">[in] Flag utilizzate da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="58093-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="58093-108">[in] Nome della destinazione di esportazione metodo in una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="58093-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="58093-109">[in] Il token per la destinazione di DLL native.</span><span class="sxs-lookup"><span data-stu-id="58093-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58093-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58093-110">Requirements</span></span>  
 <span data-ttu-id="58093-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58093-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58093-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="58093-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58093-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="58093-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58093-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58093-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58093-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58093-115">See also</span></span>

- [<span data-ttu-id="58093-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="58093-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="58093-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="58093-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
