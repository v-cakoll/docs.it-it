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
ms.openlocfilehash: c15c554e0ec135b33d671a83b5e27d0a2a89b731
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444256"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="7ccb4-102">Metodo IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="7ccb4-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="7ccb4-103">Aggiorna l'ambito dell'assembly corrente con le modifiche apportate nei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="7ccb4-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ccb4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ccb4-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ccb4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ccb4-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="7ccb4-106">[in] Puntatore a un <<!--zzxref:IUnknown --> `IUnknown`> oggetto che rappresenta i metadati delta dal file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="7ccb4-106">[in] Pointer to an <<!--zzxref:IUnknown --> `IUnknown`> object that represents the delta metadata from the portable executable (PE) file.</span></span>  
  
 <span data-ttu-id="7ccb4-107">I metadati delta sono il blocco di metadati che includono le modifiche apportate alla copia dei metadati effettivi del modulo.</span><span class="sxs-lookup"><span data-stu-id="7ccb4-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ccb4-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ccb4-108">Requirements</span></span>  
 <span data-ttu-id="7ccb4-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ccb4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ccb4-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7ccb4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ccb4-111">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7ccb4-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ccb4-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ccb4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ccb4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ccb4-113">See Also</span></span>  
 [<span data-ttu-id="7ccb4-114">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7ccb4-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7ccb4-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7ccb4-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
