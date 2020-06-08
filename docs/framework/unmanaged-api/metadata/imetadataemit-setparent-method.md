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
ms.openlocfilehash: d821413e67b36392d936499cd22f2e065f1556ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503848"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="9ff6c-102">Metodo IMetaDataEmit::SetParent</span><span class="sxs-lookup"><span data-stu-id="9ff6c-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="9ff6c-103">Stabilisce che il membro specificato, in base a quanto definito da una chiamata precedente a [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md), è un membro del tipo specificato, in base a quanto definito da una chiamata precedente a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="9ff6c-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ff6c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ff6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9ff6c-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="9ff6c-106">in `mdMemberRef`Token per ricevere un nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="9ff6c-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="9ff6c-107">in Oggetto `mdToken` per il nuovo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="9ff6c-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ff6c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9ff6c-108">Requirements</span></span>  
 <span data-ttu-id="9ff6c-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ff6c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ff6c-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9ff6c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9ff6c-111">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9ff6c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ff6c-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ff6c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff6c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ff6c-113">See also</span></span>

- [<span data-ttu-id="9ff6c-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="9ff6c-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9ff6c-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="9ff6c-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
