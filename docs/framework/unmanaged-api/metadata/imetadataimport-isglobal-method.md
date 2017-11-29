---
title: Metodo IMetaDataImport::IsGlobal
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.IsGlobal
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09f7d437e09063bf621990dec4f2903139af8238
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="009c3-102">Metodo IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="009c3-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="009c3-103">Ottiene un valore che indica se il campo, il metodo o il tipo rappresentato dal token di metadati specificato ha ambito globale.</span><span class="sxs-lookup"><span data-stu-id="009c3-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="009c3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="009c3-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="009c3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="009c3-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="009c3-106">[in] Token di metadati che rappresenta un tipo, un campo o metodo.</span><span class="sxs-lookup"><span data-stu-id="009c3-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="009c3-107">[out] 1 se l'oggetto ha ambito globale. in caso contrario, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="009c3-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="009c3-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="009c3-108">Requirements</span></span>  
 <span data-ttu-id="009c3-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="009c3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="009c3-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="009c3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="009c3-111">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="009c3-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="009c3-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="009c3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="009c3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="009c3-113">See Also</span></span>  
 [<span data-ttu-id="009c3-114">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="009c3-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="009c3-115">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="009c3-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
