---
title: Metodo ISymUnmanagedReader::GetDocument
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocument
helpviewer_keywords:
- ISymUnmanagedReader::GetDocument method [.NET Framework debugging]
- GetDocument method [.NET Framework debugging]
ms.assetid: bb203853-6a6d-4027-b9e9-603a7f28b9d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00ded0e7e88cacbcedb66e1cef27e4f5eaaf4d29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocument-method"></a><span data-ttu-id="378e5-102">Metodo ISymUnmanagedReader::GetDocument</span><span class="sxs-lookup"><span data-stu-id="378e5-102">ISymUnmanagedReader::GetDocument Method</span></span>
<span data-ttu-id="378e5-103">Trova un documento.</span><span class="sxs-lookup"><span data-stu-id="378e5-103">Finds a document.</span></span> <span data-ttu-id="378e5-104">Il linguaggio del documento, fornitore e tipo sono facoltativi.</span><span class="sxs-lookup"><span data-stu-id="378e5-104">The document language, vendor, and type are optional.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378e5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="378e5-105">Syntax</span></span>  
  
```  
HRESULT GetDocument (  
    [in]  WCHAR  *url,  
    [in]  GUID   language,  
    [in]  GUID   languageVendor,  
    [in]  GUID   documentType,  
    [out, retval] ISymUnmanagedDocument** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="378e5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="378e5-106">Parameters</span></span>  
 `url`  
 <span data-ttu-id="378e5-107">[in] L'URL che identifica il documento.</span><span class="sxs-lookup"><span data-stu-id="378e5-107">[in] The URL that identifies the document.</span></span>  
  
 `language`  
 <span data-ttu-id="378e5-108">[in] Il linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="378e5-108">[in] The document language.</span></span> <span data-ttu-id="378e5-109">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="378e5-109">This parameter is optional.</span></span>  
  
 `languageVendor`  
 <span data-ttu-id="378e5-110">[in] L'identità del fornitore del linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="378e5-110">[in] The identity of the vendor for the document language.</span></span> <span data-ttu-id="378e5-111">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="378e5-111">This parameter is optional.</span></span>  
  
 `documentType`  
 <span data-ttu-id="378e5-112">[in] Il tipo del documento.</span><span class="sxs-lookup"><span data-stu-id="378e5-112">[in] The type of the document.</span></span> <span data-ttu-id="378e5-113">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="378e5-113">This parameter is optional.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="378e5-114">[out] Puntatore a interfaccia restituito.</span><span class="sxs-lookup"><span data-stu-id="378e5-114">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="378e5-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="378e5-115">Return Value</span></span>  
 <span data-ttu-id="378e5-116">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="378e5-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="378e5-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="378e5-117">Requirements</span></span>  
 <span data-ttu-id="378e5-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="378e5-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="378e5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="378e5-119">See Also</span></span>  
 [<span data-ttu-id="378e5-120">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="378e5-120">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
