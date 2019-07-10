---
title: Metodo ISymUnmanagedWriter::DefineField
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 37794d40b4b379c5d3a05935cf1f2b7b3da11baa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777372"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="c94bc-102">Metodo ISymUnmanagedWriter::DefineField</span><span class="sxs-lookup"><span data-stu-id="c94bc-102">ISymUnmanagedWriter::DefineField Method</span></span>
<span data-ttu-id="c94bc-103">Definisce una singola variabile che non è incluso un metodo.</span><span class="sxs-lookup"><span data-stu-id="c94bc-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="c94bc-104">Questo metodo è utilizzato per alcuni campi nelle classi, campi di bit e così via.</span><span class="sxs-lookup"><span data-stu-id="c94bc-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c94bc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c94bc-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c94bc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c94bc-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="c94bc-107">[in] Il tipo di metadati o il metodo token.</span><span class="sxs-lookup"><span data-stu-id="c94bc-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="c94bc-108">[in] Il nome del campo.</span><span class="sxs-lookup"><span data-stu-id="c94bc-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="c94bc-109">[in] Gli attributi di campo.</span><span class="sxs-lookup"><span data-stu-id="c94bc-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="c94bc-110">[in] Oggetto `ULONG32` vale a dire le dimensioni, in caratteri, del buffer necessaria per contenere la firma del campo.</span><span class="sxs-lookup"><span data-stu-id="c94bc-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="c94bc-111">[in] Matrice di firme di campo.</span><span class="sxs-lookup"><span data-stu-id="c94bc-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="c94bc-112">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="c94bc-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="c94bc-113">[in] Il primo indirizzo relativo al campo specificato.</span><span class="sxs-lookup"><span data-stu-id="c94bc-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="c94bc-114">[in] Il secondo indirizzo relativo al campo specificato.</span><span class="sxs-lookup"><span data-stu-id="c94bc-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="c94bc-115">[in] Terzo indirizzo relativo al campo specificato.</span><span class="sxs-lookup"><span data-stu-id="c94bc-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c94bc-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c94bc-116">Return Value</span></span>  
 <span data-ttu-id="c94bc-117">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c94bc-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c94bc-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c94bc-118">Requirements</span></span>  
 <span data-ttu-id="c94bc-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c94bc-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c94bc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c94bc-120">See also</span></span>

- [<span data-ttu-id="c94bc-121">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="c94bc-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
