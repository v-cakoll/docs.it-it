---
title: Struttura AXL_AUTHENTICODE_SIGNER_INFO
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd07707b5a80ec0980fc50b27caddf0a24398fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400445"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="c9d86-102">Struttura AXL_AUTHENTICODE_SIGNER_INFO</span><span class="sxs-lookup"><span data-stu-id="c9d86-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="c9d86-103">Definisce le informazioni su chi ha apposto la firma Authenticode.</span><span class="sxs-lookup"><span data-stu-id="c9d86-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9d86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9d86-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c9d86-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c9d86-105">Members</span></span>  
  
|<span data-ttu-id="c9d86-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c9d86-106">Member</span></span>|<span data-ttu-id="c9d86-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9d86-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="c9d86-108">Dimensione della struttura.</span><span class="sxs-lookup"><span data-stu-id="c9d86-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="c9d86-109">Codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c9d86-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="c9d86-110">Algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="c9d86-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="c9d86-111">Hash.</span><span class="sxs-lookup"><span data-stu-id="c9d86-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="c9d86-112">Descrizione.</span><span class="sxs-lookup"><span data-stu-id="c9d86-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="c9d86-113">URL della descrizione.</span><span class="sxs-lookup"><span data-stu-id="c9d86-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="c9d86-114">Contesto della catena del firmatario.</span><span class="sxs-lookup"><span data-stu-id="c9d86-114">The chain context of the signer.</span></span> <span data-ttu-id="c9d86-115">Vedere il [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) struttura.</span><span class="sxs-lookup"><span data-stu-id="c9d86-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9d86-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9d86-116">See Also</span></span>  
 [<span data-ttu-id="c9d86-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="c9d86-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
