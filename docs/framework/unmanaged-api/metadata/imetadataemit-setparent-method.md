---
title: Metodo IMetaDataEmit::SetParent
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: a73afaebc2943190eeeee50367ecd31f1fb59df1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432444"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="3a523-102">Metodo IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="3a523-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="3a523-103">Stabilisce che il membro specificato, in base a quanto definito da una chiamata precedente a [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), è un membro del tipo specificato, in base a quanto definito da una chiamata precedente a [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="3a523-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a523-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a523-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a523-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a523-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="3a523-106">in Token `mdMemberRef` per ricevere un nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="3a523-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="3a523-107">in `mdToken` per il nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="3a523-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a523-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a523-108">Requirements</span></span>  
 <span data-ttu-id="3a523-109">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a523-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a523-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3a523-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a523-111">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3a523-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a523-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a523-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a523-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a523-113">See also</span></span>

- [<span data-ttu-id="3a523-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3a523-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3a523-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3a523-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
