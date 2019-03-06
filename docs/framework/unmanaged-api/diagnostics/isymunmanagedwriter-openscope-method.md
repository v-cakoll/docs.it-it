---
title: Metodo ISymUnmanagedWriter::OpenScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ccaaee614b1ec4d03271e70338fff82d629a7c28
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468463"
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="bacaa-102">Metodo ISymUnmanagedWriter::OpenScope</span><span class="sxs-lookup"><span data-stu-id="bacaa-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="bacaa-103">Apre un nuovo ambito lessicale nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="bacaa-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="bacaa-104">L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti.</span><span class="sxs-lookup"><span data-stu-id="bacaa-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="bacaa-105">Gli ambiti devono formare una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="bacaa-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="bacaa-106">Elementi di pari livello non possono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="bacaa-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bacaa-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bacaa-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bacaa-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="bacaa-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="bacaa-109">[in] L'offset della prima istruzione dell'ambito lessicale, in byte, dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="bacaa-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="bacaa-110">[out] Un puntatore a un `ULONG32` che riceve l'identificatore di ambito.</span><span class="sxs-lookup"><span data-stu-id="bacaa-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bacaa-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bacaa-111">Return Value</span></span>  
 <span data-ttu-id="bacaa-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="bacaa-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bacaa-113">Note</span><span class="sxs-lookup"><span data-stu-id="bacaa-113">Remarks</span></span>  
 <span data-ttu-id="bacaa-114">`ISymUnmanagedWriter::OpenScope` Restituisce un identificatore di ambito opaco che può essere usato con [SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) per definire un ambito dell'offset iniziale e finale in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="bacaa-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="bacaa-115">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="bacaa-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="bacaa-116">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="bacaa-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bacaa-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bacaa-117">Requirements</span></span>  
 <span data-ttu-id="bacaa-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bacaa-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacaa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bacaa-119">See also</span></span>
- [<span data-ttu-id="bacaa-120">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="bacaa-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
