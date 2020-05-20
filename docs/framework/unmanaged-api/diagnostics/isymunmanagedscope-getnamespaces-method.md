---
title: Metodo ISymUnmanagedScope::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetNamespaces
helpviewer_keywords:
- GetNamespaces method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetNamespaces method [.NET Framework debugging]
ms.assetid: c44b0440-04bd-460a-84fb-41afecf44503
topic_type:
- apiref
ms.openlocfilehash: 6f11a69671864ba4627c2bb8c86e0c9beb27eeb1
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83611120"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="388bf-102">Metodo ISymUnmanagedScope::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="388bf-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="388bf-103">Ottiene gli spazi dei nomi utilizzati all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="388bf-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="388bf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="388bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="388bf-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="388bf-106">[in] Dimensione della matrice `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="388bf-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="388bf-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione del buffer necessario per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="388bf-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="388bf-108">out Matrice che riceve gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="388bf-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="388bf-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="388bf-109">Return Value</span></span>  
 <span data-ttu-id="388bf-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="388bf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="388bf-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="388bf-111">Requirements</span></span>  
 <span data-ttu-id="388bf-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="388bf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388bf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="388bf-113">See also</span></span>

- [<span data-ttu-id="388bf-114">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="388bf-114">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)
