---
title: Metodo ISymUnmanagedReader::GetNamespaces
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e0c72cd6e7dce784064f7653ba35e488061d9fd7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773588"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="c3b37-102">Metodo ISymUnmanagedReader::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="c3b37-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="c3b37-103">Ottiene gli spazi dei nomi definiti in ambito globale all'interno di questo archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="c3b37-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3b37-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3b37-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="c3b37-106">[in] Le dimensioni della matrice di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c3b37-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="c3b37-107">[out] Un puntatore a una variabile che riceve la lunghezza dell'elenco lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c3b37-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="c3b37-108">[out] Puntatore a una variabile che riceve l'elenco di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c3b37-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3b37-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c3b37-109">Return Value</span></span>  
 <span data-ttu-id="c3b37-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c3b37-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b37-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3b37-111">Requirements</span></span>  
 <span data-ttu-id="c3b37-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3b37-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b37-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3b37-113">See also</span></span>

- [<span data-ttu-id="c3b37-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="c3b37-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
