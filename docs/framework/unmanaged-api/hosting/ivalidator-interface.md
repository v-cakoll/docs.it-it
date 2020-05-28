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
ms.openlocfilehash: d8e5ab607f9310341ded482b35f02f3845926328
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008560"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="2d853-102">Interfaccia IValidator</span><span class="sxs-lookup"><span data-stu-id="2d853-102">IValidator Interface</span></span>
<span data-ttu-id="2d853-103">Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="2d853-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d853-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2d853-104">Methods</span></span>  
  
|<span data-ttu-id="2d853-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2d853-105">Method</span></span>|<span data-ttu-id="2d853-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d853-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2d853-107">Validate</span><span class="sxs-lookup"><span data-stu-id="2d853-107">Validate</span></span>|<span data-ttu-id="2d853-108">Convalida il file PE o Microsoft Intermediate Language (MSIL) specificato.</span><span class="sxs-lookup"><span data-stu-id="2d853-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="2d853-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="2d853-109">FormatEventInfo</span></span>|<span data-ttu-id="2d853-110">Ottiene il messaggio di errore corrispondente all'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="2d853-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d853-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d853-111">Requirements</span></span>  
 <span data-ttu-id="2d853-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d853-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d853-113">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="2d853-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="2d853-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2d853-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d853-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d853-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d853-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d853-116">See also</span></span>

- [<span data-ttu-id="2d853-117">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="2d853-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="2d853-118">Coclasse CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2d853-118">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
