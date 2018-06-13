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
ms.openlocfilehash: ce8be38f6e146b2a8669ea5c694353615f6f2d66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445903"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="5cc0d-102">Metodo IMetaDataEmit::SetModuleProps</span><span class="sxs-lookup"><span data-stu-id="5cc0d-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="5cc0d-103">Aggiorna i riferimenti a un modulo definito da una precedente chiamata a [IMetaDataEmit:: DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="5cc0d-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc0d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cc0d-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cc0d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cc0d-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="5cc0d-106">[in] Il nome del modulo in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="5cc0d-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="5cc0d-107">Questo è solo il nome di file e non il nome e percorso completo.</span><span class="sxs-lookup"><span data-stu-id="5cc0d-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc0d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cc0d-108">Requirements</span></span>  
 <span data-ttu-id="5cc0d-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cc0d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc0d-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5cc0d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5cc0d-111">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5cc0d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cc0d-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cc0d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc0d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cc0d-113">See Also</span></span>  
 [<span data-ttu-id="5cc0d-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5cc0d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="5cc0d-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5cc0d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
