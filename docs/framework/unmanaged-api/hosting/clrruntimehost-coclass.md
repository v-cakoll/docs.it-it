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
ms.openlocfilehash: 841b05ca1037d82046820554878d883f94687d34
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779154"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="6979e-102">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6979e-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="6979e-103">Fornisce interfacce per gestire l'esecuzione di codice dal runtime.</span><span class="sxs-lookup"><span data-stu-id="6979e-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6979e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6979e-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="6979e-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="6979e-105">Interfaces</span></span>  
  
|<span data-ttu-id="6979e-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="6979e-106">Interface</span></span>|<span data-ttu-id="6979e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6979e-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="6979e-108">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6979e-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="6979e-109">Fornisce metodi per controllare l'esecuzione delle applicazioni dal runtime.</span><span class="sxs-lookup"><span data-stu-id="6979e-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="6979e-110">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="6979e-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="6979e-111">Fornisce metodi per la convalida delle immagini eseguibili portabili e per i report dettagliato degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="6979e-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6979e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6979e-112">Requirements</span></span>  
 <span data-ttu-id="6979e-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6979e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6979e-114">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="6979e-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6979e-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6979e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6979e-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6979e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6979e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6979e-117">See also</span></span>

- [<span data-ttu-id="6979e-118">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="6979e-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
