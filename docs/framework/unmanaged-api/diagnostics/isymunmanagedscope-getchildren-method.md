---
title: Metodo ISymUnmanagedScope::GetChildren
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
ms.openlocfilehash: c6d21f40c260890c9c88dcdfccd7e31161024ba3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614864"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="36f84-102">Metodo ISymUnmanagedScope::GetChildren</span><span class="sxs-lookup"><span data-stu-id="36f84-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="36f84-103">Ottiene gli elementi figlio di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="36f84-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36f84-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36f84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36f84-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="36f84-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="36f84-106">in Oggetto `ULONG32` che indica la dimensione della `children` matrice.</span><span class="sxs-lookup"><span data-stu-id="36f84-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="36f84-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione del buffer necessario per contenere gli elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="36f84-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="36f84-108">out Matrice di elementi figlio restituita.</span><span class="sxs-lookup"><span data-stu-id="36f84-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36f84-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="36f84-109">Return Value</span></span>  
 <span data-ttu-id="36f84-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="36f84-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36f84-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36f84-111">Requirements</span></span>  
 <span data-ttu-id="36f84-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="36f84-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36f84-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36f84-113">See also</span></span>

- [<span data-ttu-id="36f84-114">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="36f84-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
- [<span data-ttu-id="36f84-115">Metodo GetParent</span><span class="sxs-lookup"><span data-stu-id="36f84-115">GetParent Method</span></span>](isymunmanagedscope-getparent-method.md)
