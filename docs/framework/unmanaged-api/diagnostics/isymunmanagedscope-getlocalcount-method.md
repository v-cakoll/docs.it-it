---
title: Metodo ISymUnmanagedScope::GetLocalCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
ms.openlocfilehash: 3b5dbe875b47f48c24c5e955abddb2c6f778bcdd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446346"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="dc7c6-102">Metodo ISymUnmanagedScope::GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="dc7c6-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="dc7c6-103">Ottiene un conteggio delle variabili locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="dc7c6-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc7c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dc7c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc7c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dc7c6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="dc7c6-106">out Puntatore a un `ULONG32` che riceve il conteggio delle variabili locali.</span><span class="sxs-lookup"><span data-stu-id="dc7c6-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc7c6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dc7c6-107">Return Value</span></span>  
 <span data-ttu-id="dc7c6-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="dc7c6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc7c6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dc7c6-109">Requirements</span></span>  
 <span data-ttu-id="dc7c6-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="dc7c6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc7c6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc7c6-111">See also</span></span>

- [<span data-ttu-id="dc7c6-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="dc7c6-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
