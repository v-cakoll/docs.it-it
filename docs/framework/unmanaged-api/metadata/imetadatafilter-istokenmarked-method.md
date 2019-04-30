---
title: Metodo IMetaDataFilter::IsTokenMarked
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6969f2c1df9b5b04122ed6aef550697171123cf5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992498"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="41f9a-102">Metodo IMetaDataFilter::IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="41f9a-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="41f9a-103">Ottiene un valore che indica se il token di metadati specificato è stato contrassegnato come elaborato.</span><span class="sxs-lookup"><span data-stu-id="41f9a-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41f9a-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41f9a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41f9a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="41f9a-106">[in] Il token da esaminare per un segno di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="41f9a-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="41f9a-107">[out] Valore che rappresenta `true` se `tk` è stato elaborato; in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="41f9a-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41f9a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41f9a-108">Requirements</span></span>  
 <span data-ttu-id="41f9a-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41f9a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41f9a-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41f9a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41f9a-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="41f9a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41f9a-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41f9a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f9a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41f9a-113">See also</span></span>

- [<span data-ttu-id="41f9a-114">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="41f9a-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
