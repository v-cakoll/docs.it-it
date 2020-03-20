---
title: Metodo IMetaDataEmit::GetTokenFromTypeSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
ms.openlocfilehash: 8c609d730297881c0ac20dca8569f0e9492638e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175720"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="bb438-102">Metodo IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="bb438-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="bb438-103">Ottiene un token di metadati per il tipo con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="bb438-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb438-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb438-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb438-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb438-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="bb438-106">[in] Firma da definire.</span><span class="sxs-lookup"><span data-stu-id="bb438-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="bb438-107">[in] Numero di byte `pvSig`in .</span><span class="sxs-lookup"><span data-stu-id="bb438-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="bb438-108">[fuori] Token `mdTypeSpec` assegnato.</span><span class="sxs-lookup"><span data-stu-id="bb438-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb438-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb438-109">Requirements</span></span>  
 <span data-ttu-id="bb438-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb438-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb438-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb438-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb438-112">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bb438-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb438-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb438-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb438-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb438-114">See also</span></span>

- [<span data-ttu-id="bb438-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bb438-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bb438-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bb438-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
