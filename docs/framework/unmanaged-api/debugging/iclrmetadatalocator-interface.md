---
title: Interfaccia ICLRMetadataLocator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetadataLocator
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRMetadataLocator
helpviewer_keywords: ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 955bd6bffe56a166b4c9c313fcb730ce714bf24b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="425da-102">Interfaccia ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="425da-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="425da-103">Utilizzato dal livello dei servizi di accesso ai dati per individuare i metadati di assembly in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="425da-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="425da-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="425da-104">Methods</span></span>  
  
|<span data-ttu-id="425da-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="425da-105">Method</span></span>|<span data-ttu-id="425da-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="425da-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="425da-107">GetMetadata (metodo)</span><span class="sxs-lookup"><span data-stu-id="425da-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="425da-108">Recupera i metadati di un'immagine dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="425da-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="425da-109">Note</span><span class="sxs-lookup"><span data-stu-id="425da-109">Remarks</span></span>  
 <span data-ttu-id="425da-110">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="425da-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="425da-111">Ad esempio, l'implementazione per un processo reale sarebbe diverso da quello di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="425da-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="425da-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="425da-112">Requirements</span></span>  
 <span data-ttu-id="425da-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="425da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="425da-114">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="425da-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="425da-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="425da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="425da-116">**.**</span><span class="sxs-lookup"><span data-stu-id="425da-116">**.**</span></span> <span data-ttu-id="425da-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="425da-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="425da-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="425da-118">See Also</span></span>  
 [<span data-ttu-id="425da-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="425da-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
