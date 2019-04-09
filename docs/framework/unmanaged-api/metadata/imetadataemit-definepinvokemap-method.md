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
ms.openlocfilehash: 15fd75ae807ee5cd7f94f6e650639c3be0628429
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136539"
---
# <a name="imetadataemitdefinepinvokemap-method"></a><span data-ttu-id="39062-102">Metodo IMetaDataEmit::DefinePinvokeMap</span><span class="sxs-lookup"><span data-stu-id="39062-102">IMetaDataEmit::DefinePinvokeMap Method</span></span>
<span data-ttu-id="39062-103">Imposta le funzionalità di firma PInvoke del metodo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="39062-103">Sets features of the PInvoke signature of the method referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39062-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39062-104">Syntax</span></span>  
  
```  
HRESULT DefinePinvokeMap (   
    [in]  mdToken            tk,   
    [in]  DWORD              dwMappingFlags,   
    [in]  LPCWSTR            szImportName,   
    [in]  mdModuleRef        mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39062-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39062-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="39062-106">[in] Il token per il metodo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="39062-106">[in] The token for the target method.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="39062-107">[in] Flag utilizzate da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="39062-107">[in] Flags used by PInvoke to do the mapping.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="39062-108">[in] Nome della destinazione di esportazione metodo in una DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="39062-108">[in] The name of the target export method in an unmanaged DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="39062-109">[in] Il token per la destinazione di DLL native.</span><span class="sxs-lookup"><span data-stu-id="39062-109">[in] The token for the target native DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39062-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39062-110">Requirements</span></span>  
 <span data-ttu-id="39062-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39062-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39062-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="39062-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39062-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="39062-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="39062-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="39062-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="39062-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39062-115">See also</span></span>

- [<span data-ttu-id="39062-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="39062-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="39062-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="39062-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
