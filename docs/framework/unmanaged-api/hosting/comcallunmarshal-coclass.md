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
ms.openlocfilehash: 939acc0ad47021d5fdffe7b7b71ea6a4a1635a6d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616736"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="1b3bd-102">Coclasse ComCallUnmarshal</span><span class="sxs-lookup"><span data-stu-id="1b3bd-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="1b3bd-103">Fornisce interfacce per la gestione del marshalling dei puntatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b3bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b3bd-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="1b3bd-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="1b3bd-105">Interfaces</span></span>  
  
|<span data-ttu-id="1b3bd-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="1b3bd-106">Interface</span></span>|<span data-ttu-id="1b3bd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b3bd-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="1b3bd-108">Fornisce metodi per la creazione, l'inizializzazione e la gestione di un proxy in un processo client.</span><span class="sxs-lookup"><span data-stu-id="1b3bd-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b3bd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b3bd-109">Requirements</span></span>  
 <span data-ttu-id="1b3bd-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b3bd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b3bd-111">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="1b3bd-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1b3bd-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1b3bd-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b3bd-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b3bd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b3bd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b3bd-114">See also</span></span>

- [<span data-ttu-id="1b3bd-115">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="1b3bd-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
