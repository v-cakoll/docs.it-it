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
ms.openlocfilehash: b765294826a5da4010cdd2db79b50667a6f1cdb4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446299"
---
# <a name="isymunmanagedscopegetnamespaces-method"></a><span data-ttu-id="6cedf-102">Metodo ISymUnmanagedScope::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="6cedf-102">ISymUnmanagedScope::GetNamespaces Method</span></span>
<span data-ttu-id="6cedf-103">Ottiene gli spazi dei nomi utilizzati all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="6cedf-103">Gets the namespaces that are being used within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cedf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6cedf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces),  
        length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cedf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6cedf-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="6cedf-106">[in] Dimensione della matrice `namespaces`.</span><span class="sxs-lookup"><span data-stu-id="6cedf-106">[in] The size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="6cedf-107">out Puntatore a un `ULONG32` che riceve la dimensione del buffer necessario per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6cedf-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="6cedf-108">out Matrice che riceve gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6cedf-108">[out] The array that receives the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cedf-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6cedf-109">Return Value</span></span>  
 <span data-ttu-id="6cedf-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6cedf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cedf-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6cedf-111">Requirements</span></span>  
 <span data-ttu-id="6cedf-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6cedf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cedf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cedf-113">See also</span></span>

- [<span data-ttu-id="6cedf-114">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="6cedf-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
