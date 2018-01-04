---
title: Metodo IMetaDataEmit::Save
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.Save
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a11241894116f57889a15a184290cd95f2f4f54f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="c9c32-102">Metodo IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="c9c32-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="c9c32-103">Salva tutti i metadati nell'ambito corrente del file all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="c9c32-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9c32-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9c32-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9c32-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9c32-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="c9c32-106">[in] Il nome del file da salvare.</span><span class="sxs-lookup"><span data-stu-id="c9c32-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="c9c32-107">Se questo valore è null, la copia in memoria verrà salvata e l'ultimo percorso usato.</span><span class="sxs-lookup"><span data-stu-id="c9c32-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="c9c32-108">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="c9c32-108">[in] Reserved.</span></span> <span data-ttu-id="c9c32-109">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="c9c32-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9c32-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9c32-110">Requirements</span></span>  
 <span data-ttu-id="c9c32-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9c32-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9c32-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c9c32-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9c32-113">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9c32-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9c32-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c32-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9c32-115">See Also</span></span>  
 [<span data-ttu-id="c9c32-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c9c32-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c9c32-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c9c32-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
