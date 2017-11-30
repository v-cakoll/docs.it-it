---
title: Metodo IMetaDataEmit::ApplyEditAndContinue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.ApplyEditAndContinue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6d7744051bca9aeec677803f8b6c0bbbd0cdd1fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="a0e9a-102">Metodo IMetaDataEmit::ApplyEditAndContinue</span><span class="sxs-lookup"><span data-stu-id="a0e9a-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="a0e9a-103">Aggiorna l'ambito dell'assembly corrente con le modifiche apportate nei metadati specificati.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0e9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0e9a-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0e9a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0e9a-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="a0e9a-106">[in] Puntatore a un <<!--zzxref:IUnknown --> `IUnknown`> oggetto che rappresenta i metadati delta dal file eseguibile portabile (PE).</span><span class="sxs-lookup"><span data-stu-id="a0e9a-106">[in] Pointer to an <<!--zzxref:IUnknown --> `IUnknown`> object that represents the delta metadata from the portable executable (PE) file.</span></span>  
  
 <span data-ttu-id="a0e9a-107">I metadati delta sono il blocco di metadati che includono le modifiche apportate alla copia dei metadati effettivi del modulo.</span><span class="sxs-lookup"><span data-stu-id="a0e9a-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0e9a-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0e9a-108">Requirements</span></span>  
 <span data-ttu-id="a0e9a-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0e9a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0e9a-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a0e9a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0e9a-111">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0e9a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0e9a-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0e9a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e9a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0e9a-113">See Also</span></span>  
 [<span data-ttu-id="a0e9a-114">IMetaDataEmit (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a0e9a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a0e9a-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a0e9a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
