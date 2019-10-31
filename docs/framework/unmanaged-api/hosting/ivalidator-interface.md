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
ms.openlocfilehash: 1a732e59d539c330f91e8665e81dc4771b40e2d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123292"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="620e2-102">Interfaccia IValidator</span><span class="sxs-lookup"><span data-stu-id="620e2-102">IValidator Interface</span></span>
<span data-ttu-id="620e2-103">Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="620e2-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="620e2-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="620e2-104">Methods</span></span>  
  
|<span data-ttu-id="620e2-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="620e2-105">Method</span></span>|<span data-ttu-id="620e2-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="620e2-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="620e2-107">Validate</span><span class="sxs-lookup"><span data-stu-id="620e2-107">Validate</span></span>|<span data-ttu-id="620e2-108">Convalida il file PE o Microsoft Intermediate Language (MSIL) specificato.</span><span class="sxs-lookup"><span data-stu-id="620e2-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="620e2-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="620e2-109">FormatEventInfo</span></span>|<span data-ttu-id="620e2-110">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="620e2-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="620e2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="620e2-111">Requirements</span></span>  
 <span data-ttu-id="620e2-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="620e2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="620e2-113">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="620e2-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="620e2-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="620e2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="620e2-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="620e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620e2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="620e2-116">See also</span></span>

- [<span data-ttu-id="620e2-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="620e2-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="620e2-118">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="620e2-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
