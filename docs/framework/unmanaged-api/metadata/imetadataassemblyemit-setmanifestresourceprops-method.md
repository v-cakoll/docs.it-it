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
ms.openlocfilehash: 74111a175b0decbc1beef7c8df5ade59d31d845b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009145"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="49fe5-102">Metodo IMetaDataAssemblyEmit::SetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="49fe5-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="49fe5-103">Modifica la struttura dei metadati `ManifestResource` specificata.</span><span class="sxs-lookup"><span data-stu-id="49fe5-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49fe5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49fe5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49fe5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49fe5-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="49fe5-106">in Token che specifica la `ManifestResource` struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="49fe5-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="49fe5-107">in Token, di tipo `File` o `AssemblyRef` , che esegue il mapping al provider di risorse.</span><span class="sxs-lookup"><span data-stu-id="49fe5-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="49fe5-108">in Offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="49fe5-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="49fe5-109">in Combinazione bit per bit di valori di flag che specificano gli attributi della risorsa.</span><span class="sxs-lookup"><span data-stu-id="49fe5-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49fe5-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="49fe5-110">Remarks</span></span>  
 <span data-ttu-id="49fe5-111">Per creare una `ManifestResource` struttura di metadati, usare il metodo [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) .</span><span class="sxs-lookup"><span data-stu-id="49fe5-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49fe5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49fe5-112">Requirements</span></span>  
 <span data-ttu-id="49fe5-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49fe5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49fe5-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49fe5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49fe5-115">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="49fe5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49fe5-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49fe5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49fe5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49fe5-117">See also</span></span>

- [<span data-ttu-id="49fe5-118">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="49fe5-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
