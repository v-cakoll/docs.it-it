---
title: Metodo IMetaDataEmit::DefineMethodImpl
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
ms.openlocfilehash: 64d76efa8c2f29fda559e5c84217b865540027ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175824"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="34a51-102">Metodo IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="34a51-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="34a51-103">Crea una definizione per l'implementazione di un metodo ereditato da un'interfaccia e restituisce un token a tale definizione di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="34a51-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34a51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34a51-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34a51-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34a51-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="34a51-106">[in] Token `mdTypedef` della classe di implementazione.</span><span class="sxs-lookup"><span data-stu-id="34a51-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="34a51-107">[in] Token `mdMethodDef` `mdMemberRef` o del corpo del codice.</span><span class="sxs-lookup"><span data-stu-id="34a51-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="34a51-108">[in] Token `mdMethodDef` `mdMemberRef` o del metodo di interfaccia implementato.</span><span class="sxs-lookup"><span data-stu-id="34a51-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34a51-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34a51-109">Requirements</span></span>  
 <span data-ttu-id="34a51-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34a51-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34a51-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34a51-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34a51-112">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="34a51-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34a51-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34a51-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34a51-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34a51-114">See also</span></span>

- [<span data-ttu-id="34a51-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="34a51-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="34a51-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="34a51-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
