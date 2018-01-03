---
title: Metodo ISymUnmanagedDocument::GetLanguage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetLanguage
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetLanguage
helpviewer_keywords:
- ISymUnmanagedDocument::GetLanguage method [.NET Framework debugging]
- GetLanguage method [.NET Framework debugging]
ms.assetid: c6639418-e9f2-4a99-8ce2-ec9876e0bc79
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31fdd2caaf877372fa28693cdc5b09ddf601427c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocumentgetlanguage-method"></a><span data-ttu-id="a84b4-102">Metodo ISymUnmanagedDocument::GetLanguage</span><span class="sxs-lookup"><span data-stu-id="a84b4-102">ISymUnmanagedDocument::GetLanguage Method</span></span>
<span data-ttu-id="a84b4-103">Ottiene l'identificatore di lingua di questo documento</span><span class="sxs-lookup"><span data-stu-id="a84b4-103">Gets the language identifier of this document</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a84b4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a84b4-104">Syntax</span></span>  
  
```  
HRESULT GetLanguage(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a84b4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a84b4-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a84b4-106">[out] Puntatore a una variabile che riceve l'identificatore di lingua.</span><span class="sxs-lookup"><span data-stu-id="a84b4-106">[out] A pointer to a variable that receives the language identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a84b4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a84b4-107">Return Value</span></span>  
 <span data-ttu-id="a84b4-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a84b4-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a84b4-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a84b4-109">See Also</span></span>  
 [<span data-ttu-id="a84b4-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="a84b4-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
