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
ms.openlocfilehash: 84b2c0571a7991829e65b45759bd61fa4009aa71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445877"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="6e17b-102">Metodo IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="6e17b-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="6e17b-103">Imposta o modifica le funzionalità di firma del metodo PInvoke, come definito da una precedente chiamata a [IMetaDataEmit:: DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="6e17b-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e17b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e17b-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e17b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6e17b-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6e17b-106">[in] Il `mdToken` a cui mapping si applicano informazioni.</span><span class="sxs-lookup"><span data-stu-id="6e17b-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="6e17b-107">[in] Flag utilizzati da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="6e17b-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="6e17b-108">Si tratta di una maschera di bit di `CorPinvokeMap` valori.</span><span class="sxs-lookup"><span data-stu-id="6e17b-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="6e17b-109">[in] Nome della destinazione dell'esportazione nella DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="6e17b-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="6e17b-110">[in] Il `mdModuleRef` token per la destinazione di DLL non gestita.</span><span class="sxs-lookup"><span data-stu-id="6e17b-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e17b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e17b-111">Requirements</span></span>  
 <span data-ttu-id="6e17b-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e17b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e17b-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6e17b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e17b-114">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6e17b-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e17b-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e17b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e17b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e17b-116">See Also</span></span>  
 [<span data-ttu-id="6e17b-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6e17b-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="6e17b-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6e17b-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
