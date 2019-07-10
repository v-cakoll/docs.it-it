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
ms.openlocfilehash: a437ff11114ea8d577b2fc3b81cd981cebb8c8d6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751072"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="d3950-102">Metodo IMetaDataEmit::SetMethodImplFlags</span><span class="sxs-lookup"><span data-stu-id="d3950-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="d3950-103">Imposta o aggiorna la firma dei metadati dell'implementazione del metodo ereditato che fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="d3950-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3950-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3950-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3950-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3950-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="d3950-106">[in] Il token per il metodo da modificare.</span><span class="sxs-lookup"><span data-stu-id="d3950-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="d3950-107">[in] Una combinazione dei valori del [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumerazione che specifica la funzionalità di implementazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="d3950-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3950-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3950-108">Requirements</span></span>  
 <span data-ttu-id="d3950-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3950-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3950-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d3950-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3950-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d3950-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3950-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3950-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3950-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3950-113">See also</span></span>

- [<span data-ttu-id="d3950-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d3950-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d3950-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d3950-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
