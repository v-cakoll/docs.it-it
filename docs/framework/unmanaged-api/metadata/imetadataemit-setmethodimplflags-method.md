---
title: Metodo IMetaDataEmit::SetMethodImplFlags
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cffbf01cb8098f30fb026491e0153ac9a651756a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692392"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="65d2e-102">Metodo IMetaDataEmit::SetMethodImplFlags</span><span class="sxs-lookup"><span data-stu-id="65d2e-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="65d2e-103">Imposta o aggiorna la firma dei metadati dell'implementazione del metodo ereditato che fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="65d2e-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65d2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65d2e-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65d2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65d2e-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="65d2e-106">[in] Il token per il metodo da modificare.</span><span class="sxs-lookup"><span data-stu-id="65d2e-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="65d2e-107">[in] Una combinazione dei valori del [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione che specifica la funzionalità di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="65d2e-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65d2e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65d2e-108">Requirements</span></span>  
 <span data-ttu-id="65d2e-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65d2e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65d2e-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="65d2e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="65d2e-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="65d2e-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65d2e-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65d2e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d2e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65d2e-113">See also</span></span>
- [<span data-ttu-id="65d2e-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="65d2e-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="65d2e-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="65d2e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
