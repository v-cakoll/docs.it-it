---
title: Interfaccia IMetaDataDispenser
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dda284fc86f0a82472c59d6bab08fd4a87364723
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225976"
---
# <a name="imetadatadispenser-interface"></a><span data-ttu-id="31039-102">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="31039-102">IMetaDataDispenser Interface</span></span>
<span data-ttu-id="31039-103">Fornisce metodi per creare un nuovo ambito dei metadati o aprirne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="31039-103">Provides methods to create a new metadata scope, or open an existing one.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31039-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="31039-104">Methods</span></span>  
  
|<span data-ttu-id="31039-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="31039-105">Method</span></span>|<span data-ttu-id="31039-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="31039-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31039-107">Metodo DefineScope</span><span class="sxs-lookup"><span data-stu-id="31039-107">DefineScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|<span data-ttu-id="31039-108">Crea una nuova area in memoria in cui è possibile creare nuovi metadati.</span><span class="sxs-lookup"><span data-stu-id="31039-108">Creates a new area in memory where you can create new metadata.</span></span>|  
|[<span data-ttu-id="31039-109">Metodo OpenScope</span><span class="sxs-lookup"><span data-stu-id="31039-109">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|<span data-ttu-id="31039-110">Apre un file esistente su disco e viene eseguito il mapping dei metadati in memoria.</span><span class="sxs-lookup"><span data-stu-id="31039-110">Opens an existing, on-disk file and maps its metadata into memory.</span></span>|  
|[<span data-ttu-id="31039-111">Metodo OpenScopeOnMemory</span><span class="sxs-lookup"><span data-stu-id="31039-111">OpenScopeOnMemory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|<span data-ttu-id="31039-112">Apre un'area di memoria che contiene i metadati esistenti.</span><span class="sxs-lookup"><span data-stu-id="31039-112">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="31039-113">Vale a dire, questo metodo consente di aprire un'area specificata di memoria in cui i dati esistenti viene considerati come metadati.</span><span class="sxs-lookup"><span data-stu-id="31039-113">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31039-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31039-114">Requirements</span></span>  
 <span data-ttu-id="31039-115">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31039-115">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31039-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="31039-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31039-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="31039-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="31039-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="31039-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31039-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31039-119">See also</span></span>

- [<span data-ttu-id="31039-120">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="31039-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="31039-121">Interfacce di metadati</span><span class="sxs-lookup"><span data-stu-id="31039-121">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
