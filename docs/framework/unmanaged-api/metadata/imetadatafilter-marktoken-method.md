---
title: Metodo IMetaDataFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::MarkToken
helpviewer_keywords:
- IMetaDataFilter::MarkToken method [.NET Framework metadata]
- MarkToken method, IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: bd492834-6529-4d39-b93d-f8cdbd3e297f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97f184bae4628f2aa357644188594396468671ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444152"
---
# <a name="imetadatafiltermarktoken-method"></a><span data-ttu-id="6acc4-102">Metodo IMetaDataFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="6acc4-102">IMetaDataFilter::MarkToken Method</span></span>
<span data-ttu-id="6acc4-103">Imposta un valore che indica che il token di metadati specificato è stato elaborato.</span><span class="sxs-lookup"><span data-stu-id="6acc4-103">Sets a value indicating that the specified metadata token has been processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acc4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6acc4-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in] mdToken   tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6acc4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6acc4-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="6acc4-106">[in] Token da contrassegnare come elaborato.</span><span class="sxs-lookup"><span data-stu-id="6acc4-106">[in] The token to mark as processed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6acc4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6acc4-107">Requirements</span></span>  
 <span data-ttu-id="6acc4-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6acc4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6acc4-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6acc4-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6acc4-110">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6acc4-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6acc4-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6acc4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6acc4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6acc4-112">See Also</span></span>  
 [<span data-ttu-id="6acc4-113">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="6acc4-113">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
