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
ms.openlocfilehash: 5ed5afbbf49b6680d00e78b6af3d45c6f0a7229d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004491"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="ccf2c-102">Metodo IMetaDataEmit::DefineMethodImpl</span><span class="sxs-lookup"><span data-stu-id="ccf2c-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="ccf2c-103">Crea una definizione per l'implementazione di un metodo ereditato da un'interfaccia e restituisce un token a tale definizione di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="ccf2c-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccf2c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccf2c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccf2c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ccf2c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ccf2c-106">in `mdTypedef`Token della classe di implementazione.</span><span class="sxs-lookup"><span data-stu-id="ccf2c-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="ccf2c-107">in `mdMethodDef`Token o `mdMemberRef` del corpo del codice.</span><span class="sxs-lookup"><span data-stu-id="ccf2c-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="ccf2c-108">in `mdMethodDef`Token o `mdMemberRef` del metodo di interfaccia implementato.</span><span class="sxs-lookup"><span data-stu-id="ccf2c-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccf2c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ccf2c-109">Requirements</span></span>  
 <span data-ttu-id="ccf2c-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccf2c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccf2c-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ccf2c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccf2c-112">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ccf2c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccf2c-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccf2c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccf2c-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccf2c-114">See also</span></span>

- [<span data-ttu-id="ccf2c-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="ccf2c-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ccf2c-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ccf2c-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
