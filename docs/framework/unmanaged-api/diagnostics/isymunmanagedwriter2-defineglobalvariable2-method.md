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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9f35e3c9327a3945e6ddce85be52b757294b39aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429724"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="71210-102">Metodo ISymUnmanagedWriter2::DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="71210-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="71210-103">Definisce una singola variabile globale.</span><span class="sxs-lookup"><span data-stu-id="71210-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71210-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71210-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71210-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71210-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="71210-106">[in] Il nome della variabile globale.</span><span class="sxs-lookup"><span data-stu-id="71210-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="71210-107">[in] Attributi della variabile globale.</span><span class="sxs-lookup"><span data-stu-id="71210-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="71210-108">[in] Il token di metadati della firma.</span><span class="sxs-lookup"><span data-stu-id="71210-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="71210-109">[in] Il tipo di indirizzo.</span><span class="sxs-lookup"><span data-stu-id="71210-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="71210-110">[in] Il primo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="71210-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="71210-111">[in] Il secondo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="71210-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="71210-112">[in] Terzo indirizzo per la specifica del parametro.</span><span class="sxs-lookup"><span data-stu-id="71210-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71210-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="71210-113">Return Value</span></span>  
 <span data-ttu-id="71210-114">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="71210-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71210-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71210-115">Requirements</span></span>  
 <span data-ttu-id="71210-116">**Intestazione:** CorSym. idl</span><span class="sxs-lookup"><span data-stu-id="71210-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71210-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71210-117">See Also</span></span>  
 [<span data-ttu-id="71210-118">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="71210-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="71210-119">Metodo DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="71210-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
