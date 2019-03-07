---
title: Metodo ISymUnmanagedNamespace::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetName
helpviewer_keywords:
- ISymUnmanagedNamespace::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 657bf91d-005a-4ea4-9298-04d1291c0bc3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e57e7ff024037ef523c85105b69a45e866850934
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496482"
---
# <a name="isymunmanagednamespacegetname-method"></a><span data-ttu-id="f2794-102">Metodo ISymUnmanagedNamespace::GetName</span><span class="sxs-lookup"><span data-stu-id="f2794-102">ISymUnmanagedNamespace::GetName Method</span></span>
<span data-ttu-id="f2794-103">Ottiene il nome di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f2794-103">Gets the name of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2794-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2794-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2794-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f2794-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f2794-106">[in] Oggetto `ULONG32` che indica le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="f2794-106">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f2794-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il nome dello spazio dei nomi, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="f2794-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespace name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="f2794-108">[out] Un puntatore a un buffer che contiene il nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f2794-108">[out] A pointer to a buffer that contains the namespace name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2794-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f2794-109">Return Value</span></span>  
 <span data-ttu-id="f2794-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f2794-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2794-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f2794-111">Requirements</span></span>  
 <span data-ttu-id="f2794-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f2794-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2794-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2794-113">See also</span></span>
- [<span data-ttu-id="f2794-114">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="f2794-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
