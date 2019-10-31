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
ms.openlocfilehash: b1e595e1a4f1b462437f47207b998829a8bd774d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129458"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="9f5c1-102">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9f5c1-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="9f5c1-103">Fornisce interfacce per la gestione dell'esecuzione del codice da parte del runtime.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f5c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f5c1-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="9f5c1-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="9f5c1-105">Interfaces</span></span>  
  
|<span data-ttu-id="9f5c1-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="9f5c1-106">Interface</span></span>|<span data-ttu-id="9f5c1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f5c1-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="9f5c1-108">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="9f5c1-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="9f5c1-109">Fornisce metodi per controllare l'esecuzione delle applicazioni da parte del runtime.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="9f5c1-110">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="9f5c1-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="9f5c1-111">Fornisce metodi per la convalida delle immagini eseguibili portabili e per la segnalazione dettagliata degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="9f5c1-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f5c1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f5c1-112">Requirements</span></span>  
 <span data-ttu-id="9f5c1-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f5c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f5c1-114">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="9f5c1-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9f5c1-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9f5c1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f5c1-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f5c1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5c1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f5c1-117">See also</span></span>

- [<span data-ttu-id="9f5c1-118">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="9f5c1-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
