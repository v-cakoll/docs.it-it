---
title: Metodo ISymUnmanagedDocument::GetLanguageVendor
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd01dcbd45ecae84ccccffb510c20f580ae8c598
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939828"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="315a0-102">Metodo ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="315a0-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="315a0-103">Ottiene il fornitore di linguaggio di questo documento.</span><span class="sxs-lookup"><span data-stu-id="315a0-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="315a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="315a0-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="315a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="315a0-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="315a0-106">[out] Puntatore a una variabile che riceve il fornitore del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="315a0-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="315a0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="315a0-107">Return Value</span></span>  
 <span data-ttu-id="315a0-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="315a0-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="315a0-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="315a0-109">See also</span></span>

- [<span data-ttu-id="315a0-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="315a0-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
