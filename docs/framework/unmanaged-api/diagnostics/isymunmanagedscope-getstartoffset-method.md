---
title: Metodo ISymUnmanagedScope::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetStartOffset method [.NET Framework debugging]
ms.assetid: da6bbc75-94d1-4354-9722-0d455b4428fb
topic_type:
- apiref
ms.openlocfilehash: 071ad6c24804eecb0f2260d54c854f22ff997bc1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611016"
---
# <a name="isymunmanagedscopegetstartoffset-method"></a><span data-ttu-id="8b8f6-102">Metodo ISymUnmanagedScope::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="8b8f6-102">ISymUnmanagedScope::GetStartOffset Method</span></span>
<span data-ttu-id="8b8f6-103">Ottiene l'offset iniziale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-103">Gets the start offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b8f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b8f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b8f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b8f6-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8b8f6-106">out Puntatore a un oggetto `ULONG32` che contiene l'offset iniziale.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-106">[out] A pointer to a `ULONG32` that contains the starting offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b8f6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8b8f6-107">Return Value</span></span>  
 <span data-ttu-id="8b8f6-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8b8f6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b8f6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b8f6-109">Requirements</span></span>  
 <span data-ttu-id="8b8f6-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8b8f6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b8f6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b8f6-111">See also</span></span>

- [<span data-ttu-id="8b8f6-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="8b8f6-112">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="8b8f6-113">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="8b8f6-113">GetEndOffset Method</span></span>](isymunmanagedscope-getendoffset-method.md)
