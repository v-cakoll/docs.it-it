---
title: Metodo IMetaDataImport::IsGlobal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7032e55d52804d559d1faed810ca7cccd6a9e628
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475641"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="b6c7f-102">Metodo IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="b6c7f-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="b6c7f-103">Ottiene un valore che indica se il campo, il metodo o il tipo rappresentato dal token di metadati specificato ha ambito globale.</span><span class="sxs-lookup"><span data-stu-id="b6c7f-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6c7f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6c7f-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6c7f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b6c7f-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="b6c7f-106">[in] Un token di metadati che rappresenta un tipo, un campo o metodo.</span><span class="sxs-lookup"><span data-stu-id="b6c7f-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="b6c7f-107">[out] 1 se l'oggetto ha un ambito globale; in caso contrario, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="b6c7f-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6c7f-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6c7f-108">Requirements</span></span>  
 <span data-ttu-id="b6c7f-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6c7f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6c7f-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6c7f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b6c7f-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b6c7f-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b6c7f-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c7f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6c7f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6c7f-113">See also</span></span>
- [<span data-ttu-id="b6c7f-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b6c7f-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b6c7f-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b6c7f-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
