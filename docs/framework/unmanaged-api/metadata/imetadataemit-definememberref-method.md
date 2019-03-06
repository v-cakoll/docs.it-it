---
title: Metodo IMetaDataEmit::DefineMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ad2b3e5c452a5fc79e7a1cc0342cfc1d119a5fbd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481989"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="c5b5a-102">Metodo IMetaDataEmit::DefineMemberRef</span><span class="sxs-lookup"><span data-stu-id="c5b5a-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="c5b5a-103">Definisce un riferimento a un membro di un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione.</span><span class="sxs-lookup"><span data-stu-id="c5b5a-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5b5a-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5b5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5b5a-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="c5b5a-106">[in] Token per la classe o interfaccia, il membro di destinazione se il membro non è globale; Se il membro è globale, il `mdModuleRef` token per gli altri file.</span><span class="sxs-lookup"><span data-stu-id="c5b5a-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="c5b5a-107">[in] Nome del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5b5a-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c5b5a-108">[in] La firma del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5b5a-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c5b5a-109">[in] Il numero di byte in `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="c5b5a-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="c5b5a-110">[out] Il `mdMemberRef` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="c5b5a-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5b5a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5b5a-111">Requirements</span></span>  
 <span data-ttu-id="c5b5a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5b5a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5b5a-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c5b5a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5b5a-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c5b5a-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5b5a-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5b5a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b5a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5b5a-116">See also</span></span>
- [<span data-ttu-id="c5b5a-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c5b5a-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c5b5a-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c5b5a-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
