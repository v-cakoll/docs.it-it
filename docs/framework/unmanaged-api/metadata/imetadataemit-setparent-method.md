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
ms.openlocfilehash: da82950ea1a0da81c77d173be9ab45dcb3001bfe
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007832"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="b4c89-102">Metodo IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="b4c89-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="b4c89-103">Stabilisce che il membro specificato, in base a quanto definito da una chiamata precedente a [IMetaDataEmit::D efinememberref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), è un membro del tipo specificato, in base a quanto definito da una chiamata precedente a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="b4c89-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4c89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4c89-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4c89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4c89-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="b4c89-106">in `mdMemberRef`Token per ricevere un nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="b4c89-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="b4c89-107">in Oggetto `mdToken` per il nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="b4c89-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4c89-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4c89-108">Requirements</span></span>  
 <span data-ttu-id="b4c89-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c89-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4c89-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b4c89-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4c89-111">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b4c89-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4c89-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c89-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4c89-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4c89-113">See also</span></span>

- [<span data-ttu-id="b4c89-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b4c89-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b4c89-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b4c89-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
