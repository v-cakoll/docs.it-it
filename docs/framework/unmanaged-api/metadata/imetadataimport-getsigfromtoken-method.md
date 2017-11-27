---
title: Metodo IMetaDataImport::GetSigFromToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetSigFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab7df32641d4fcd093f1ed31eb9ed7c7954e6bf8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="122d3-102">Metodo IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="122d3-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="122d3-103">Ottiene la firma binaria dei metadati associata al token specificato.</span><span class="sxs-lookup"><span data-stu-id="122d3-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="122d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="122d3-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="122d3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="122d3-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="122d3-106">[in] Il token da restituire la firma binaria dei metadati.</span><span class="sxs-lookup"><span data-stu-id="122d3-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="122d3-107">[out] Puntatore alla firma dei metadati restituiti.</span><span class="sxs-lookup"><span data-stu-id="122d3-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="122d3-108">[out] Le dimensioni in byte della firma binaria dei metadati.</span><span class="sxs-lookup"><span data-stu-id="122d3-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="122d3-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="122d3-109">Requirements</span></span>  
 <span data-ttu-id="122d3-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="122d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="122d3-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="122d3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="122d3-112">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="122d3-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="122d3-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="122d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="122d3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="122d3-114">See Also</span></span>  
 [<span data-ttu-id="122d3-115">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="122d3-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="122d3-116">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="122d3-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
