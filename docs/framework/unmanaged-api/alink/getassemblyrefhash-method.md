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
ms.openlocfilehash: d19eebaa3aa0ebb6f9807f0cf277b7ed6183c148
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777201"
---
# <a name="getassemblyrefhash-method"></a><span data-ttu-id="6c8ed-102">Metodo GetAssemblyRefHash</span><span class="sxs-lookup"><span data-stu-id="6c8ed-102">GetAssemblyRefHash Method</span></span>
<span data-ttu-id="6c8ed-103">Recupera un blob hash per un determinato assembly.</span><span class="sxs-lookup"><span data-stu-id="6c8ed-103">Retrieves a hash blob for a given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c8ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c8ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefHash(  
    mdToken FileToken,  
    const void** ppvHash,  
    DWORD* pcbHash  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c8ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c8ed-105">Parameters</span></span>  
 `FileToken`  
 <span data-ttu-id="6c8ed-106">ID dell'assembly a cui si riferisce l'hash.</span><span class="sxs-lookup"><span data-stu-id="6c8ed-106">ID of assembly to which the hash will refer.</span></span>  
  
 `ppvHash`  
 <span data-ttu-id="6c8ed-107">Riceve il blob hash risultante.</span><span class="sxs-lookup"><span data-stu-id="6c8ed-107">Receives the resulting hash blob.</span></span>  
  
 `pcbHash`  
 <span data-ttu-id="6c8ed-108">Riceve le dimensioni, in byte, del blob hash.</span><span class="sxs-lookup"><span data-stu-id="6c8ed-108">Receives size, in bytes, of hash blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c8ed-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c8ed-109">Return Value</span></span>  
 <span data-ttu-id="6c8ed-110">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6c8ed-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c8ed-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c8ed-111">Requirements</span></span>  
 <span data-ttu-id="6c8ed-112">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="6c8ed-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c8ed-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c8ed-113">See also</span></span>

- [<span data-ttu-id="6c8ed-114">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="6c8ed-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="6c8ed-115">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="6c8ed-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="6c8ed-116">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="6c8ed-116">ALink API</span></span>](index.md)
