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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939815"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="26bc2-102">Metodo ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="26bc2-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="26bc2-103">Restituisce l'uniform resource locator () per questo documento.</span><span class="sxs-lookup"><span data-stu-id="26bc2-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26bc2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26bc2-104">Syntax</span></span>  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26bc2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="26bc2-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="26bc2-106">[in] Le dimensioni, in caratteri, del `szURL` buffer.</span><span class="sxs-lookup"><span data-stu-id="26bc2-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="26bc2-107">[out] Un puntatore a una variabile che riceve le dimensioni dell'URL, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="26bc2-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="26bc2-108">[out] Buffer che contiene l'URL.</span><span class="sxs-lookup"><span data-stu-id="26bc2-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26bc2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="26bc2-109">Return Value</span></span>  
 <span data-ttu-id="26bc2-110">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="26bc2-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26bc2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26bc2-111">See also</span></span>

- [<span data-ttu-id="26bc2-112">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="26bc2-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
