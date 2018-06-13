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
ms.openlocfilehash: 94a473d00110c07615ccdfc98bb8944e40dc30e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405473"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="0e9f5-102">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="0e9f5-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="0e9f5-103">Recupera il token di chiave pubblica per un determinato file o un contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0e9f5-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e9f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0e9f5-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="0e9f5-106">Nome del file della chiave.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="0e9f5-107">Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="0e9f5-108">Indirizzo in cui il token di chiave da archiviare.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="0e9f5-109">Specifica la dimensione, in byte, del buffer indicato da `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="0e9f5-110">Al momento della restituzione, contiene il numero effettivo di byte utilizzati.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e9f5-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0e9f5-111">Return Value</span></span>  
 <span data-ttu-id="0e9f5-112">Se il metodo ha esito positivo, restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e9f5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e9f5-113">Requirements</span></span>  
 <span data-ttu-id="0e9f5-114">Richiede alink.h.</span><span class="sxs-lookup"><span data-stu-id="0e9f5-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9f5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e9f5-115">See Also</span></span>  
 [<span data-ttu-id="0e9f5-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="0e9f5-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0e9f5-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="0e9f5-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0e9f5-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="0e9f5-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
