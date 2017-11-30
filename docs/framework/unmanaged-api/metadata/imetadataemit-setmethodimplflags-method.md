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
ms.openlocfilehash: d69940d5cffe397d009b7364a20a09dbbd95db4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="ae918-102">Metodo IMetaDataEmit::SetMethodImplFlags</span><span class="sxs-lookup"><span data-stu-id="ae918-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="ae918-103">Imposta o aggiorna la firma dei metadati di implementazione del metodo ereditato a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="ae918-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae918-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae918-104">Syntax</span></span>  
  
```  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae918-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae918-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="ae918-106">[in] Il token per il metodo da modificare.</span><span class="sxs-lookup"><span data-stu-id="ae918-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="ae918-107">[in] Una combinazione dei valori del [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione che specifica le funzionalità di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="ae918-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae918-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae918-108">Requirements</span></span>  
 <span data-ttu-id="ae918-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae918-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae918-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ae918-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae918-111">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae918-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae918-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae918-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae918-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae918-113">See Also</span></span>  
 [<span data-ttu-id="ae918-114">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ae918-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="ae918-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="ae918-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
