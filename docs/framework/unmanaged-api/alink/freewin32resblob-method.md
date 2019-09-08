---
title: Metodo FreeWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.FreeWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- FreeWin32ResBlob
helpviewer_keywords:
- FreeWin32ResBlob method
ms.assetid: d941102b-2679-4c49-b15e-c0fc9c53e11f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea0fbceb1e778a2f26e0625a337b803f417b59eb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777251"
---
# <a name="freewin32resblob-method"></a><span data-ttu-id="4053a-102">Metodo FreeWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="4053a-102">FreeWin32ResBlob Method</span></span>
<span data-ttu-id="4053a-103">Rilascia il BLOB di risorse Win32 e le risorse associate.</span><span class="sxs-lookup"><span data-stu-id="4053a-103">Releases the Win32 resource blob and associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4053a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4053a-104">Syntax</span></span>  
  
```cpp  
HRESULT FreeWin32ResBlob(  
    const void** ppResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4053a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4053a-105">Parameters</span></span>  
 `ppResBlob`  
 <span data-ttu-id="4053a-106">BLOB di risorse da rilasciare.</span><span class="sxs-lookup"><span data-stu-id="4053a-106">The resource blob to be released.</span></span> <span data-ttu-id="4053a-107">Questo metodo assegna il puntatore del BLOB a NULL.</span><span class="sxs-lookup"><span data-stu-id="4053a-107">This method assigns the blob pointer to NULL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4053a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4053a-108">Return Value</span></span>  
 <span data-ttu-id="4053a-109">Restituisce S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4053a-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4053a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4053a-110">Requirements</span></span>  
 <span data-ttu-id="4053a-111">Richiede ALink. h</span><span class="sxs-lookup"><span data-stu-id="4053a-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4053a-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4053a-112">See also</span></span>

- [<span data-ttu-id="4053a-113">Interfaccia IALink</span><span class="sxs-lookup"><span data-stu-id="4053a-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4053a-114">Interfaccia IALink2</span><span class="sxs-lookup"><span data-stu-id="4053a-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4053a-115">Alink (API)</span><span class="sxs-lookup"><span data-stu-id="4053a-115">ALink API</span></span>](index.md)
