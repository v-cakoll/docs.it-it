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
ms.openlocfilehash: 4e2a78e2d049e952aa1be0b3a8fd640eb18d0320
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440576"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="30559-102">Metodo IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="30559-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="30559-103">Imposta o modifica le funzionalità della firma PInvoke di un metodo, come definito da una chiamata precedente a [IMetaDataEmit::D efinepinvokemap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="30559-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30559-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30559-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30559-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30559-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="30559-106">in `mdToken` a cui si applicano le informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="30559-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="30559-107">in Flag utilizzati da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="30559-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="30559-108">Si tratta di una maschera di maschera dei valori `CorPinvokeMap`.</span><span class="sxs-lookup"><span data-stu-id="30559-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="30559-109">in Nome dell'esportazione di destinazione nella DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="30559-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="30559-110">in Token `mdModuleRef` per la DLL non gestita di destinazione.</span><span class="sxs-lookup"><span data-stu-id="30559-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30559-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30559-111">Requirements</span></span>  
 <span data-ttu-id="30559-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30559-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30559-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="30559-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30559-114">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="30559-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30559-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30559-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30559-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30559-116">See also</span></span>

- [<span data-ttu-id="30559-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="30559-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="30559-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="30559-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
