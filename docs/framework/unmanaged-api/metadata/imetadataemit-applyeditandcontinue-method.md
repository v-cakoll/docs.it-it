---
title: Metodo IMetaDataEmit::ApplyEditAndContinue
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05de7d45c53d8aeaafaa06ae351050cc8bca3622
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777697"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="4af15-102">Metodo IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="4af15-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="4af15-103">Aggiorna l'ambito dell'assembly corrente con le modifiche apportate nei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="4af15-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4af15-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4af15-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4af15-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="4af15-106">\[nelle\] puntatore a un [IUnknown](/cpp/atl/iunknown) oggetto che rappresenta i metadati del delta dal file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="4af15-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="4af15-107">I metadati del delta sono il blocco di metadati che includono le modifiche apportate alla copia dei metadati effettivi del modulo.</span><span class="sxs-lookup"><span data-stu-id="4af15-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4af15-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4af15-108">Requirements</span></span>  
 <span data-ttu-id="4af15-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4af15-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af15-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4af15-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4af15-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4af15-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4af15-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af15-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af15-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4af15-113">See also</span></span>

- [<span data-ttu-id="4af15-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4af15-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4af15-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4af15-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
