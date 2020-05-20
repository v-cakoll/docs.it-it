---
title: Metodo ISymUnmanagedVariable::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
ms.openlocfilehash: 91117eae23d38f3bc608f3203ebe53f92516c9c9
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610496"
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="59d78-102">Metodo ISymUnmanagedVariable::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="59d78-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="59d78-103">Ottiene l'offset finale della variabile all'interno dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="59d78-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="59d78-104">Se si tratta di una variabile locale all'interno di un ambito, l'offset finale rientrerà negli offset definiti per l'ambito.</span><span class="sxs-lookup"><span data-stu-id="59d78-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59d78-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59d78-105">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59d78-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="59d78-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="59d78-107">out Puntatore a un oggetto `ULONG32` che riceve l'offset finale.</span><span class="sxs-lookup"><span data-stu-id="59d78-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59d78-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="59d78-108">Return Value</span></span>  
 <span data-ttu-id="59d78-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="59d78-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59d78-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59d78-110">Requirements</span></span>  
 <span data-ttu-id="59d78-111">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="59d78-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59d78-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59d78-112">See also</span></span>

- [<span data-ttu-id="59d78-113">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="59d78-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="59d78-114">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="59d78-114">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)
