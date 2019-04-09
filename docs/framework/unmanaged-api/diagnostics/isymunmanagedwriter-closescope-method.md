---
title: Metodo ISymUnmanagedWriter::CloseScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ab30e1f80be71b42a131afe68e38f0b2731ae60
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212947"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="18a9e-102">Metodo ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="18a9e-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="18a9e-103">Chiude l'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="18a9e-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a9e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18a9e-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18a9e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18a9e-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="18a9e-106">[in] L'offset dall'inizio del metodo del punto alla fine dell'ultima istruzione nell'ambito lessicale, in byte.</span><span class="sxs-lookup"><span data-stu-id="18a9e-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18a9e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="18a9e-107">Return Value</span></span>  
 <span data-ttu-id="18a9e-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="18a9e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18a9e-109">Note</span><span class="sxs-lookup"><span data-stu-id="18a9e-109">Remarks</span></span>  
 <span data-ttu-id="18a9e-110">Una volta chiuso un ambito, non altre variabili possono essere definite all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="18a9e-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="18a9e-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere usato con [SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) per definire successivamente un ambito dell'offset iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="18a9e-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="18a9e-112">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` saranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="18a9e-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="18a9e-113">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="18a9e-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18a9e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18a9e-114">Requirements</span></span>  
 <span data-ttu-id="18a9e-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="18a9e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18a9e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18a9e-116">See also</span></span>

- [<span data-ttu-id="18a9e-117">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="18a9e-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
