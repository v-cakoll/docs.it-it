---
title: Interfaccia IValidator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator
api_location: mscoree.dll
api_type: COM
f1_keywords: IValidator
helpviewer_keywords: IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d88bfa0a3e71f34a7439e97f4347a06aa2c4058
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ivalidator-interface"></a><span data-ttu-id="501fd-102">Interfaccia IValidator</span><span class="sxs-lookup"><span data-stu-id="501fd-102">IValidator Interface</span></span>
<span data-ttu-id="501fd-103">Fornisce metodi per la convalida (PE) immagini di tipo PE e la segnalazione degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="501fd-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="501fd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="501fd-104">Methods</span></span>  
  
|<span data-ttu-id="501fd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="501fd-105">Method</span></span>|<span data-ttu-id="501fd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="501fd-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="501fd-107">Validate</span><span class="sxs-lookup"><span data-stu-id="501fd-107">Validate</span></span>|<span data-ttu-id="501fd-108">Convalida il file specificato di PE o in Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="501fd-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="501fd-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="501fd-109">FormatEventInfo</span></span>|<span data-ttu-id="501fd-110">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="501fd-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="501fd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="501fd-111">Requirements</span></span>  
 <span data-ttu-id="501fd-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="501fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="501fd-113">**Intestazione:** IValidator. idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="501fd-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="501fd-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="501fd-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="501fd-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="501fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="501fd-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="501fd-116">See Also</span></span>  
 [<span data-ttu-id="501fd-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="501fd-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="501fd-118">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="501fd-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
