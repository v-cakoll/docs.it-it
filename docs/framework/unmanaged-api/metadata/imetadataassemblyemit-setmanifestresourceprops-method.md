---
title: Metodo IMetaDataAssemblyEmit::SetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6fbc3f41e95730e93bd907762dd8cd4205037c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187304"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="93b9d-102">Metodo IMetaDataAssemblyEmit::SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="93b9d-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="93b9d-103">Modifica la struttura dei metadati `ManifestResource` specificata.</span><span class="sxs-lookup"><span data-stu-id="93b9d-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93b9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93b9d-104">Syntax</span></span>  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93b9d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93b9d-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="93b9d-106">[in] Il token che specifica il `ManifestResource` modifica della struttura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="93b9d-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="93b9d-107">[in] Il token, di tipo `File` o `AssemblyRef`, che esegue il mapping al provider di risorse.</span><span class="sxs-lookup"><span data-stu-id="93b9d-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="93b9d-108">[in] L'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="93b9d-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="93b9d-109">[in] Combinazione bit per bit dei valori di flag che specificano gli attributi della risorsa.</span><span class="sxs-lookup"><span data-stu-id="93b9d-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93b9d-110">Note</span><span class="sxs-lookup"><span data-stu-id="93b9d-110">Remarks</span></span>  
 <span data-ttu-id="93b9d-111">Per creare un `ManifestResource` struttura dei metadati, usare il [DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="93b9d-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93b9d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93b9d-112">Requirements</span></span>  
 <span data-ttu-id="93b9d-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93b9d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93b9d-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="93b9d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93b9d-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="93b9d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93b9d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93b9d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93b9d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93b9d-117">See also</span></span>

- [<span data-ttu-id="93b9d-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="93b9d-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
