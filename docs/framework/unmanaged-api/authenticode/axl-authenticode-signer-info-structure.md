---
title: Struttura AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c69be0de98e2996176e7360bae0bb0736c1a797
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038437"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="916c1-102">Struttura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="916c1-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="916c1-103">Definisce le informazioni su chi ha apposto la firma Authenticode.</span><span class="sxs-lookup"><span data-stu-id="916c1-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="916c1-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="916c1-105">Members</span><span class="sxs-lookup"><span data-stu-id="916c1-105">Members</span></span>  
  
|<span data-ttu-id="916c1-106">Member</span><span class="sxs-lookup"><span data-stu-id="916c1-106">Member</span></span>|<span data-ttu-id="916c1-107">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="916c1-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="916c1-108">Dimensione della struttura.</span><span class="sxs-lookup"><span data-stu-id="916c1-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="916c1-109">Codice di errore.</span><span class="sxs-lookup"><span data-stu-id="916c1-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="916c1-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="916c1-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="916c1-111">Hash.</span><span class="sxs-lookup"><span data-stu-id="916c1-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="916c1-112">Descrizione.</span><span class="sxs-lookup"><span data-stu-id="916c1-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="916c1-113">URL della descrizione.</span><span class="sxs-lookup"><span data-stu-id="916c1-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="916c1-114">Contesto della catena del firmatario.</span><span class="sxs-lookup"><span data-stu-id="916c1-114">The chain context of the signer.</span></span> <span data-ttu-id="916c1-115">Vedere la struttura [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) .</span><span class="sxs-lookup"><span data-stu-id="916c1-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="916c1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="916c1-116">See also</span></span>

- [<span data-ttu-id="916c1-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="916c1-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
