---
title: Metodo ISymUnmanagedDocument::GetURL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetURL
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 591383fee2f9b22a00956193555c719e72d722bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="e2fb6-102">Metodo ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="e2fb6-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="e2fb6-103">Restituisce l'uniform resource locator () per questo documento.</span><span class="sxs-lookup"><span data-stu-id="e2fb6-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2fb6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2fb6-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2fb6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2fb6-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="e2fb6-106">[in] La dimensione, in caratteri, del `szURL` buffer.</span><span class="sxs-lookup"><span data-stu-id="e2fb6-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="e2fb6-107">[out] Un puntatore a una variabile che riceve le dimensioni dell'URL, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="e2fb6-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="e2fb6-108">[out] Buffer contenente l'URL.</span><span class="sxs-lookup"><span data-stu-id="e2fb6-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2fb6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e2fb6-109">Return Value</span></span>  
 <span data-ttu-id="e2fb6-110">S_OK se il metodo ha esito positivo. in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e2fb6-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2fb6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2fb6-111">See Also</span></span>  
 [<span data-ttu-id="e2fb6-112">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="e2fb6-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
