---
title: Metodo IMetaDataEmit::SetModuleProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5219a414c5961128d4eaa27c1f18d635938dc5ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497405"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="01a56-102">Metodo IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="01a56-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="01a56-103">Aggiorna i riferimenti a un modulo definito da una chiamata precedente a [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="01a56-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a56-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01a56-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01a56-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01a56-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="01a56-106">[in] Il nome del modulo in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="01a56-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="01a56-107">Si tratta solo il nome del file e non il nome e percorso completo.</span><span class="sxs-lookup"><span data-stu-id="01a56-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01a56-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01a56-108">Requirements</span></span>  
 <span data-ttu-id="01a56-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01a56-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01a56-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="01a56-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01a56-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="01a56-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01a56-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01a56-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01a56-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01a56-113">See also</span></span>
- [<span data-ttu-id="01a56-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="01a56-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="01a56-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="01a56-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
