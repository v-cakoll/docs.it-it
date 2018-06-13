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
ms.openlocfilehash: 5bf5149e8e42a810a6a490767638b374f66b5679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445864"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="49e79-102">Metodo IMetaDataFilter::IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="49e79-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="49e79-103">Ottiene un valore che indica se il token di metadati specificato è stato contrassegnato come elaborato.</span><span class="sxs-lookup"><span data-stu-id="49e79-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49e79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49e79-104">Syntax</span></span>  
  
```  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49e79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="49e79-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="49e79-106">[in] Token da esaminare per un segno di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="49e79-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="49e79-107">[out] Un valore che è `true` se `tk` è stato elaborato; in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="49e79-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49e79-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49e79-108">Requirements</span></span>  
 <span data-ttu-id="49e79-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49e79-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49e79-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49e79-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49e79-111">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="49e79-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49e79-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49e79-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49e79-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49e79-113">See Also</span></span>  
 [<span data-ttu-id="49e79-114">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="49e79-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
