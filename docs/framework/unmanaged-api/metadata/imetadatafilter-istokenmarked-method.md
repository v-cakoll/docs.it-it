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
ms.openlocfilehash: 10f31d56a9727e99157f49038c19781f12cd9958
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440425"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="1aa2c-102">Metodo IMetaDataFilter::IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="1aa2c-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="1aa2c-103">Ottiene un valore che indica se il token di metadati specificato è stato contrassegnato come elaborato.</span><span class="sxs-lookup"><span data-stu-id="1aa2c-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa2c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1aa2c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aa2c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1aa2c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1aa2c-106">in Token da esaminare per un contrassegno di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="1aa2c-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="1aa2c-107">out Valore `true` se `tk` è stato elaborato. in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="1aa2c-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa2c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1aa2c-108">Requirements</span></span>  
 <span data-ttu-id="1aa2c-109">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aa2c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aa2c-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1aa2c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1aa2c-111">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1aa2c-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1aa2c-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aa2c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa2c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1aa2c-113">See also</span></span>

- [<span data-ttu-id="1aa2c-114">Interfaccia IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="1aa2c-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
