---
title: Metodo ISymUnmanagedNamespace::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d7ac84971f7d0e97f7ccd26710151d1aeefe729
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207214"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="21fec-102">Metodo ISymUnmanagedNamespace::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="21fec-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="21fec-103">Ottiene gli elementi figlio di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="21fec-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21fec-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21fec-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21fec-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21fec-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="21fec-106">[in] Oggetto `ULONG32` che indica le dimensioni del `namespaces` matrice.</span><span class="sxs-lookup"><span data-stu-id="21fec-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="21fec-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="21fec-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="21fec-108">[out] Puntatore al buffer che contiene gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="21fec-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21fec-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="21fec-109">Return Value</span></span>  
 <span data-ttu-id="21fec-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="21fec-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21fec-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21fec-111">Requirements</span></span>  
 <span data-ttu-id="21fec-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="21fec-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21fec-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21fec-113">See also</span></span>

- [<span data-ttu-id="21fec-114">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="21fec-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
