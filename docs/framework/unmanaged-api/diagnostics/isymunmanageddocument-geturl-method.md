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
ms.openlocfilehash: 3685707f1983ffec413e9cea2df5034ac53f643a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615592"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="f0500-102">Metodo ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="f0500-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="f0500-103">Restituisce l'URL (Uniform Resource Locator) per questo documento.</span><span class="sxs-lookup"><span data-stu-id="f0500-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0500-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0500-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0500-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f0500-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="f0500-106">in Dimensione, in caratteri, del `szURL` buffer.</span><span class="sxs-lookup"><span data-stu-id="f0500-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="f0500-107">out Puntatore a una variabile che riceve le dimensioni dell'URL, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="f0500-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="f0500-108">out Buffer contenente l'URL.</span><span class="sxs-lookup"><span data-stu-id="f0500-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0500-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f0500-109">Return Value</span></span>  
 <span data-ttu-id="f0500-110">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f0500-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0500-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0500-111">See also</span></span>

- [<span data-ttu-id="f0500-112">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="f0500-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
