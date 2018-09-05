---
title: Struttura AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773325"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="be025-102">Struttura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="be025-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="be025-103">Definisce le informazioni su chi ha apposto la firma Authenticode.</span><span class="sxs-lookup"><span data-stu-id="be025-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be025-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be025-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="be025-105">Membri</span><span class="sxs-lookup"><span data-stu-id="be025-105">Members</span></span>  
  
|<span data-ttu-id="be025-106">Membro</span><span class="sxs-lookup"><span data-stu-id="be025-106">Member</span></span>|<span data-ttu-id="be025-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be025-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="be025-108">Dimensione della struttura.</span><span class="sxs-lookup"><span data-stu-id="be025-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="be025-109">Codice di errore.</span><span class="sxs-lookup"><span data-stu-id="be025-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="be025-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="be025-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="be025-111">Hash.</span><span class="sxs-lookup"><span data-stu-id="be025-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="be025-112">Descrizione.</span><span class="sxs-lookup"><span data-stu-id="be025-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="be025-113">URL della descrizione.</span><span class="sxs-lookup"><span data-stu-id="be025-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="be025-114">Contesto della catena del firmatario.</span><span class="sxs-lookup"><span data-stu-id="be025-114">The chain context of the signer.</span></span> <span data-ttu-id="be025-115">Vedere le [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) struttura.</span><span class="sxs-lookup"><span data-stu-id="be025-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be025-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be025-116">See Also</span></span>  
 [<span data-ttu-id="be025-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="be025-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
