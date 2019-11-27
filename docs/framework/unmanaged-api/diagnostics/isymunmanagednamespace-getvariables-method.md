---
title: Metodo ISymUnmanagedNamespace::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: 98ed5556020b93fb1f31d1dde84690fc33092627
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448368"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="fc1cc-102">Metodo ISymUnmanagedNamespace::GetVariables</span><span class="sxs-lookup"><span data-stu-id="fc1cc-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="fc1cc-103">Restituisce tutte le variabili definite in ambito globale all'interno di questo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fc1cc-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc1cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fc1cc-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc1cc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fc1cc-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="fc1cc-106">in `ULONG32` che indica le dimensioni della matrice di `pVars`.</span><span class="sxs-lookup"><span data-stu-id="fc1cc-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="fc1cc-107">out Puntatore a un `ULONG32` che riceve la dimensione del buffer necessario per contenere gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fc1cc-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="fc1cc-108">out Puntatore a un buffer che contiene gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="fc1cc-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc1cc-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fc1cc-109">Return Value</span></span>  
 <span data-ttu-id="fc1cc-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fc1cc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc1cc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fc1cc-111">Requirements</span></span>  
 <span data-ttu-id="fc1cc-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="fc1cc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc1cc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fc1cc-113">See also</span></span>

- [<span data-ttu-id="fc1cc-114">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="fc1cc-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
