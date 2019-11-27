---
title: Metodo IMetaDataEmit::Save
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
ms.openlocfilehash: afd60cdf566bea459816ee890d44cc09258de516
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435942"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="4f5b7-102">Metodo IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="4f5b7-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="4f5b7-103">Salva tutti i metadati nell'ambito corrente nel file in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="4f5b7-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f5b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f5b7-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f5b7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f5b7-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="4f5b7-106">in Nome del file in cui salvare.</span><span class="sxs-lookup"><span data-stu-id="4f5b7-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="4f5b7-107">Se questo valore è null, la copia in memoria verrà salvata nell'ultima posizione utilizzata.</span><span class="sxs-lookup"><span data-stu-id="4f5b7-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="4f5b7-108">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="4f5b7-108">[in] Reserved.</span></span> <span data-ttu-id="4f5b7-109">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="4f5b7-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f5b7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f5b7-110">Requirements</span></span>  
 <span data-ttu-id="4f5b7-111">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f5b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f5b7-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4f5b7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f5b7-113">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4f5b7-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f5b7-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f5b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f5b7-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f5b7-115">See also</span></span>

- [<span data-ttu-id="4f5b7-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4f5b7-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4f5b7-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4f5b7-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
