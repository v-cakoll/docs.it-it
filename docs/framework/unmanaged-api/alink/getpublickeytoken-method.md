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
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789844"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="60760-102">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="60760-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="60760-103">Recupera il token di chiave pubblica per un file di chiave specificata o un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="60760-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60760-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60760-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="60760-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60760-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="60760-106">Nome file della chiave.</span><span class="sxs-lookup"><span data-stu-id="60760-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="60760-107">Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="60760-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="60760-108">Indirizzo in cui viene archiviato il token di chiave.</span><span class="sxs-lookup"><span data-stu-id="60760-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="60760-109">Specifica la dimensione, in byte, del buffer indicato da `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="60760-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="60760-110">Dopo la restituzione, contiene il numero effettivo di byte utilizzati.</span><span class="sxs-lookup"><span data-stu-id="60760-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60760-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="60760-111">Return Value</span></span>  
 <span data-ttu-id="60760-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="60760-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60760-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60760-113">Requirements</span></span>  
 <span data-ttu-id="60760-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="60760-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60760-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60760-115">See also</span></span>

- [<span data-ttu-id="60760-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="60760-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="60760-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="60760-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="60760-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="60760-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
