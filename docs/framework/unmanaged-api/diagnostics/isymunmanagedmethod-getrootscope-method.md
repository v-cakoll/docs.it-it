---
title: Metodo ISymUnmanagedMethod::GetRootScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: c956f5d68c992f1b08988e59038e8667b391f734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448920"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="13b68-102">Metodo ISymUnmanagedMethod::GetRootScope</span><span class="sxs-lookup"><span data-stu-id="13b68-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="13b68-103">Ottiene l'ambito lessicale radice all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="13b68-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="13b68-104">Questo ambito racchiude l'intero metodo.</span><span class="sxs-lookup"><span data-stu-id="13b68-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b68-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13b68-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13b68-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="13b68-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="13b68-107">out Puntatore impostato sull'interfaccia [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="13b68-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13b68-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="13b68-108">Return Value</span></span>  
 <span data-ttu-id="13b68-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="13b68-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13b68-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13b68-110">Requirements</span></span>  
 <span data-ttu-id="13b68-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="13b68-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b68-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13b68-112">See also</span></span>

- [<span data-ttu-id="13b68-113">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="13b68-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
