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
ms.openlocfilehash: 52375486eb9d7780a51808dedc5f876587efb115
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444564"
---
# <a name="ihostfiltermarktoken-method"></a><span data-ttu-id="d92a9-102">Metodo IHostFilter::MarkToken</span><span class="sxs-lookup"><span data-stu-id="d92a9-102">IHostFilter::MarkToken Method</span></span>
<span data-ttu-id="d92a9-103">Indica che verrà elaborato il token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="d92a9-103">Indicates that the specified metadata token will be processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d92a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d92a9-104">Syntax</span></span>  
  
```  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d92a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d92a9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="d92a9-106">[in] Il token di metadati da elaborare.</span><span class="sxs-lookup"><span data-stu-id="d92a9-106">[in] The metadata token to be processed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d92a9-107">Note</span><span class="sxs-lookup"><span data-stu-id="d92a9-107">Remarks</span></span>  
 <span data-ttu-id="d92a9-108">In genere, si desidera un token da elaborare, se presente nell'ambito dei metadati.</span><span class="sxs-lookup"><span data-stu-id="d92a9-108">Typically, you want a token to be processed if it is in the metadata scope.</span></span> <span data-ttu-id="d92a9-109">Il `MarkToken` viene passato al motore di metadati tramite il [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="d92a9-109">The `MarkToken` method is passed to the metadata engine via the [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d92a9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d92a9-110">Requirements</span></span>  
 <span data-ttu-id="d92a9-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d92a9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d92a9-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d92a9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d92a9-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d92a9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d92a9-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d92a9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92a9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d92a9-115">See Also</span></span>  
 [<span data-ttu-id="d92a9-116">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="d92a9-116">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="d92a9-117">Interfaccia IHostFilter</span><span class="sxs-lookup"><span data-stu-id="d92a9-117">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)
