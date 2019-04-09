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
ms.openlocfilehash: b956ac1717ffcb73e819e985450249754f80af2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136162"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="c396d-102">Metodo IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="c396d-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="c396d-103">Ottiene un valore che indica se il campo, il metodo o il tipo rappresentato dal token di metadati specificato ha ambito globale.</span><span class="sxs-lookup"><span data-stu-id="c396d-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c396d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c396d-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c396d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c396d-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="c396d-106">[in] Un token di metadati che rappresenta un tipo, un campo o metodo.</span><span class="sxs-lookup"><span data-stu-id="c396d-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="c396d-107">[out] 1 se l'oggetto ha un ambito globale; in caso contrario, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c396d-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c396d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c396d-108">Requirements</span></span>  
 <span data-ttu-id="c396d-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c396d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c396d-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c396d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c396d-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c396d-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c396d-112">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c396d-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c396d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c396d-113">See also</span></span>

- [<span data-ttu-id="c396d-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c396d-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c396d-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c396d-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
