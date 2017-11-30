---
title: Metodo IMetaDataEmit::SaveToStream
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SaveToStream
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 97f65fb6cfb7067ed4e6929772f0f114cedcf787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="43f46-102">Metodo IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="43f46-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="43f46-103">Salva tutti i metadati nell'ambito corrente specificato `IStream`.</span><span class="sxs-lookup"><span data-stu-id="43f46-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f46-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43f46-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43f46-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43f46-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="43f46-106">[in] Flusso scrivibile da salvare.</span><span class="sxs-lookup"><span data-stu-id="43f46-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="43f46-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="43f46-107">[in] Reserved.</span></span> <span data-ttu-id="43f46-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="43f46-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43f46-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43f46-109">Requirements</span></span>  
 <span data-ttu-id="43f46-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43f46-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43f46-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="43f46-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43f46-112">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43f46-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43f46-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43f46-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f46-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43f46-114">See Also</span></span>  
 [<span data-ttu-id="43f46-115">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="43f46-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="43f46-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="43f46-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
