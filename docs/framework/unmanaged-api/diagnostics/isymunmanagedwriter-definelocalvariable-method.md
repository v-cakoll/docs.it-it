---
title: Metodo ISymUnmanagedWriter::DefineLocalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
ms.openlocfilehash: 5730cdd910257d762230f5e54576d5e0a7ac1adb
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614825"
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="8c837-102">Metodo ISymUnmanagedWriter::DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="8c837-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="8c837-103">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="8c837-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="8c837-104">Questo metodo può essere chiamato più volte per una variabile con lo stesso nome che dispone di più case in un ambito.</span><span class="sxs-lookup"><span data-stu-id="8c837-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="8c837-105">In questo caso, tuttavia, i valori dei `startOffset` parametri e `endOffset` non devono sovrapporsi.</span><span class="sxs-lookup"><span data-stu-id="8c837-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c837-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c837-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c837-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c837-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8c837-108">in Puntatore a un oggetto `WCHAR` che definisce il nome della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="8c837-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="8c837-109">in Attributi della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="8c837-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="8c837-110">in Oggetto `ULONG32` che indica la dimensione, in byte, del `signature` buffer.</span><span class="sxs-lookup"><span data-stu-id="8c837-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="8c837-111">in Firma della variabile locale.</span><span class="sxs-lookup"><span data-stu-id="8c837-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="8c837-112">in Tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="8c837-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="8c837-113">in Primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="8c837-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="8c837-114">in Secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="8c837-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="8c837-115">in Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="8c837-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="8c837-116">in Offset iniziale della variabile.</span><span class="sxs-lookup"><span data-stu-id="8c837-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="8c837-117">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c837-117">This parameter is optional.</span></span> <span data-ttu-id="8c837-118">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="8c837-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8c837-119">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="8c837-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="8c837-120">in Offset finale della variabile.</span><span class="sxs-lookup"><span data-stu-id="8c837-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="8c837-121">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8c837-121">This parameter is optional.</span></span> <span data-ttu-id="8c837-122">Se è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito.</span><span class="sxs-lookup"><span data-stu-id="8c837-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8c837-123">Se è un valore diverso da zero, la variabile rientra negli offset dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="8c837-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c837-124">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c837-124">Return Value</span></span>  
 <span data-ttu-id="8c837-125">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8c837-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c837-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c837-126">Requirements</span></span>  
 <span data-ttu-id="8c837-127">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8c837-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c837-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c837-128">See also</span></span>

- [<span data-ttu-id="8c837-129">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="8c837-129">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="8c837-130">Metodo DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="8c837-130">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
- [<span data-ttu-id="8c837-131">Metodo DefineLocalVariable2</span><span class="sxs-lookup"><span data-stu-id="8c837-131">DefineLocalVariable2 Method</span></span>](isymunmanagedwriter2-definelocalvariable2-method.md)
