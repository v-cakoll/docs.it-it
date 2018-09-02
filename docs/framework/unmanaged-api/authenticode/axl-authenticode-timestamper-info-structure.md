---
title: Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f4fff4f2c2b3dd04625f4cf50b8b19a0ef6f39
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415897"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="9f013-102">Struttura AXL_AUTHENTICODE_TIMESTAMPER_INFO</span><span class="sxs-lookup"><span data-stu-id="9f013-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="9f013-103">Definisce le informazioni su chi ha apposto il timestamp Authenticode.</span><span class="sxs-lookup"><span data-stu-id="9f013-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f013-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f013-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="9f013-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9f013-105">Members</span></span>  
  
|<span data-ttu-id="9f013-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9f013-106">Member</span></span>|<span data-ttu-id="9f013-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f013-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="9f013-108">Dimensione della struttura.</span><span class="sxs-lookup"><span data-stu-id="9f013-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="9f013-109">Codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9f013-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="9f013-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="9f013-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="9f013-111">Ora del timestamp.</span><span class="sxs-lookup"><span data-stu-id="9f013-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="9f013-112">Contesto della catena del timestamp.</span><span class="sxs-lookup"><span data-stu-id="9f013-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="9f013-113">Vedere le [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) struttura.</span><span class="sxs-lookup"><span data-stu-id="9f013-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f013-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f013-114">See Also</span></span>  
 [<span data-ttu-id="9f013-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="9f013-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
