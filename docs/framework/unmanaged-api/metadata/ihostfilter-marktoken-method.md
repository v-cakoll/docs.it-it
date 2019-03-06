---
title: Metodo IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96f0b1648c8182b4d075a479f9bd376dbe33ef61
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487903"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="2b7ad-102">Metodo IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="2b7ad-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="2b7ad-103">Indica che il token di metadati specificato verrà elaborato.</span><span class="sxs-lookup"><span data-stu-id="2b7ad-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b7ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b7ad-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b7ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b7ad-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2b7ad-106">[in] Il token di metadati da elaborare.</span><span class="sxs-lookup"><span data-stu-id="2b7ad-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b7ad-107">Note</span><span class="sxs-lookup"><span data-stu-id="2b7ad-107">Remarks</span></span>  
 <span data-ttu-id="2b7ad-108">In genere, si vuole che un token per l'elaborazione se presente nell'ambito dei metadati.</span><span class="sxs-lookup"><span data-stu-id="2b7ad-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="2b7ad-109">Il `MarkToken` viene passato al motore di metadati tramite il [SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="2b7ad-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b7ad-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b7ad-110">Requirements</span></span>  
 <span data-ttu-id="2b7ad-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b7ad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b7ad-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2b7ad-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b7ad-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2b7ad-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b7ad-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b7ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7ad-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b7ad-115">See also</span></span>
- [<span data-ttu-id="2b7ad-116">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="2b7ad-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="2b7ad-117">Interfaccia IHostFilter</span><span class="sxs-lookup"><span data-stu-id="2b7ad-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
