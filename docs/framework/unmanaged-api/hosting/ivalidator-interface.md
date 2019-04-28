---
title: Interfaccia IValidator
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f516bf1f19e4d4a77e2d6af834a1c3d4e34c327
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765349"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="12535-102">Interfaccia IValidator</span><span class="sxs-lookup"><span data-stu-id="12535-102">IValidator Interface</span></span>
<span data-ttu-id="12535-103">Fornisce metodi per la convalida le immagini (PE) eseguibili portabili e segnalazione di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="12535-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12535-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="12535-104">Methods</span></span>  
  
|<span data-ttu-id="12535-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="12535-105">Method</span></span>|<span data-ttu-id="12535-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12535-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="12535-107">Validate</span><span class="sxs-lookup"><span data-stu-id="12535-107">Validate</span></span>|<span data-ttu-id="12535-108">Convalida il file specificato di PE o Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="12535-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="12535-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="12535-109">FormatEventInfo</span></span>|<span data-ttu-id="12535-110">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="12535-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12535-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12535-111">Requirements</span></span>  
 <span data-ttu-id="12535-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12535-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12535-113">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="12535-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="12535-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="12535-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12535-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12535-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12535-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12535-116">See also</span></span>

- [<span data-ttu-id="12535-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="12535-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="12535-118">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="12535-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
