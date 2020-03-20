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
ms.openlocfilehash: 4c68754bc44fe035fd8e7143c52895928beae395
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175590"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="93281-102">Metodo IMetaDataEmit::SetPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="93281-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="93281-103">Imposta o modifica le funzionalità della firma PInvoke di un metodo, come definito da una precedente chiamata a [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="93281-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93281-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93281-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93281-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93281-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="93281-106">[in] Oggetto `mdToken` a cui si applicano le informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="93281-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="93281-107">[in] Flag utilizzati da PInvoke per eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="93281-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="93281-108">Si tratta di `CorPinvokeMap` una maschera di bit di valori.</span><span class="sxs-lookup"><span data-stu-id="93281-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="93281-109">[in] Nome dell'esportazione di destinazione nella DLL nativa.</span><span class="sxs-lookup"><span data-stu-id="93281-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="93281-110">[in] Token `mdModuleRef` per la DLL non gestita di destinazione.</span><span class="sxs-lookup"><span data-stu-id="93281-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93281-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93281-111">Requirements</span></span>  
 <span data-ttu-id="93281-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93281-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93281-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="93281-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93281-114">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93281-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93281-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93281-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93281-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93281-116">See also</span></span>

- [<span data-ttu-id="93281-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="93281-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="93281-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="93281-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
