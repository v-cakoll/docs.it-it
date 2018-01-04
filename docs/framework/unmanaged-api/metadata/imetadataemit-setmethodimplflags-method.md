---
title: Metodo IMetaDataEmit::SetMethodImplFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetMethodImplFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8026ec666e853b5a0ccd98e5ba75a3e04ffea9a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="4f07e-102">Metodo IMetaDataEmit::SetMethodImplFlags</span><span class="sxs-lookup"><span data-stu-id="4f07e-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="4f07e-103">Imposta o aggiorna la firma dei metadati di implementazione del metodo ereditato a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="4f07e-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f07e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f07e-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f07e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f07e-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="4f07e-106">[in] Il token per il metodo da modificare.</span><span class="sxs-lookup"><span data-stu-id="4f07e-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="4f07e-107">[in] Una combinazione dei valori del [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione che specifica le funzionalità di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="4f07e-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f07e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f07e-108">Requirements</span></span>  
 <span data-ttu-id="4f07e-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f07e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f07e-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4f07e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f07e-111">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f07e-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f07e-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f07e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f07e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f07e-113">See Also</span></span>  
 [<span data-ttu-id="4f07e-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4f07e-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="4f07e-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4f07e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
