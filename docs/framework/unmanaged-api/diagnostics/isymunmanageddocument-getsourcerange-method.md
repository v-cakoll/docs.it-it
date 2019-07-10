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
ms.openlocfilehash: 981048c10be27900f011afeab55d1c5eb523f734
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776675"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a><span data-ttu-id="86623-102">Metodo ISymUnmanagedDocument::GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="86623-102">ISymUnmanagedDocument::GetSourceRange Method</span></span>
<span data-ttu-id="86623-103">Restituisce l'intervallo specificato dell'origine incorporata al buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="86623-103">Returns the specified range of the embedded source into the given buffer.</span></span> <span data-ttu-id="86623-104">Il buffer deve essere sufficientemente grande da contenere l'origine.</span><span class="sxs-lookup"><span data-stu-id="86623-104">The buffer must be large enough to hold the source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86623-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86623-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="86623-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="86623-106">Parameters</span></span>  
 `startLine`  
 <span data-ttu-id="86623-107">[in] La riga iniziale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="86623-107">[in] The starting line in the current document.</span></span>  
  
 `startColumn`  
 <span data-ttu-id="86623-108">[in] La colonna iniziale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="86623-108">[in] The starting column in the current document.</span></span>  
  
 `endLine`  
 <span data-ttu-id="86623-109">[in] La riga finale nel documento corrente.</span><span class="sxs-lookup"><span data-stu-id="86623-109">[in] The final line in the current document.</span></span>  
  
 `endColumn`  
 <span data-ttu-id="86623-110">[in] La colonna finale del documento corrente.</span><span class="sxs-lookup"><span data-stu-id="86623-110">[in] The final column in the current document.</span></span>  
  
 `cSourceBytes`  
 <span data-ttu-id="86623-111">[in] Le dimensioni dell'origine, in byte.</span><span class="sxs-lookup"><span data-stu-id="86623-111">[in] The size of the source, in bytes.</span></span>  
  
 `pcSourceBytes`  
 <span data-ttu-id="86623-112">[out] Puntatore a una variabile che riceve le dimensioni di origine.</span><span class="sxs-lookup"><span data-stu-id="86623-112">[out] A pointer to a variable that receives the source size.</span></span>  
  
 `source`  
 <span data-ttu-id="86623-113">[out] Le dimensioni e la lunghezza dell'intervallo specificato del documento di origine, in byte.</span><span class="sxs-lookup"><span data-stu-id="86623-113">[out] The size and length of the specified range of the source document, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86623-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="86623-114">Return Value</span></span>  
 <span data-ttu-id="86623-115">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="86623-115">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86623-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86623-116">See also</span></span>

- [<span data-ttu-id="86623-117">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="86623-117">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
