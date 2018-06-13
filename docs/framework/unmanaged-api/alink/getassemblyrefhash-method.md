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
ms.openlocfilehash: ccf60d067af356dda1870a2fb1dcca21966f16a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401486"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="52b17-102">Metodo GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="52b17-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="52b17-103">Recupera un blob hash per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="52b17-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52b17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52b17-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52b17-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52b17-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="52b17-106">ID dell'assembly a cui farà riferimento all'hash.</span><span class="sxs-lookup"><span data-stu-id="52b17-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="52b17-107">Riceve il blob hash risultante.</span><span class="sxs-lookup"><span data-stu-id="52b17-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="52b17-108">Riceve le dimensioni, in byte del blob hash.</span><span class="sxs-lookup"><span data-stu-id="52b17-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52b17-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52b17-109">Return Value</span></span>  
 <span data-ttu-id="52b17-110">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="52b17-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52b17-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52b17-111">Requirements</span></span>  
 <span data-ttu-id="52b17-112">Richiede alink.h</span><span class="sxs-lookup"><span data-stu-id="52b17-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52b17-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52b17-113">See Also</span></span>  
 [<span data-ttu-id="52b17-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="52b17-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="52b17-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="52b17-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="52b17-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="52b17-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
