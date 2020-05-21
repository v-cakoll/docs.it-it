---
title: Interfaccia ICLRValidator
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: e071f9cba7e991c59bf697647e0e4badea57573a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762045"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="a8dfc-102">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="a8dfc-102">ICLRValidator Interface</span></span>
<span data-ttu-id="a8dfc-103">Fornisce metodi per convalidare immagini PE (Portable Executable) e segnalare errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="a8dfc-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8dfc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a8dfc-104">Methods</span></span>  
  
|<span data-ttu-id="a8dfc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a8dfc-105">Method</span></span>|<span data-ttu-id="a8dfc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a8dfc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8dfc-107">Metodo FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="a8dfc-107">FormatEventInfo Method</span></span>](iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="a8dfc-108">Ottiene un messaggio dettagliato sull'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="a8dfc-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="a8dfc-109">Metodo Validate</span><span class="sxs-lookup"><span data-stu-id="a8dfc-109">Validate Method</span></span>](iclrvalidator-validate-method.md)|<span data-ttu-id="a8dfc-110">Convalida il file eseguibile portatile o MSIL (Microsoft Intermediate Language) nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="a8dfc-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8dfc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8dfc-111">Requirements</span></span>  
 <span data-ttu-id="a8dfc-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8dfc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8dfc-113">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="a8dfc-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="a8dfc-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a8dfc-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a8dfc-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8dfc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8dfc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8dfc-116">See also</span></span>

- [<span data-ttu-id="a8dfc-117">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="a8dfc-117">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="a8dfc-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a8dfc-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a8dfc-119">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a8dfc-119">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
