---
title: Metodo ISymUnmanagedDocument::GetLanguage
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguage
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7fe5686f516f967ffd182788add643387cb8af9a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473968"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="948cd-102">Metodo ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="948cd-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="948cd-103">Ottiene l'identificatore di lingua di questo documento</span><span class="sxs-lookup"><span data-stu-id="948cd-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="948cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="948cd-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="948cd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="948cd-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="948cd-106">[out] Puntatore a una variabile che riceve l'identificatore di lingua.</span><span class="sxs-lookup"><span data-stu-id="948cd-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="948cd-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="948cd-107">Return Value</span></span>  
 <span data-ttu-id="948cd-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="948cd-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="948cd-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="948cd-109">See also</span></span>
- [<span data-ttu-id="948cd-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="948cd-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
