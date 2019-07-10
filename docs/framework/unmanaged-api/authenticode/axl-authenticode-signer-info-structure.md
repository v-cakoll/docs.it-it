---
title: Struttura AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 232c78db32aecd0ee1379d4d969fa0378db4159a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741363"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="852ba-102">Struttura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="852ba-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="852ba-103">Definisce le informazioni su chi ha apposto la firma Authenticode.</span><span class="sxs-lookup"><span data-stu-id="852ba-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="852ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="852ba-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="852ba-105">Membri</span><span class="sxs-lookup"><span data-stu-id="852ba-105">Members</span></span>  
  
|<span data-ttu-id="852ba-106">Member</span><span class="sxs-lookup"><span data-stu-id="852ba-106">Member</span></span>|<span data-ttu-id="852ba-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="852ba-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="852ba-108">Dimensione della struttura.</span><span class="sxs-lookup"><span data-stu-id="852ba-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="852ba-109">Codice di errore.</span><span class="sxs-lookup"><span data-stu-id="852ba-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="852ba-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="852ba-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="852ba-111">Hash.</span><span class="sxs-lookup"><span data-stu-id="852ba-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="852ba-112">Descrizione.</span><span class="sxs-lookup"><span data-stu-id="852ba-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="852ba-113">URL della descrizione.</span><span class="sxs-lookup"><span data-stu-id="852ba-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="852ba-114">Contesto della catena del firmatario.</span><span class="sxs-lookup"><span data-stu-id="852ba-114">The chain context of the signer.</span></span> <span data-ttu-id="852ba-115">Vedere le [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) struttura.</span><span class="sxs-lookup"><span data-stu-id="852ba-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="852ba-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="852ba-116">See also</span></span>

- [<span data-ttu-id="852ba-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="852ba-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
