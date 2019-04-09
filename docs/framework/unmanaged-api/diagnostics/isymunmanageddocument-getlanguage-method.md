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
ms.openlocfilehash: 05ce47953358b7025e30080fbbaf288a6c0e879d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104594"
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="ff30a-102">Metodo ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="ff30a-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="ff30a-103">Ottiene l'identificatore di lingua di questo documento</span><span class="sxs-lookup"><span data-stu-id="ff30a-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff30a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ff30a-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff30a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ff30a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ff30a-106">[out] Puntatore a una variabile che riceve l'identificatore di lingua.</span><span class="sxs-lookup"><span data-stu-id="ff30a-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff30a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ff30a-107">Return Value</span></span>  
 <span data-ttu-id="ff30a-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ff30a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff30a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff30a-109">See also</span></span>

- [<span data-ttu-id="ff30a-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="ff30a-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
