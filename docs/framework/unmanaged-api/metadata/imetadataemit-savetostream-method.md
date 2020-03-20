---
title: Metodo IMetaDataEmit::SaveToStream
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 7db27670b72a5018a03d4614b69486f67bcef155
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175681"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="e569b-102">Metodo IMetaDataEmit::SaveToStream</span><span class="sxs-lookup"><span data-stu-id="e569b-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="e569b-103">Salva tutti i metadati nell'ambito corrente nell'oggetto specificato. `IStream`</span><span class="sxs-lookup"><span data-stu-id="e569b-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e569b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e569b-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e569b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e569b-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="e569b-106">[in] Flusso scrivibile in cui salvare.</span><span class="sxs-lookup"><span data-stu-id="e569b-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="e569b-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="e569b-107">[in] Reserved.</span></span> <span data-ttu-id="e569b-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="e569b-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e569b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e569b-109">Requirements</span></span>  
 <span data-ttu-id="e569b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e569b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e569b-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e569b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e569b-112">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e569b-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e569b-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e569b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e569b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e569b-114">See also</span></span>

- [<span data-ttu-id="e569b-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e569b-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e569b-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e569b-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
