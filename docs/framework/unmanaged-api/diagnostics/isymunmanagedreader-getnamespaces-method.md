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
ms.openlocfilehash: 570532433483e9d0a08f4d685087c0736e135390
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993304"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="f236a-102">Metodo ISymUnmanagedReader::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="f236a-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="f236a-103">Ottiene gli spazi dei nomi definiti in ambito globale all'interno di questo archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="f236a-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f236a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f236a-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f236a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f236a-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="f236a-106">[in] Le dimensioni della matrice di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f236a-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="f236a-107">[out] Un puntatore a una variabile che riceve la lunghezza dell'elenco lo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f236a-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="f236a-108">[out] Puntatore a una variabile che riceve l'elenco di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f236a-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f236a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f236a-109">Return Value</span></span>  
 <span data-ttu-id="f236a-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f236a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f236a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f236a-111">Requirements</span></span>  
 <span data-ttu-id="f236a-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f236a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f236a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f236a-113">See also</span></span>

- [<span data-ttu-id="f236a-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="f236a-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
