---
title: Metodo ISymUnmanagedConstant::GetValue
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
ms.openlocfilehash: 8e20d2e0f3d5cb6dc7444c8e78665b6c8b82d2de
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441474"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="1e5fc-102">Metodo ISymUnmanagedConstant::GetValue</span><span class="sxs-lookup"><span data-stu-id="1e5fc-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="1e5fc-103"> Ottiene il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="1e5fc-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e5fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e5fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e5fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e5fc-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="1e5fc-106">out Puntatore a una variabile che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="1e5fc-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e5fc-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e5fc-107">Return Value</span></span>  
 <span data-ttu-id="1e5fc-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1e5fc-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e5fc-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e5fc-109">Requirements</span></span>  
 <span data-ttu-id="1e5fc-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1e5fc-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e5fc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e5fc-111">See also</span></span>

- [<span data-ttu-id="1e5fc-112">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="1e5fc-112">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="1e5fc-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="1e5fc-113">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="1e5fc-114">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="1e5fc-114">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
