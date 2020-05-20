---
title: Metodo ISymUnmanagedScope::GetMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type:
- apiref
ms.openlocfilehash: cdbffe71540b51ff539a45861546efd761761892
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615371"
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="7c930-102">Metodo ISymUnmanagedScope::GetMethod</span><span class="sxs-lookup"><span data-stu-id="7c930-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="7c930-103">Ottiene il metodo che contiene questo ambito.</span><span class="sxs-lookup"><span data-stu-id="7c930-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c930-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c930-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c930-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c930-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="7c930-106">out Puntatore all'interfaccia [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="7c930-106">[out] A pointer to the returned [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c930-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c930-107">Return Value</span></span>  
 <span data-ttu-id="7c930-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7c930-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c930-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c930-109">Requirements</span></span>  
 <span data-ttu-id="7c930-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7c930-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c930-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c930-111">See also</span></span>

- [<span data-ttu-id="7c930-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="7c930-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
