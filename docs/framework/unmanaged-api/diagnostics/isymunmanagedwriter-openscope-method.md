---
title: Metodo ISymUnmanagedWriter::OpenScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenScope
helpviewer_keywords:
- OpenScope method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::OpenScope method [.NET Framework debugging]
ms.assetid: dbea0644-3873-4329-90b8-624163e87467
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f56bc14b096b5086db1fc8d046ed699559381fb0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriteropenscope-method"></a><span data-ttu-id="04721-102">Metodo ISymUnmanagedWriter::OpenScope</span><span class="sxs-lookup"><span data-stu-id="04721-102">ISymUnmanagedWriter::OpenScope Method</span></span>
<span data-ttu-id="04721-103">Apre un nuovo ambito lessicale nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="04721-103">Opens a new lexical scope in the current method.</span></span> <span data-ttu-id="04721-104">L'ambito diventa il nuovo ambito corrente e viene inserito nello stack di ambiti.</span><span class="sxs-lookup"><span data-stu-id="04721-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="04721-105">Gli ambiti devono formare una gerarchia.</span><span class="sxs-lookup"><span data-stu-id="04721-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="04721-106">Elementi di pari livello non è consentiti si sovrappongono.</span><span class="sxs-lookup"><span data-stu-id="04721-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04721-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="04721-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32 startOffset,  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04721-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="04721-108">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="04721-109">[in] L'offset della prima istruzione nell'ambito lessicale, in byte, dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="04721-109">[in] The offset of the first instruction in the lexical scope, in bytes, from the beginning of the method.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="04721-110">[out] Un puntatore a un `ULONG32` che riceve l'identificatore di ambito.</span><span class="sxs-lookup"><span data-stu-id="04721-110">[out] A pointer to a `ULONG32` that receives the scope identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04721-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="04721-111">Return Value</span></span>  
 <span data-ttu-id="04721-112">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="04721-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04721-113">Note</span><span class="sxs-lookup"><span data-stu-id="04721-113">Remarks</span></span>  
 <span data-ttu-id="04721-114">`ISymUnmanagedWriter::OpenScope`Restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) per definire un ambito dell'offset iniziale e finale in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="04721-114">`ISymUnmanagedWriter::OpenScope` returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="04721-115">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e [ISymUnmanagedWriter:: CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="04721-115">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="04721-116">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="04721-116">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04721-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04721-117">Requirements</span></span>  
 <span data-ttu-id="04721-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="04721-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04721-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04721-119">See Also</span></span>  
 [<span data-ttu-id="04721-120">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="04721-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
