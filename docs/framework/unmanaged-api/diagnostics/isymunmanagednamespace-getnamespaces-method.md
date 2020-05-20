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
ms.openlocfilehash: 48c50ac6be6d525676d85578e5a55a27104c180a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615098"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="489d5-102">Metodo ISymUnmanagedNamespace::GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="489d5-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="489d5-103">Ottiene gli elementi figlio di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="489d5-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="489d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="489d5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="489d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="489d5-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="489d5-106">in Oggetto `ULONG32` che indica la dimensione della `namespaces` matrice.</span><span class="sxs-lookup"><span data-stu-id="489d5-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="489d5-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="489d5-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="489d5-108">out Puntatore al buffer che contiene gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="489d5-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="489d5-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="489d5-109">Return Value</span></span>  
 <span data-ttu-id="489d5-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="489d5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="489d5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="489d5-111">Requirements</span></span>  
 <span data-ttu-id="489d5-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="489d5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489d5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="489d5-113">See also</span></span>

- [<span data-ttu-id="489d5-114">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="489d5-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
