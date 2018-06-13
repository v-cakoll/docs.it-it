---
title: Coclasse ComCallUnmarshal
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7884d53630ca13a30d7b4efd55d46684a9dd7d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427642"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="5b6bb-102">Coclasse ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="5b6bb-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="5b6bb-103">Fornisce interfacce per gestire il marshalling di puntatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5b6bb-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b6bb-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="5b6bb-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="5b6bb-105">Interfaces</span></span>  
  
|<span data-ttu-id="5b6bb-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="5b6bb-106">Interface</span></span>|<span data-ttu-id="5b6bb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5b6bb-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="5b6bb-108">Fornisce metodi per la creazione, l'inizializzazione e gestione di un proxy in un processo client.</span><span class="sxs-lookup"><span data-stu-id="5b6bb-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b6bb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b6bb-109">Requirements</span></span>  
 <span data-ttu-id="5b6bb-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b6bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b6bb-111">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="5b6bb-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5b6bb-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5b6bb-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b6bb-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b6bb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6bb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b6bb-114">See Also</span></span>  
 [<span data-ttu-id="5b6bb-115">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="5b6bb-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
