---
title: Metodo ISymUnmanagedDocument::GetSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59420cfd29c3228aece9fc5ae02b950db6099ea0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939857"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="e8b9e-102">Metodo ISymUnmanagedDocument::GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="e8b9e-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="e8b9e-103">Restituisce l'intervallo specificato dell'origine incorporata al buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="e8b9e-104">Il buffer deve essere sufficientemente grande da contenere l'origine.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b9e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8b9e-105">Syntax</span></span>  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8b9e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8b9e-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="e8b9e-107">[in] La riga iniziale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="e8b9e-108">[in] La colonna iniziale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="e8b9e-109">[in] La riga finale nel documento corrente.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="e8b9e-110">[in] La colonna finale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="e8b9e-111">[in] Le dimensioni dell'origine, in byte.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="e8b9e-112">[out] Puntatore a una variabile che riceve le dimensioni di origine.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="e8b9e-113">[out] Le dimensioni e la lunghezza dell'intervallo specificato del documento di origine, in byte.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8b9e-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e8b9e-114">Return Value</span></span>  
 <span data-ttu-id="e8b9e-115">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e8b9e-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b9e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8b9e-116">See also</span></span>

- [<span data-ttu-id="e8b9e-117">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="e8b9e-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
