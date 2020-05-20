---
title: Metodo ISymUnmanagedWriter::DefineConstant
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
ms.openlocfilehash: 200e68abb3f176c267045bf2a5e7e35d18400519
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610093"
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="6cce2-102">Metodo ISymUnmanagedWriter::DefineConstant</span><span class="sxs-lookup"><span data-stu-id="6cce2-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="6cce2-103">Definisce un nome per un valore costante.</span><span class="sxs-lookup"><span data-stu-id="6cce2-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cce2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6cce2-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cce2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6cce2-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="6cce2-106">in Puntatore a un oggetto `WCHAR` che definisce il nome della costante.</span><span class="sxs-lookup"><span data-stu-id="6cce2-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="6cce2-107">in Valore della costante.</span><span class="sxs-lookup"><span data-stu-id="6cce2-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="6cce2-108">[in] Dimensione della matrice `signature`.</span><span class="sxs-lookup"><span data-stu-id="6cce2-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="6cce2-109">in Firma del tipo per la costante.</span><span class="sxs-lookup"><span data-stu-id="6cce2-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6cce2-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6cce2-110">Return Value</span></span>  
 <span data-ttu-id="6cce2-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6cce2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cce2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6cce2-112">Requirements</span></span>  
 <span data-ttu-id="6cce2-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6cce2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cce2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cce2-114">See also</span></span>

- [<span data-ttu-id="6cce2-115">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="6cce2-115">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="6cce2-116">Metodo DefineConstant2</span><span class="sxs-lookup"><span data-stu-id="6cce2-116">DefineConstant2 Method</span></span>](isymunmanagedwriter2-defineconstant2-method.md)
