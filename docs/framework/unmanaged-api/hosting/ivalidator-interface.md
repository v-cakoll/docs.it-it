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
ms.openlocfilehash: 9e79a69bf71aee035fb1f9a0178879d7c19e62b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448921"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="d207b-102">Interfaccia IValidator</span><span class="sxs-lookup"><span data-stu-id="d207b-102">IValidator Interface</span></span>
<span data-ttu-id="d207b-103">Fornisce metodi per la convalida (PE) immagini di tipo PE e la segnalazione degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="d207b-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d207b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="d207b-104">Methods</span></span>  
  
|<span data-ttu-id="d207b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="d207b-105">Method</span></span>|<span data-ttu-id="d207b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d207b-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d207b-107">Validate</span><span class="sxs-lookup"><span data-stu-id="d207b-107">Validate</span></span>|<span data-ttu-id="d207b-108">Convalida il file specificato di PE o in Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="d207b-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="d207b-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="d207b-109">FormatEventInfo</span></span>|<span data-ttu-id="d207b-110">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="d207b-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d207b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d207b-111">Requirements</span></span>  
 <span data-ttu-id="d207b-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d207b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d207b-113">**Intestazione:** IValidator. idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="d207b-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d207b-114">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d207b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d207b-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d207b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d207b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d207b-116">See Also</span></span>  
 [<span data-ttu-id="d207b-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d207b-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="d207b-118">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d207b-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
