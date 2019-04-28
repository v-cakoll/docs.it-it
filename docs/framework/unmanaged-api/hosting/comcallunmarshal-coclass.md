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
ms.openlocfilehash: 2f17a88a90905006432ae8c5dc040277124c947b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697290"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="2c059-102">Coclasse ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="2c059-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="2c059-103">Fornisce interfacce per gestire il marshalling di puntatori a interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2c059-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c059-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c059-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="2c059-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="2c059-105">Interfaces</span></span>  
  
|<span data-ttu-id="2c059-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="2c059-106">Interface</span></span>|<span data-ttu-id="2c059-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c059-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="2c059-108">Fornisce metodi per la creazione, l'inizializzazione e gestione di un proxy in un processo client.</span><span class="sxs-lookup"><span data-stu-id="2c059-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c059-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c059-109">Requirements</span></span>  
 <span data-ttu-id="2c059-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c059-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c059-111">**Intestazione:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="2c059-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="2c059-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2c059-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c059-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c059-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c059-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c059-114">See also</span></span>

- [<span data-ttu-id="2c059-115">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="2c059-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
