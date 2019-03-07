---
title: Metodo GetPublicKeyToken
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0481cfc3fa88aeb6fd7cd6ba93554d426f8eb2e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492049"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="f4f61-102">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="f4f61-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="f4f61-103">Recupera il token di chiave pubblica per un file di chiave specificata o un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="f4f61-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4f61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4f61-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4f61-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4f61-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="f4f61-106">Nome file della chiave.</span><span class="sxs-lookup"><span data-stu-id="f4f61-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="f4f61-107">Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="f4f61-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="f4f61-108">Indirizzo in cui viene archiviato il token di chiave.</span><span class="sxs-lookup"><span data-stu-id="f4f61-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="f4f61-109">Specifica la dimensione, in byte, del buffer indicato da `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="f4f61-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="f4f61-110">Dopo la restituzione, contiene il numero effettivo di byte utilizzati.</span><span class="sxs-lookup"><span data-stu-id="f4f61-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4f61-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f4f61-111">Return Value</span></span>  
 <span data-ttu-id="f4f61-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f4f61-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4f61-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4f61-113">Requirements</span></span>  
 <span data-ttu-id="f4f61-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="f4f61-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4f61-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4f61-115">See also</span></span>
- [<span data-ttu-id="f4f61-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="f4f61-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f4f61-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="f4f61-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f4f61-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="f4f61-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
