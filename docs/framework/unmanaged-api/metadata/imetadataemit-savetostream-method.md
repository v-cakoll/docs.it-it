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
ms.workload: dotnet
ms.openlocfilehash: 135faea41ab1a8165e315b8d0815abc48ba7fd38
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="91308-102">Metodo IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="91308-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="91308-103">Salva tutti i metadati nell'ambito corrente specificato `IStream`.</span><span class="sxs-lookup"><span data-stu-id="91308-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91308-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91308-104">Syntax</span></span>  
  
```  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91308-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="91308-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="91308-106">[in] Flusso scrivibile da salvare.</span><span class="sxs-lookup"><span data-stu-id="91308-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="91308-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="91308-107">[in] Reserved.</span></span> <span data-ttu-id="91308-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="91308-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91308-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91308-109">Requirements</span></span>  
 <span data-ttu-id="91308-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91308-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91308-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="91308-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91308-112">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91308-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91308-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91308-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91308-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91308-114">See Also</span></span>  
 [<span data-ttu-id="91308-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="91308-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="91308-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="91308-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
