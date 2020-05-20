---
title: Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod
ms.date: 03/30/2017
ms.assetid: 670a7653-dac6-4171-98ee-d669e3adf4b2
ms.openlocfilehash: 91b4c2688dadf12fa4a835a662622267d7831cf8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441799"
---
# <a name="isymunmanagedasyncmethodisasyncmethod-method"></a><span data-ttu-id="6a9d9-102">Metodo ISymUnmanagedAsyncMethod::IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="6a9d9-102">ISymUnmanagedAsyncMethod::IsAsyncMethod Method</span></span>
<span data-ttu-id="6a9d9-103">Verifica se il metodo contiene informazioni asincrone o meno.</span><span class="sxs-lookup"><span data-stu-id="6a9d9-103">Checks if the method has async information or not.</span></span>  
  
 <span data-ttu-id="6a9d9-104">Se questo metodo restituisce `FALSE` , non è valido chiamare altri metodi in questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6a9d9-104">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="6a9d9-105">`E_UNEXPECTED`In questo caso verranno restituiti tutti.</span><span class="sxs-lookup"><span data-stu-id="6a9d9-105">They will all return `E_UNEXPECTED` in this case.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a9d9-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a9d9-106">Syntax</span></span>  
  
```idl  
HRESULT IsAsyncMethod(    [out, retval] BOOL* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a9d9-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a9d9-107">Parameters</span></span>  
  
|<span data-ttu-id="6a9d9-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="6a9d9-108">Parameter</span></span>|<span data-ttu-id="6a9d9-109">Description</span><span class="sxs-lookup"><span data-stu-id="6a9d9-109">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="6a9d9-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6a9d9-110">Return Value</span></span>  
 <span data-ttu-id="6a9d9-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="6a9d9-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a9d9-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a9d9-112">Requirements</span></span>  
 <span data-ttu-id="6a9d9-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6a9d9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9d9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a9d9-114">See also</span></span>

- [<span data-ttu-id="6a9d9-115">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="6a9d9-115">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
