---
title: Interfaccia ICLRMetadataLocator
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator
helpviewer_keywords:
- ICLRMetadataLocator interface [.NET Framework debugging]
ms.assetid: 43c944f4-406a-4df6-981e-0eabb33dd5d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d1d767de88b239c96cb98130b6ff006e3f75b09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495032"
---
# <a name="iclrmetadatalocator-interface"></a><span data-ttu-id="f70bd-102">Interfaccia ICLRMetadataLocator</span><span class="sxs-lookup"><span data-stu-id="f70bd-102">ICLRMetadataLocator Interface</span></span>
<span data-ttu-id="f70bd-103">Usato dal livello di servizi di accesso ai dati per individuare i metadati degli assembly in un processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f70bd-103">Used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f70bd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f70bd-104">Methods</span></span>  
  
|<span data-ttu-id="f70bd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f70bd-105">Method</span></span>|<span data-ttu-id="f70bd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f70bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f70bd-107">Metodo getMetaData</span><span class="sxs-lookup"><span data-stu-id="f70bd-107">GetMetadata Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-getmetadata-method.md)|<span data-ttu-id="f70bd-108">Recupera i metadati di un'immagine dal processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f70bd-108">Retrieves the metadata of an image from the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f70bd-109">Note</span><span class="sxs-lookup"><span data-stu-id="f70bd-109">Remarks</span></span>  
 <span data-ttu-id="f70bd-110">Il client API, ovvero il debugger, deve implementare questa interfaccia in modo appropriato per il processo di destinazione specifico.</span><span class="sxs-lookup"><span data-stu-id="f70bd-110">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="f70bd-111">Ad esempio, l'implementazione per un processo reale sarebbe diversa da quella di un dump di memoria.</span><span class="sxs-lookup"><span data-stu-id="f70bd-111">For example, the implementation for a live process would be different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f70bd-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f70bd-112">Requirements</span></span>  
 <span data-ttu-id="f70bd-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f70bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f70bd-114">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="f70bd-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f70bd-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f70bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f70bd-116">**.**</span><span class="sxs-lookup"><span data-stu-id="f70bd-116">**.**</span></span> <span data-ttu-id="f70bd-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f70bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70bd-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f70bd-118">See also</span></span>
- [<span data-ttu-id="f70bd-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f70bd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
