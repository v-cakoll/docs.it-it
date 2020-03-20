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
ms.openlocfilehash: e371330336002c673f2c54d882e70dbed41b743c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175837"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="471ee-102">Metodo IMetaDataEmit::DefineMemberRef</span><span class="sxs-lookup"><span data-stu-id="471ee-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="471ee-103">Definisce un riferimento a un membro di un modulo esterno all'ambito corrente e ottiene un token per tale definizione di riferimento.</span><span class="sxs-lookup"><span data-stu-id="471ee-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="471ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="471ee-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="471ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="471ee-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="471ee-106">[in] Token per la classe o l'interfaccia del membro di destinazione, se il membro non è globale; se il membro è `mdModuleRef` globale, il token per l'altro file.</span><span class="sxs-lookup"><span data-stu-id="471ee-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="471ee-107">[in] Nome del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="471ee-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="471ee-108">[in] Firma del membro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="471ee-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="471ee-109">[in] Numero di byte `pvSigBlob`in .</span><span class="sxs-lookup"><span data-stu-id="471ee-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="471ee-110">[fuori] Token `mdMemberRef` assegnato.</span><span class="sxs-lookup"><span data-stu-id="471ee-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="471ee-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="471ee-111">Requirements</span></span>  
 <span data-ttu-id="471ee-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="471ee-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="471ee-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="471ee-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="471ee-114">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="471ee-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="471ee-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="471ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="471ee-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="471ee-116">See also</span></span>

- [<span data-ttu-id="471ee-117">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="471ee-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="471ee-118">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="471ee-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
