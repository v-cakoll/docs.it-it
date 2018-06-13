---
title: Metodo ISymUnmanagedDocument::GetSourceLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3341159600c85915cd3c1a138265dc386edbb766
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424118"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="ba160-102">Metodo ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="ba160-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="ba160-103">Recupera la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="ba160-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba160-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba160-104">Syntax</span></span>  
  
```  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ba160-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba160-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ba160-106">[out] Un puntatore a una variabile che indica la lunghezza, espressa in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="ba160-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba160-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba160-107">Return Value</span></span>  
 <span data-ttu-id="ba160-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ba160-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba160-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba160-109">See Also</span></span>  
 [<span data-ttu-id="ba160-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="ba160-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
