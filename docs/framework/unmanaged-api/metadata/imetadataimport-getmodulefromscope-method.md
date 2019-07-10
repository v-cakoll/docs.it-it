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
ms.openlocfilehash: 05ce699669095e9c0b45882b18a01ec326640038
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778999"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="6a9cd-102">Metodo IMetaDataImport::GetModuleFromScope</span><span class="sxs-lookup"><span data-stu-id="6a9cd-102">IMetaDataImport::GetModuleFromScope Method</span></span>
<span data-ttu-id="6a9cd-103">Ottiene i metadati di un token per il modulo di cui viene fatto riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="6a9cd-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a9cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a9cd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a9cd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a9cd-105">Parameters</span></span>  
 `pmd`  
 <span data-ttu-id="6a9cd-106">[out] Puntatore al token che rappresenta il modulo di cui viene fatto riferimento nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="6a9cd-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a9cd-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a9cd-107">Requirements</span></span>  
 <span data-ttu-id="6a9cd-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a9cd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a9cd-109">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6a9cd-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a9cd-110">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6a9cd-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a9cd-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a9cd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9cd-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a9cd-112">See also</span></span>

- [<span data-ttu-id="6a9cd-113">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6a9cd-113">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a9cd-114">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6a9cd-114">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
