---
title: Metodo IMetaDataEmit::SetPinvokeMap
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7248f4c78684f7211c7b7633095fdc3f3f2fb1f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658624"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="e275d-102">Metodo IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="e275d-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="e275d-103">Imposta o modifica le funzionalità di firma del metodo PInvoke, come definito da una chiamata precedente a [DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="e275d-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e275d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e275d-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e275d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e275d-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e275d-106">[in] Il `mdToken` al quale mapping informazioni si applicano.</span><span class="sxs-lookup"><span data-stu-id="e275d-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="e275d-107">[in] Flag utilizzate da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="e275d-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="e275d-108">Si tratta di una maschera di bit delle `CorPinvokeMap` valori.</span><span class="sxs-lookup"><span data-stu-id="e275d-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="e275d-109">[in] Il nome della destinazione dell'esportazione nella DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="e275d-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="e275d-110">[in] Il `mdModuleRef` token per la destinazione di DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="e275d-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e275d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e275d-111">Requirements</span></span>  
 <span data-ttu-id="e275d-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e275d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e275d-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e275d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e275d-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e275d-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e275d-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e275d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e275d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e275d-116">See also</span></span>
- [<span data-ttu-id="e275d-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e275d-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e275d-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e275d-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
