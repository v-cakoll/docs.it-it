---
title: Metodo ISymUnmanagedWriter2::DefineGlobalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: 12475b1ac8a1a81e565aa689eac2ae1a9b55e73a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438277"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="90a0f-102">Metodo ISymUnmanagedWriter2::DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="90a0f-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="90a0f-103">Definisce una singola variabile globale.</span><span class="sxs-lookup"><span data-stu-id="90a0f-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90a0f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90a0f-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90a0f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="90a0f-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="90a0f-106">in Nome della variabile globale.</span><span class="sxs-lookup"><span data-stu-id="90a0f-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="90a0f-107">in Attributi della variabile globale.</span><span class="sxs-lookup"><span data-stu-id="90a0f-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="90a0f-108">in Token di metadati della firma.</span><span class="sxs-lookup"><span data-stu-id="90a0f-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="90a0f-109">in Tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="90a0f-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="90a0f-110">in Primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="90a0f-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="90a0f-111">in Secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="90a0f-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="90a0f-112">in Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="90a0f-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90a0f-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="90a0f-113">Return Value</span></span>  
 <span data-ttu-id="90a0f-114">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="90a0f-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90a0f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90a0f-115">Requirements</span></span>  
 <span data-ttu-id="90a0f-116">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="90a0f-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90a0f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90a0f-117">See also</span></span>

- [<span data-ttu-id="90a0f-118">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="90a0f-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="90a0f-119">Metodo DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="90a0f-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
