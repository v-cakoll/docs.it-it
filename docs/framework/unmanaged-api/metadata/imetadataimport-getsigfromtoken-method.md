---
title: Metodo IMetaDataImport::GetSigFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetSigFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetSigFromToken
helpviewer_keywords:
- IMetaDataImport::GetSigFromToken method [.NET Framework metadata]
- GetSigFromToken method [.NET Framework metadata]
ms.assetid: ab894dc4-f7b6-4afc-bfcb-582a4b7e53a2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 823a172c05d2ce76fef790966f54d7216f579fde
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152984"
---
# <a name="imetadataimportgetsigfromtoken-method"></a><span data-ttu-id="d5d97-102">Metodo IMetaDataImport::GetSigFromToken</span><span class="sxs-lookup"><span data-stu-id="d5d97-102">IMetaDataImport::GetSigFromToken Method</span></span>
<span data-ttu-id="d5d97-103">Ottiene la firma binaria dei metadati associata al token specificato.</span><span class="sxs-lookup"><span data-stu-id="d5d97-103">Gets the binary metadata signature associated with the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5d97-104">Syntax</span></span>  
  
```  
HRESULT GetSigFromToken (   
   [in]   mdSignature        mdSig,   
   [out]  PCCOR_SIGNATURE    *ppvSig,   
   [out]  ULONG              *pcbSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5d97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5d97-105">Parameters</span></span>  
 `mdSig`  
 <span data-ttu-id="d5d97-106">[in] Il token per restituire la firma binaria dei metadati.</span><span class="sxs-lookup"><span data-stu-id="d5d97-106">[in] The token to return the binary metadata signature for.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="d5d97-107">[out] Un puntatore per la firma dei metadati restituiti.</span><span class="sxs-lookup"><span data-stu-id="d5d97-107">[out] A pointer to the returned metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="d5d97-108">[out] La dimensione in byte della firma binaria dei metadati.</span><span class="sxs-lookup"><span data-stu-id="d5d97-108">[out] The size in bytes of the binary metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5d97-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5d97-109">Requirements</span></span>  
 <span data-ttu-id="d5d97-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5d97-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d97-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d5d97-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5d97-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d5d97-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5d97-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d97-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d97-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5d97-114">See also</span></span>

- [<span data-ttu-id="d5d97-115">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="d5d97-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d5d97-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="d5d97-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
