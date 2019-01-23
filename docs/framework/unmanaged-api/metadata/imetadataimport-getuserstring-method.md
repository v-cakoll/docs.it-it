---
title: Metodo IMetaDataImport::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e806bae1911ea6ffc5bb6e9af76d99524636d39e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491148"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="3f385-102">Metodo IMetaDataImport::GetUserString</span><span class="sxs-lookup"><span data-stu-id="3f385-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="3f385-103">Ottiene la stringa letterale rappresentata dal token di metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="3f385-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f385-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f385-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f385-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f385-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="3f385-106">[in] Il token di stringa per restituire la stringa associata.</span><span class="sxs-lookup"><span data-stu-id="3f385-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="3f385-107">[out] Una copia della stringa richiesta.</span><span class="sxs-lookup"><span data-stu-id="3f385-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="3f385-108">[in] La dimensione massima in caratteri "wide" dell'oggetto richiesto `szString`.</span><span class="sxs-lookup"><span data-stu-id="3f385-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="3f385-109">[out] La dimensione in caratteri "wide" dell'oggetto restituito `szString`.</span><span class="sxs-lookup"><span data-stu-id="3f385-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f385-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f385-110">Requirements</span></span>  
 <span data-ttu-id="3f385-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f385-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f385-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3f385-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3f385-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3f385-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3f385-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f385-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f385-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f385-115">See also</span></span>
- [<span data-ttu-id="3f385-116">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3f385-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3f385-117">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3f385-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
