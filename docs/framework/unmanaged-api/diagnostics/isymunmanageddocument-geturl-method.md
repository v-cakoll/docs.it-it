---
title: Metodo ISymUnmanagedDocument::GetURL
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15b42bb72975fad4c1830a961f83d9e3065d055b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187460"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="f7340-102">Metodo ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="f7340-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="f7340-103">Restituisce l'uniform resource locator () per questo documento.</span><span class="sxs-lookup"><span data-stu-id="f7340-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7340-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7340-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7340-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7340-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="f7340-106">[in] Le dimensioni, in caratteri, del `szURL` buffer.</span><span class="sxs-lookup"><span data-stu-id="f7340-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="f7340-107">[out] Un puntatore a una variabile che riceve le dimensioni dell'URL, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="f7340-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="f7340-108">[out] Buffer che contiene l'URL.</span><span class="sxs-lookup"><span data-stu-id="f7340-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7340-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f7340-109">Return Value</span></span>  
 <span data-ttu-id="f7340-110">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f7340-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7340-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7340-111">See also</span></span>

- [<span data-ttu-id="f7340-112">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="f7340-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
