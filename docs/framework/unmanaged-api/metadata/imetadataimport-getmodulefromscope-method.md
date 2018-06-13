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
ms.openlocfilehash: f1f8acc546c0d96aca079223200b43aec933f729
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447909"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="08eff-102">Metodo IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="08eff-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="08eff-103">Ottiene i metadati di un token per il modulo a cui fa riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="08eff-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08eff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="08eff-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08eff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="08eff-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="08eff-106">[out] Puntatore al token che rappresenta il modulo a cui fa riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="08eff-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08eff-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="08eff-107">Requirements</span></span>  
 <span data-ttu-id="08eff-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08eff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08eff-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08eff-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08eff-110">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="08eff-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08eff-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08eff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08eff-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08eff-112">See Also</span></span>  
 [<span data-ttu-id="08eff-113">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08eff-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="08eff-114">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08eff-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
