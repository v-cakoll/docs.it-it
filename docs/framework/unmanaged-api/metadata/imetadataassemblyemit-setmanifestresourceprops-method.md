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
ms.openlocfilehash: 9370b27fd385b0223b354365d64aa57048f4ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177833"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="5a417-102">Metodo IMetaDataAssemblyEmit::SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="5a417-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="5a417-103">Modifica la struttura dei metadati `ManifestResource` specificata.</span><span class="sxs-lookup"><span data-stu-id="5a417-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a417-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a417-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a417-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a417-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="5a417-106">[in] Token che specifica `ManifestResource` la struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="5a417-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="5a417-107">[in] Token di tipo `File` `AssemblyRef`o , che esegue il mapping al provider di risorse.</span><span class="sxs-lookup"><span data-stu-id="5a417-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="5a417-108">[in] Offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="5a417-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="5a417-109">[in] Combinazione bit per bit di valori flag che specificano gli attributi della risorsa.</span><span class="sxs-lookup"><span data-stu-id="5a417-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a417-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5a417-110">Remarks</span></span>  
 <span data-ttu-id="5a417-111">Per creare `ManifestResource` una struttura dei metadati, utilizzare il metodo [IMetaDataAssemblyEmit::DefineManifestResource.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)</span><span class="sxs-lookup"><span data-stu-id="5a417-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a417-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a417-112">Requirements</span></span>  
 <span data-ttu-id="5a417-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a417-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a417-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a417-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a417-115">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a417-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a417-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a417-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a417-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a417-117">See also</span></span>

- [<span data-ttu-id="5a417-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5a417-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
