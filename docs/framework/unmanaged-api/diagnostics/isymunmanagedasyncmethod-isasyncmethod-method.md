---
title: Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5cddf34f1a6277e966901c9692bff63e26a3b8e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136734"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="46385-102">Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="46385-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="46385-103">Controlla se il metodo contiene le informazioni di async o meno.</span><span class="sxs-lookup"><span data-stu-id="46385-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="46385-104">Se questo metodo restituisce `FALSE` quindi non è consentito chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="46385-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="46385-105">Restituirà tutti `E_UNEXPECTED` in questo caso.</span><span class="sxs-lookup"><span data-stu-id="46385-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46385-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="46385-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46385-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="46385-107">Parameters</span></span>  
  
|<span data-ttu-id="46385-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="46385-108">Parameter</span></span>|<span data-ttu-id="46385-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="46385-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="46385-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="46385-110">Return Value</span></span>  
 <span data-ttu-id="46385-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="46385-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46385-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="46385-112">Requirements</span></span>  
 <span data-ttu-id="46385-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="46385-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46385-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46385-114">See also</span></span>

- [<span data-ttu-id="46385-115">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="46385-115">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
