---
title: Metodo ISymUnmanagedWriter2::DefineLocalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d336b35e91abd1b7180c2b918edeba2e1eccdbde
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499589"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="7e8d8-102">Metodo ISymUnmanagedWriter2::DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="7e8d8-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="7e8d8-103">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="7e8d8-104">Questo metodo può essere chiamato più volte per una variabile con lo stesso nome presente in più posizioni in un ambito.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="7e8d8-105">In questo caso, tuttavia, i valori del `startOffset` e `endOffset` parametri non devono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e8d8-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e8d8-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e8d8-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e8d8-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="7e8d8-108">[in] Il nome della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="7e8d8-109">[in] Attributi della variabile locali.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="7e8d8-110">[in] Il token di metadati della firma.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="7e8d8-111">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="7e8d8-112">[in] Il primo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="7e8d8-113">[in] Il secondo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="7e8d8-114">[in] Terzo indirizzo relativo al parametro specificato.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="7e8d8-115">[in] Offset iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="7e8d8-116">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-116">This parameter is optional.</span></span> <span data-ttu-id="7e8d8-117">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="7e8d8-118">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="7e8d8-119">[in] Offset finale per la variabile.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="7e8d8-120">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-120">This parameter is optional.</span></span> <span data-ttu-id="7e8d8-121">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="7e8d8-122">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e8d8-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7e8d8-123">Return Value</span></span>  
 <span data-ttu-id="7e8d8-124">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7e8d8-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e8d8-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e8d8-125">Requirements</span></span>  
 <span data-ttu-id="7e8d8-126">**Intestazione:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="7e8d8-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e8d8-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e8d8-127">See also</span></span>
- [<span data-ttu-id="7e8d8-128">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="7e8d8-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="7e8d8-129">Metodo DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="7e8d8-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
