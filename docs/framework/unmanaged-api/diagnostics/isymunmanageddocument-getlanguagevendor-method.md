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
ms.openlocfilehash: 0a6830f47d5cac2cf9c84144c18486489b0ec581
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424531"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="347a1-102">Metodo ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="347a1-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="347a1-103">Recupera il fornitore di linguaggio di questo documento.</span><span class="sxs-lookup"><span data-stu-id="347a1-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="347a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="347a1-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="347a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="347a1-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="347a1-106">[out] Puntatore a una variabile che riceve il fornitore di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="347a1-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="347a1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="347a1-107">Return Value</span></span>  
 <span data-ttu-id="347a1-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="347a1-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="347a1-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="347a1-109">See Also</span></span>  
 [<span data-ttu-id="347a1-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="347a1-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
