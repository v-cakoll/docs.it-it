---
title: Metodo IMetaDataEmit::GetTokenFromSig
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be42fea034be4fe5d48874b00db86977a3039a34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448220"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="42ca0-102">Metodo IMetaDataEmit::GetTokenFromSig</span><span class="sxs-lookup"><span data-stu-id="42ca0-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="42ca0-103">Ottiene un token per la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="42ca0-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ca0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42ca0-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42ca0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="42ca0-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="42ca0-106">[in] La firma di mantenere e archiviati.</span><span class="sxs-lookup"><span data-stu-id="42ca0-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="42ca0-107">[in] Il numero di byte in `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="42ca0-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="42ca0-108">[out] Il `mdSignature` token assegnato.</span><span class="sxs-lookup"><span data-stu-id="42ca0-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42ca0-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42ca0-109">Requirements</span></span>  
 <span data-ttu-id="42ca0-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42ca0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42ca0-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="42ca0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42ca0-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="42ca0-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42ca0-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42ca0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42ca0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42ca0-114">See Also</span></span>  
 [<span data-ttu-id="42ca0-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="42ca0-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="42ca0-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="42ca0-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
