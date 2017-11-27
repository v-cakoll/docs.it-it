---
title: Metodo ISymUnmanagedWriter::CloseScope
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a8df22e5f9ea2ca294f502fcebf4b2ed5cd7900d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="741c4-102">Metodo ISymUnmanagedWriter::CloseScope</span><span class="sxs-lookup"><span data-stu-id="741c4-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="741c4-103">Chiude l'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="741c4-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="741c4-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="741c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="741c4-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="741c4-106">[in] L'offset dall'inizio del metodo del punto alla fine dell'ultima istruzione nell'ambito lessicale, in byte.</span><span class="sxs-lookup"><span data-stu-id="741c4-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="741c4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="741c4-107">Return Value</span></span>  
 <span data-ttu-id="741c4-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="741c4-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="741c4-109">Note</span><span class="sxs-lookup"><span data-stu-id="741c4-109">Remarks</span></span>  
 <span data-ttu-id="741c4-110">Una volta chiuso un ambito, non più variabili possono essere definite all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="741c4-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="741c4-111">[ISymUnmanagedWriter:: OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) restituisce un identificatore di ambito opaco che può essere utilizzato con [ISymUnmanagedWriter::](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) per definire successivamente un ambito dell'offset iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="741c4-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="741c4-112">In questo caso, gli offset passati a `ISymUnmanagedWriter::OpenScope` e `ISymUnmanagedWriter::CloseScope` saranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="741c4-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="741c4-113">Gli identificatori di ambito sono validi solo nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="741c4-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="741c4-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="741c4-114">Requirements</span></span>  
 <span data-ttu-id="741c4-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="741c4-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741c4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="741c4-116">See Also</span></span>  
 [<span data-ttu-id="741c4-117">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="741c4-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
