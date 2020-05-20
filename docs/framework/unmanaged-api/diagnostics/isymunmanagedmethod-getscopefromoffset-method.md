---
title: Metodo ISymUnmanagedMethod::GetScopeFromOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
ms.openlocfilehash: 4eefd019280f501a6ce194e5ce84388e32cc66e1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615137"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="aa37c-102">Metodo ISymUnmanagedMethod::GetScopeFromOffset</span><span class="sxs-lookup"><span data-stu-id="aa37c-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="aa37c-103">Ottiene l'ambito lessicale di maggiore inclusione all'interno di questo metodo che racchiude l'offset specificato.</span><span class="sxs-lookup"><span data-stu-id="aa37c-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="aa37c-104">Questa operazione può essere utilizzata per avviare le ricerche variabili locali.</span><span class="sxs-lookup"><span data-stu-id="aa37c-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa37c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aa37c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa37c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="aa37c-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="aa37c-107">in Oggetto `ULONG` che contiene l'offset.</span><span class="sxs-lookup"><span data-stu-id="aa37c-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="aa37c-108">out Puntatore impostato sull'interfaccia [ISymUnmanagedScope](isymunmanagedscope-interface.md) restituita.</span><span class="sxs-lookup"><span data-stu-id="aa37c-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa37c-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aa37c-109">Return Value</span></span>  
 <span data-ttu-id="aa37c-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="aa37c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa37c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aa37c-111">Requirements</span></span>  
 <span data-ttu-id="aa37c-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="aa37c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa37c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa37c-113">See also</span></span>

- [<span data-ttu-id="aa37c-114">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="aa37c-114">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
