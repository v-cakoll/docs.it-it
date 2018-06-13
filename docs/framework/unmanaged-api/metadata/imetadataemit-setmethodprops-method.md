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
ms.openlocfilehash: 5ef6771ec3f458c20701cc330a5730367b3c5b89
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445926"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="c5092-102">Metodo IMetaDataEmit::SetMethodProps</span><span class="sxs-lookup"><span data-stu-id="c5092-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="c5092-103">Imposta o aggiorna la funzione, archiviata nell'indirizzo virtuale relativo specificato, di un metodo definito da una precedente chiamata a [IMetaDataEmit:: DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="c5092-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5092-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c5092-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5092-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c5092-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="c5092-106">[in] Il token per il metodo da modificare.</span><span class="sxs-lookup"><span data-stu-id="c5092-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="c5092-107">[in] Gli attributi dei membri.</span><span class="sxs-lookup"><span data-stu-id="c5092-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="c5092-108">[in] L'indirizzo del codice.</span><span class="sxs-lookup"><span data-stu-id="c5092-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="c5092-109">[in] I flag di implementazione per il metodo.</span><span class="sxs-lookup"><span data-stu-id="c5092-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5092-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c5092-110">Requirements</span></span>  
 <span data-ttu-id="c5092-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5092-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5092-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c5092-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5092-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c5092-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5092-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5092-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5092-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5092-115">See Also</span></span>  
 [<span data-ttu-id="c5092-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c5092-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c5092-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c5092-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
