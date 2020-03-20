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
ms.openlocfilehash: 76f18336808e6832b2ded94349efd7948f23a1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175694"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="e506b-102">Metodo IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="e506b-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="e506b-103">Salva tutti i metadati nell'ambito corrente nel file in corrispondenza dell'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="e506b-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e506b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e506b-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e506b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e506b-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="e506b-106">[in] Nome del file in cui salvare.</span><span class="sxs-lookup"><span data-stu-id="e506b-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="e506b-107">Se questo valore è null, la copia in memoria verrà salvata nell'ultima posizione utilizzata.</span><span class="sxs-lookup"><span data-stu-id="e506b-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="e506b-108">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="e506b-108">[in] Reserved.</span></span> <span data-ttu-id="e506b-109">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="e506b-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e506b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e506b-110">Requirements</span></span>  
 <span data-ttu-id="e506b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e506b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e506b-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e506b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e506b-113">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e506b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e506b-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e506b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e506b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e506b-115">See also</span></span>

- [<span data-ttu-id="e506b-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e506b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e506b-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e506b-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
