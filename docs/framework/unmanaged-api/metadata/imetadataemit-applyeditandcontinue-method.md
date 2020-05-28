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
ms.openlocfilehash: 7ce9ac95c7183a7d47c367914d80f77c57dde0d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005765"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="66c10-102">Metodo IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="66c10-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="66c10-103">Aggiorna l'ambito dell'assembly corrente con le modifiche apportate ai metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="66c10-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66c10-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66c10-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66c10-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="66c10-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="66c10-106">\[in \] puntatore a un oggetto [IUnknown](/cpp/atl/iunknown) che rappresenta i metadati delta dal file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="66c10-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="66c10-107">I metadati delta sono il blocco di metadati che include le modifiche apportate alla copia dei metadati effettivi del modulo.</span><span class="sxs-lookup"><span data-stu-id="66c10-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66c10-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66c10-108">Requirements</span></span>  
 <span data-ttu-id="66c10-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66c10-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66c10-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="66c10-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="66c10-111">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="66c10-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66c10-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66c10-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c10-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66c10-113">See also</span></span>

- [<span data-ttu-id="66c10-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="66c10-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="66c10-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="66c10-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
