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
ms.openlocfilehash: 9f307ad5689602b030c609a51f6834bdbb0ec4f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717715"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="eca51-102">Interfaccia IValidator</span><span class="sxs-lookup"><span data-stu-id="eca51-102">IValidator Interface</span></span>
<span data-ttu-id="eca51-103">Fornisce metodi per la convalida le immagini (PE) eseguibili portabili e segnalazione di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="eca51-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eca51-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="eca51-104">Methods</span></span>  
  
|<span data-ttu-id="eca51-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="eca51-105">Method</span></span>|<span data-ttu-id="eca51-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="eca51-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="eca51-107">Validate</span><span class="sxs-lookup"><span data-stu-id="eca51-107">Validate</span></span>|<span data-ttu-id="eca51-108">Convalida il file specificato di PE o Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="eca51-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="eca51-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="eca51-109">FormatEventInfo</span></span>|<span data-ttu-id="eca51-110">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="eca51-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eca51-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="eca51-111">Requirements</span></span>  
 <span data-ttu-id="eca51-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eca51-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eca51-113">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="eca51-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="eca51-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="eca51-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eca51-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eca51-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca51-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eca51-116">See also</span></span>
- [<span data-ttu-id="eca51-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="eca51-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="eca51-118">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="eca51-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
