---
title: Metodo ISymUnmanagedVariable::GetStartOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetStartOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetStartOffset
helpviewer_keywords:
- GetStartOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetStartOffset method [.NET Framework debugging]
ms.assetid: 63021fc1-9c2d-4788-811f-fe8ca077206a
topic_type:
- apiref
ms.openlocfilehash: f2996349fd2bf1765a3de5b67d3296a25b1eaa5e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610366"
---
# <a name="isymunmanagedvariablegetstartoffset-method"></a><span data-ttu-id="e9d8d-102">Metodo ISymUnmanagedVariable::GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="e9d8d-102">ISymUnmanagedVariable::GetStartOffset Method</span></span>
<span data-ttu-id="e9d8d-103">Ottiene l'offset iniziale della variabile all'interno dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="e9d8d-103">Gets the start offset of this variable within its parent.</span></span> <span data-ttu-id="e9d8d-104">Se si tratta di una variabile locale all'interno di un ambito, l'offset iniziale rientrerà negli offset definiti per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="e9d8d-104">If this is a local variable within a scope, the start offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9d8d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9d8d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStartOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9d8d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9d8d-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e9d8d-107">out Puntatore a un oggetto `ULONG32` che riceve l'offset iniziale.</span><span class="sxs-lookup"><span data-stu-id="e9d8d-107">[out] A pointer to a `ULONG32` that receives the start offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9d8d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e9d8d-108">Return Value</span></span>  
 <span data-ttu-id="e9d8d-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e9d8d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9d8d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9d8d-110">Requirements</span></span>  
 <span data-ttu-id="e9d8d-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="e9d8d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d8d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9d8d-112">See also</span></span>

- [<span data-ttu-id="e9d8d-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="e9d8d-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="e9d8d-114">Metodo GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="e9d8d-114">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)
