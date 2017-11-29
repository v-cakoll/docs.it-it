---
title: Metodo IMetaDataImport::GetModuleFromScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetModuleFromScope
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d7a9987f9a557cda79483e46c1798d471aa13944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="c9f8d-102">Metodo IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="c9f8d-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="c9f8d-103">Ottiene i metadati di un token per il modulo a cui fa riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="c9f8d-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9f8d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9f8d-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9f8d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9f8d-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="c9f8d-106">[out] Puntatore al token che rappresenta il modulo a cui fa riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="c9f8d-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9f8d-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9f8d-107">Requirements</span></span>  
 <span data-ttu-id="c9f8d-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9f8d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9f8d-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c9f8d-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9f8d-110">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9f8d-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9f8d-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9f8d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f8d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9f8d-112">See Also</span></span>  
 [<span data-ttu-id="c9f8d-113">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c9f8d-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c9f8d-114">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c9f8d-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
