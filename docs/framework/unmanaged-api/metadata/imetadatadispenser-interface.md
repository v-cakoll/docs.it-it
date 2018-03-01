---
title: Interfaccia IMetaDataDispenser
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataDispenser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser
helpviewer_keywords:
- IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 678796357b36beb26ebbf34edc713ff6f15a7c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="18b2d-102">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="18b2d-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="18b2d-103">Fornisce metodi per creare un nuovo ambito dei metadati o aprirne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="18b2d-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="18b2d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="18b2d-104">Methods</span></span>  
  
|<span data-ttu-id="18b2d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="18b2d-105">Method</span></span>|<span data-ttu-id="18b2d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18b2d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="18b2d-107">Metodo DefineScope</span><span class="sxs-lookup"><span data-stu-id="18b2d-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="18b2d-108">Crea una nuova area in memoria in cui è possibile creare nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="18b2d-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="18b2d-109">Metodo OpenScope</span><span class="sxs-lookup"><span data-stu-id="18b2d-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="18b2d-110">Apre un file esistente, su disco e viene eseguito il mapping dei metadati in memoria.</span><span class="sxs-lookup"><span data-stu-id="18b2d-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="18b2d-111">Metodo OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="18b2d-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="18b2d-112">Verrà visualizzata un'area di memoria che contiene i metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="18b2d-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="18b2d-113">Vale a dire, questo metodo apre un'area specificata di memoria in cui i dati esistenti viene trattati come metadati.</span><span class="sxs-lookup"><span data-stu-id="18b2d-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18b2d-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18b2d-114">Requirements</span></span>  
 <span data-ttu-id="18b2d-115">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18b2d-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18b2d-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="18b2d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18b2d-117">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18b2d-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18b2d-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18b2d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b2d-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18b2d-119">See Also</span></span>  
 [<span data-ttu-id="18b2d-120">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="18b2d-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="18b2d-121">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="18b2d-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
