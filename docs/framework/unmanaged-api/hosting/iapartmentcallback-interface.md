---
title: Interfaccia IApartmentCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: fbf501d906ecc0bf55719fa33d1af2d4db1cc2ef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617093"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="8190f-102">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="8190f-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="8190f-103">Fornisce metodi per l'esecuzione di callback in un Apartment.</span><span class="sxs-lookup"><span data-stu-id="8190f-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="8190f-104">Un *Apartment* è un contenitore logico all'interno di un processo per gli oggetti che condividono gli stessi requisiti di accesso ai thread.</span><span class="sxs-lookup"><span data-stu-id="8190f-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8190f-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8190f-105">Methods</span></span>  
  
|<span data-ttu-id="8190f-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="8190f-106">Method</span></span>|<span data-ttu-id="8190f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8190f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8190f-108">Metodo DoCallback</span><span class="sxs-lookup"><span data-stu-id="8190f-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="8190f-109">Esegue la funzione specificata in un Apartment.</span><span class="sxs-lookup"><span data-stu-id="8190f-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8190f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8190f-110">Requirements</span></span>  
 <span data-ttu-id="8190f-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8190f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8190f-112">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8190f-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8190f-113">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8190f-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8190f-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8190f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8190f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8190f-115">See also</span></span>

- [<span data-ttu-id="8190f-116">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8190f-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
