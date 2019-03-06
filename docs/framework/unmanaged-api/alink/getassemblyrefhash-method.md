---
title: Metodo GetAssemblyRefHash
ms.date: 03/30/2017
api_name:
- IALink.GetAssemblyRefHash
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetAssemblyRefHash
helpviewer_keywords:
- GetAssemblyRefHash method
ms.assetid: 091a18bd-e901-46f6-b999-74d71c8a7c41
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b2597cf14f4f1fc9a99740b4a07502246f80087d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466596"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="97d0f-102">Metodo GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="97d0f-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="97d0f-103">Recupera un blob di hash per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="97d0f-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97d0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97d0f-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="97d0f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97d0f-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="97d0f-106">ID dell'assembly a cui farà riferimento il valore hash.</span><span class="sxs-lookup"><span data-stu-id="97d0f-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="97d0f-107">Riceve il blob hash risultante.</span><span class="sxs-lookup"><span data-stu-id="97d0f-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="97d0f-108">Riceve le dimensioni, in byte del blob hash.</span><span class="sxs-lookup"><span data-stu-id="97d0f-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97d0f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97d0f-109">Return Value</span></span>  
 <span data-ttu-id="97d0f-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="97d0f-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97d0f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97d0f-111">Requirements</span></span>  
 <span data-ttu-id="97d0f-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="97d0f-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97d0f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97d0f-113">See also</span></span>
- [<span data-ttu-id="97d0f-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="97d0f-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="97d0f-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="97d0f-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="97d0f-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="97d0f-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
