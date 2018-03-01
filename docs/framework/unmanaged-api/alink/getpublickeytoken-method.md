---
title: Metodo GetPublicKeyToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 230c98e85bd0aa3bd2f368965b6f7ac028e43df4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="65ae0-102">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="65ae0-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="65ae0-103">Recupera il token di chiave pubblica per un determinato file o un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="65ae0-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65ae0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65ae0-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65ae0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65ae0-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="65ae0-106">Nome del file della chiave.</span><span class="sxs-lookup"><span data-stu-id="65ae0-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="65ae0-107">Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="65ae0-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="65ae0-108">Indirizzo in cui il token di chiave da archiviare.</span><span class="sxs-lookup"><span data-stu-id="65ae0-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="65ae0-109">Specifica la dimensione, in byte, del buffer indicato da `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="65ae0-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="65ae0-110">Al momento della restituzione, contiene il numero effettivo di byte utilizzati.</span><span class="sxs-lookup"><span data-stu-id="65ae0-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65ae0-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65ae0-111">Return Value</span></span>  
 <span data-ttu-id="65ae0-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="65ae0-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65ae0-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65ae0-113">Requirements</span></span>  
 <span data-ttu-id="65ae0-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="65ae0-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ae0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65ae0-115">See Also</span></span>  
 [<span data-ttu-id="65ae0-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="65ae0-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="65ae0-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="65ae0-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="65ae0-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="65ae0-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
