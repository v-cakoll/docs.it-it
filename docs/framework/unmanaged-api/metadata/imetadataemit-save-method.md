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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ece16d8dcdc685db960a485cd19261f6b9f2fbe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757599"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="6ca1f-102">Metodo IMetaDataEmit::Save</span><span class="sxs-lookup"><span data-stu-id="6ca1f-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="6ca1f-103">Salva tutti i metadati nell'ambito corrente del file all'indirizzo specificato.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca1f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ca1f-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ca1f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ca1f-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="6ca1f-106">[in] Il nome del file da salvare.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="6ca1f-107">Se questo valore è null, la copia in memoria verrà salvata all'ultima posizione che è stato usato.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="6ca1f-108">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-108">[in] Reserved.</span></span> <span data-ttu-id="6ca1f-109">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="6ca1f-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ca1f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ca1f-110">Requirements</span></span>  
 <span data-ttu-id="6ca1f-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ca1f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ca1f-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6ca1f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6ca1f-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6ca1f-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ca1f-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ca1f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ca1f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ca1f-115">See also</span></span>

- [<span data-ttu-id="6ca1f-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="6ca1f-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6ca1f-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="6ca1f-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
