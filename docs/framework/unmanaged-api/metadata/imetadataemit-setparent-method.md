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
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175603"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="ff3be-102">Metodo IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="ff3be-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="ff3be-103">Stabilisce che il membro specificato, come definito da una precedente chiamata a [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), è un membro del tipo specificato, come definito da una precedente chiamata a [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="ff3be-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff3be-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff3be-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff3be-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff3be-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="ff3be-106">[in] Token `mdMemberRef` per la ricezione di un nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="ff3be-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="ff3be-107">[in] Oggetto `mdToken` per il nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="ff3be-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff3be-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ff3be-108">Requirements</span></span>  
 <span data-ttu-id="ff3be-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff3be-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff3be-110">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ff3be-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff3be-111">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff3be-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff3be-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff3be-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3be-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff3be-113">See also</span></span>

- [<span data-ttu-id="ff3be-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ff3be-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ff3be-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ff3be-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
