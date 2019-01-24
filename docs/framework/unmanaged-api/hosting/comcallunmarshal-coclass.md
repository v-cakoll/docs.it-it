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
ms.openlocfilehash: 5a404448c45a37d50794ceae9a9bf8ff6af08eeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574573"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="daf38-102">Coclasse ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="daf38-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="daf38-103">Fornisce interfacce per gestire il marshalling di puntatori a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="daf38-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daf38-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="daf38-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="daf38-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="daf38-105">Interfaces</span></span>  
  
|<span data-ttu-id="daf38-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="daf38-106">Interface</span></span>|<span data-ttu-id="daf38-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="daf38-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="daf38-108">Fornisce metodi per la creazione, l'inizializzazione e gestione di un proxy in un processo client.</span><span class="sxs-lookup"><span data-stu-id="daf38-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="daf38-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="daf38-109">Requirements</span></span>  
 <span data-ttu-id="daf38-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daf38-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daf38-111">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="daf38-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="daf38-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="daf38-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="daf38-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daf38-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daf38-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="daf38-114">See also</span></span>
- [<span data-ttu-id="daf38-115">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="daf38-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
