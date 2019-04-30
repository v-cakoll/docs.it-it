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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe27d8a0508a13c1f54eef00d5119bec4daec4a7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043004"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="2bbdd-102">Metodo IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="2bbdd-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="2bbdd-103">Stabilisce che il membro specificato, come definito da una chiamata precedente a [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), è un membro del tipo specificato, come definito da una chiamata precedente a [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="2bbdd-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bbdd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bbdd-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bbdd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2bbdd-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="2bbdd-106">[in] Il `mdMemberRef` token per ricevere un nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="2bbdd-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="2bbdd-107">[in] Il `mdToken` per il nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="2bbdd-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bbdd-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2bbdd-108">Requirements</span></span>  
 <span data-ttu-id="2bbdd-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bbdd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bbdd-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2bbdd-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bbdd-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2bbdd-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bbdd-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bbdd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbdd-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bbdd-113">See also</span></span>

- [<span data-ttu-id="2bbdd-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2bbdd-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2bbdd-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2bbdd-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
