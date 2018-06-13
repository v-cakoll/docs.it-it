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
ms.openlocfilehash: 53f02499bbc64f1502951ff9fbf16a848e77f0ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430808"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="cfcc3-102">Metodo ISymUnmanagedWriter2::DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="cfcc3-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="cfcc3-103">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="cfcc3-104">Questo metodo può essere chiamato più volte per una variabile con lo stesso nome presente in più posizioni in un ambito.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="cfcc3-105">In questo caso, tuttavia, i valori del `startOffset` e `endOffset` parametri non devono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfcc3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cfcc3-106">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="cfcc3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="cfcc3-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cfcc3-108">[in] Il nome della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="cfcc3-109">[in] Attributi della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="cfcc3-110">[in] Il token di metadati della firma.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="cfcc3-111">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="cfcc3-112">[in] Il primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="cfcc3-113">[in] Il secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="cfcc3-114">[in] Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="cfcc3-115">[in] Offset iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="cfcc3-116">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-116">This parameter is optional.</span></span> <span data-ttu-id="cfcc3-117">Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="cfcc3-118">Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="cfcc3-119">[in] Offset finale della variabile.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="cfcc3-120">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-120">This parameter is optional.</span></span> <span data-ttu-id="cfcc3-121">Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="cfcc3-122">Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cfcc3-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cfcc3-123">Return Value</span></span>  
 <span data-ttu-id="cfcc3-124">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cfcc3-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfcc3-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cfcc3-125">Requirements</span></span>  
 <span data-ttu-id="cfcc3-126">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="cfcc3-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcc3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfcc3-127">See Also</span></span>  
 [<span data-ttu-id="cfcc3-128">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="cfcc3-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="cfcc3-129">Metodo DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="cfcc3-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
