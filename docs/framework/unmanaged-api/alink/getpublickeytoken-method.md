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
ms.openlocfilehash: 2e7ed4e1529104db30b0b06665f74342d9ca9a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447234"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="4cb37-102">Metodo GetPublicKeyToken</span><span class="sxs-lookup"><span data-stu-id="4cb37-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="4cb37-103">Recupera il token di chiave pubblica per un file di chiave o un contenitore di chiavi specificato.</span><span class="sxs-lookup"><span data-stu-id="4cb37-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4cb37-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cb37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4cb37-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="4cb37-106">Nome del file della chiave.</span><span class="sxs-lookup"><span data-stu-id="4cb37-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="4cb37-107">Nome del contenitore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="4cb37-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="4cb37-108">Indirizzo in cui deve essere archiviato il token di chiave.</span><span class="sxs-lookup"><span data-stu-id="4cb37-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="4cb37-109">Specifica la dimensione, in byte, del buffer indicato dal `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="4cb37-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="4cb37-110">Al momento della restituzione, contiene il numero effettivo di byte utilizzati.</span><span class="sxs-lookup"><span data-stu-id="4cb37-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cb37-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4cb37-111">Return Value</span></span>  
 <span data-ttu-id="4cb37-112">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4cb37-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb37-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4cb37-113">Requirements</span></span>  
 <span data-ttu-id="4cb37-114">Richiede ALink. h.</span><span class="sxs-lookup"><span data-stu-id="4cb37-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb37-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4cb37-115">See also</span></span>

- [<span data-ttu-id="4cb37-116">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="4cb37-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4cb37-117">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="4cb37-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4cb37-118">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="4cb37-118">ALink API</span></span>](index.md)
