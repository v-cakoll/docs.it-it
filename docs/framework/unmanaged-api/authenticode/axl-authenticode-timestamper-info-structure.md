---
title: Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9eef89c9e560da65d670ffe59649b44a64f8da6a
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039600"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="dc3af-102">Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="dc3af-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="dc3af-103">Definisce le informazioni su chi ha apposto il timestamp Authenticode.</span><span class="sxs-lookup"><span data-stu-id="dc3af-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc3af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc3af-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="dc3af-105">Members</span><span class="sxs-lookup"><span data-stu-id="dc3af-105">Members</span></span>  
  
|<span data-ttu-id="dc3af-106">Member</span><span class="sxs-lookup"><span data-stu-id="dc3af-106">Member</span></span>|<span data-ttu-id="dc3af-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dc3af-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="dc3af-108">Dimensione della struttura.</span><span class="sxs-lookup"><span data-stu-id="dc3af-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="dc3af-109">Codice di errore.</span><span class="sxs-lookup"><span data-stu-id="dc3af-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="dc3af-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="dc3af-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="dc3af-111">Ora del timestamp.</span><span class="sxs-lookup"><span data-stu-id="dc3af-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="dc3af-112">Contesto della catena del timestamp.</span><span class="sxs-lookup"><span data-stu-id="dc3af-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="dc3af-113">Vedere la struttura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="dc3af-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc3af-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc3af-114">See also</span></span>

- [<span data-ttu-id="dc3af-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="dc3af-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
