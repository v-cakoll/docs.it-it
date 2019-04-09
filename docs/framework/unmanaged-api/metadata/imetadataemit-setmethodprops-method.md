---
title: Metodo IMetaDataEmit::SetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 534afdd5990435c6b4db5ef8ea27a8065b199496
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183599"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="28163-102">Metodo IMetaDataEmit::SetMethodProps</span><span class="sxs-lookup"><span data-stu-id="28163-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="28163-103">Imposta o aggiorna la funzionalità, archiviata in corrispondenza di indirizzo virtuale relativo specificato, di un metodo definito da una chiamata precedente a [DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="28163-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28163-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28163-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28163-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="28163-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="28163-106">[in] Il token per il metodo da modificare.</span><span class="sxs-lookup"><span data-stu-id="28163-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="28163-107">[in] Attributi del membro.</span><span class="sxs-lookup"><span data-stu-id="28163-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="28163-108">[in] L'indirizzo del codice.</span><span class="sxs-lookup"><span data-stu-id="28163-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="28163-109">[in] I flag di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="28163-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28163-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28163-110">Requirements</span></span>  
 <span data-ttu-id="28163-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28163-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28163-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="28163-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28163-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="28163-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="28163-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="28163-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28163-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28163-115">See also</span></span>

- [<span data-ttu-id="28163-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="28163-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="28163-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="28163-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
