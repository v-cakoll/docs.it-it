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
ms.openlocfilehash: 09256deafdb42847f369664ec8c4bc96d72424d6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177606"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="f503f-102">Metodo IMetaDataEmit::GetTokenFromTypeSpec</span><span class="sxs-lookup"><span data-stu-id="f503f-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="f503f-103">Ottiene i metadati di un token per il tipo con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="f503f-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f503f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f503f-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f503f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f503f-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="f503f-106">[in] La firma definita.</span><span class="sxs-lookup"><span data-stu-id="f503f-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="f503f-107">[in] Il numero di byte in `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="f503f-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="f503f-108">[out] Il `mdTypeSpec` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="f503f-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f503f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f503f-109">Requirements</span></span>  
 <span data-ttu-id="f503f-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f503f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f503f-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f503f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f503f-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f503f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f503f-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f503f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f503f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f503f-114">See also</span></span>

- [<span data-ttu-id="f503f-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="f503f-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f503f-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="f503f-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
