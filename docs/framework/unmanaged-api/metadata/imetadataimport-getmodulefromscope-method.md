---
title: Metodo IMetaDataImport::GetModuleFromScope
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f40e6bfdbebdadc41da52564348c6070c18372c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194682"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="3af6a-102">Metodo IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="3af6a-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="3af6a-103">Ottiene i metadati di un token per il modulo di cui viene fatto riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="3af6a-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3af6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3af6a-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3af6a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3af6a-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="3af6a-106">[out] Puntatore al token che rappresenta il modulo di cui viene fatto riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="3af6a-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3af6a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3af6a-107">Requirements</span></span>  
 <span data-ttu-id="3af6a-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3af6a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3af6a-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3af6a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3af6a-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3af6a-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3af6a-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3af6a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3af6a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3af6a-112">See also</span></span>

- [<span data-ttu-id="3af6a-113">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3af6a-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3af6a-114">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="3af6a-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
