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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194682"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="7e511-102">Metodo IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="7e511-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="7e511-103">Ottiene i metadati di un token per il modulo di cui viene fatto riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="7e511-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e511-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e511-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e511-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e511-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="7e511-106">[out] Puntatore al token che rappresenta il modulo di cui viene fatto riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="7e511-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e511-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e511-107">Requirements</span></span>  
 <span data-ttu-id="7e511-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e511-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e511-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7e511-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7e511-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7e511-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7e511-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7e511-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7e511-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e511-112">See also</span></span>

- [<span data-ttu-id="7e511-113">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7e511-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7e511-114">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7e511-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
