---
title: Metodo ISymUnmanagedReader::GetDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32b7505a9e512f3c3e3e7a9fcbff40276e98ecf4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759353"
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="092c2-102">Metodo ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="092c2-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="092c2-103">Trova un documento.</span><span class="sxs-lookup"><span data-stu-id="092c2-103">Finds a document.</span></span> <span data-ttu-id="092c2-104">Il linguaggio del documento, fornitore e tipo sono facoltative.</span><span class="sxs-lookup"><span data-stu-id="092c2-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="092c2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="092c2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="092c2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="092c2-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="092c2-107">[in] L'URL che identifica il documento.</span><span class="sxs-lookup"><span data-stu-id="092c2-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="092c2-108">[in] Linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="092c2-108">[in] The document language.</span></span> <span data-ttu-id="092c2-109">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="092c2-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="092c2-110">[in] L'identità del fornitore del linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="092c2-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="092c2-111">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="092c2-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="092c2-112">[in] Il tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="092c2-112">[in] The type of the document.</span></span> <span data-ttu-id="092c2-113">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="092c2-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="092c2-114">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="092c2-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="092c2-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="092c2-115">Return Value</span></span>  
 <span data-ttu-id="092c2-116">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="092c2-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="092c2-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="092c2-117">Requirements</span></span>  
 <span data-ttu-id="092c2-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="092c2-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="092c2-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="092c2-119">See also</span></span>

- [<span data-ttu-id="092c2-120">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="092c2-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
