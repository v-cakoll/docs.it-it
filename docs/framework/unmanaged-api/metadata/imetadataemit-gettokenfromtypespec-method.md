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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b0b7d0364b6f58579ee8573d168d6c8180ac9dff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444577"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="b3d1a-102">Metodo IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="b3d1a-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="b3d1a-103">Ottiene i metadati di un token per il tipo con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="b3d1a-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3d1a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3d1a-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3d1a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3d1a-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="b3d1a-106">[in] La firma viene definita.</span><span class="sxs-lookup"><span data-stu-id="b3d1a-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="b3d1a-107">[in] Il numero di byte in `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="b3d1a-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="b3d1a-108">[out] Il `mdTypeSpec` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="b3d1a-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3d1a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3d1a-109">Requirements</span></span>  
 <span data-ttu-id="b3d1a-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3d1a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3d1a-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b3d1a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b3d1a-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b3d1a-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3d1a-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3d1a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d1a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3d1a-114">See Also</span></span>  
 [<span data-ttu-id="b3d1a-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b3d1a-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b3d1a-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b3d1a-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
