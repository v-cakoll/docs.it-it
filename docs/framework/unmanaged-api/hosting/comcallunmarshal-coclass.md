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
ms.openlocfilehash: fde42e3ecfac81a168920bc152833be7ba72b995
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779078"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="c2aa1-102">Coclasse ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="c2aa1-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="c2aa1-103">Fornisce interfacce per gestire il marshalling di puntatori a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c2aa1-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2aa1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c2aa1-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="c2aa1-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="c2aa1-105">Interfaces</span></span>  
  
|<span data-ttu-id="c2aa1-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="c2aa1-106">Interface</span></span>|<span data-ttu-id="c2aa1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2aa1-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="c2aa1-108">Fornisce metodi per la creazione, l'inizializzazione e gestione di un proxy in un processo client.</span><span class="sxs-lookup"><span data-stu-id="c2aa1-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2aa1-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c2aa1-109">Requirements</span></span>  
 <span data-ttu-id="c2aa1-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2aa1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2aa1-111">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="c2aa1-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c2aa1-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c2aa1-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2aa1-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2aa1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2aa1-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2aa1-114">See also</span></span>

- [<span data-ttu-id="c2aa1-115">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="c2aa1-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
