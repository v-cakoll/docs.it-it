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
ms.openlocfilehash: a11f689f1fa93e1122ffcc78187c4287db7ea534
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427024"
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="9547b-102">Metodo ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="9547b-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="9547b-103">Chiude l'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="9547b-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9547b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9547b-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9547b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9547b-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="9547b-106">[in] L'offset dall'inizio del metodo del punto alla fine dell'ultima istruzione nell'ambito lessicale, in byte.</span><span class="sxs-lookup"><span data-stu-id="9547b-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9547b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9547b-107">Return Value</span></span>  
 <span data-ttu-id="9547b-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9547b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9547b-109">Note</span><span class="sxs-lookup"><span data-stu-id="9547b-109">Remarks</span></span>  
 <span data-ttu-id="9547b-110">Una volta chiuso un ambito, non più variabili possono essere definite all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="9547b-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="9547b-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) per definire successivamente un ambito dell'offset iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="9547b-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="9547b-112">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` saranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="9547b-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="9547b-113">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="9547b-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9547b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9547b-114">Requirements</span></span>  
 <span data-ttu-id="9547b-115">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9547b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9547b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9547b-116">See Also</span></span>  
 [<span data-ttu-id="9547b-117">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="9547b-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
