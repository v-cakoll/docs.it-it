---
title: Metodo ISymUnmanagedDocument::GetLanguageVendor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetLanguageVendor
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 72fffae9995f44be9a9359c16bb876d79c9a8242
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="75f2a-102">Metodo ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="75f2a-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>
<span data-ttu-id="75f2a-103">Recupera il fornitore di linguaggio di questo documento.</span><span class="sxs-lookup"><span data-stu-id="75f2a-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75f2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75f2a-104">Syntax</span></span>  
  
```  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75f2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75f2a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="75f2a-106">[out] Puntatore a una variabile che riceve il fornitore di linguaggio.</span><span class="sxs-lookup"><span data-stu-id="75f2a-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75f2a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="75f2a-107">Return Value</span></span>  
 <span data-ttu-id="75f2a-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="75f2a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f2a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f2a-109">See Also</span></span>  
 [<span data-ttu-id="75f2a-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="75f2a-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
