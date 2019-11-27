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
ms.openlocfilehash: 99f529a151a42cf4a9ee1f74bd3a76a5b6b1b35f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445266"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="c5518-102">Metodo IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="c5518-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="c5518-103">Crea una definizione per l'implementazione di un metodo ereditato da un'interfaccia e restituisce un token a tale definizione di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="c5518-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5518-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5518-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5518-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5518-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c5518-106">in Token `mdTypedef` della classe di implementazione.</span><span class="sxs-lookup"><span data-stu-id="c5518-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="c5518-107">in Token `mdMethodDef` o `mdMemberRef` del corpo del codice.</span><span class="sxs-lookup"><span data-stu-id="c5518-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="c5518-108">in Token `mdMethodDef` o `mdMemberRef` del metodo di interfaccia implementato.</span><span class="sxs-lookup"><span data-stu-id="c5518-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5518-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5518-109">Requirements</span></span>  
 <span data-ttu-id="c5518-110">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5518-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5518-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c5518-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5518-112">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c5518-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5518-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5518-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5518-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5518-114">See also</span></span>

- [<span data-ttu-id="c5518-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c5518-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c5518-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c5518-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
