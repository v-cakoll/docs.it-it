---
title: Coclasse CLRRuntimeHost
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e40f08a3dae6f17617e97e07a23b9d7eb611083
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558631"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="c2889-102">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c2889-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="c2889-103">Fornisce interfacce per gestire l'esecuzione di codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="c2889-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2889-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2889-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="c2889-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="c2889-105">Interfaces</span></span>  
  
|<span data-ttu-id="c2889-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="c2889-106">Interface</span></span>|<span data-ttu-id="c2889-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2889-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="c2889-108">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c2889-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="c2889-109">Fornisce metodi per controllare l'esecuzione delle applicazioni dal runtime.</span><span class="sxs-lookup"><span data-stu-id="c2889-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="c2889-110">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="c2889-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="c2889-111">Fornisce metodi per la convalida delle immagini eseguibili portabili e per i report dettagliato degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="c2889-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2889-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2889-112">Requirements</span></span>  
 <span data-ttu-id="c2889-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2889-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2889-114">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="c2889-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c2889-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c2889-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2889-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2889-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2889-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2889-117">See also</span></span>
- [<span data-ttu-id="c2889-118">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="c2889-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
