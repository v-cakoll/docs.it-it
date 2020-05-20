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
ms.openlocfilehash: ac7559bd5431f45b266602404ddde9081aa2944d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614695"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="fd223-102">Metodo ISymUnmanagedWriter2::DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="fd223-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="fd223-103">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="fd223-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="fd223-104">Questo metodo può essere chiamato più volte per una variabile con lo stesso nome che dispone di più case in un ambito.</span><span class="sxs-lookup"><span data-stu-id="fd223-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="fd223-105">In questo caso, tuttavia, i valori dei `startOffset` parametri e `endOffset` non devono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="fd223-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd223-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd223-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="fd223-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd223-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fd223-108">in Nome della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="fd223-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="fd223-109">in Attributi della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="fd223-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="fd223-110">in Token di metadati della firma.</span><span class="sxs-lookup"><span data-stu-id="fd223-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="fd223-111">in Tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="fd223-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="fd223-112">in Primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="fd223-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="fd223-113">in Secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="fd223-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="fd223-114">in Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="fd223-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="fd223-115">in Offset iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="fd223-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="fd223-116">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd223-116">This parameter is optional.</span></span> <span data-ttu-id="fd223-117">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="fd223-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="fd223-118">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="fd223-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="fd223-119">in Offset finale della variabile.</span><span class="sxs-lookup"><span data-stu-id="fd223-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="fd223-120">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="fd223-120">This parameter is optional.</span></span> <span data-ttu-id="fd223-121">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="fd223-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="fd223-122">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="fd223-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd223-123">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fd223-123">Return Value</span></span>  
 <span data-ttu-id="fd223-124">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fd223-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd223-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd223-125">Requirements</span></span>  
 <span data-ttu-id="fd223-126">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="fd223-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd223-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd223-127">See also</span></span>

- [<span data-ttu-id="fd223-128">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="fd223-128">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="fd223-129">Metodo DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="fd223-129">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
