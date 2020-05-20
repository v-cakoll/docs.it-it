---
title: Metodo ISymUnmanagedDocument::FindClosestLine
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.FindClosestLine
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::FindClosestLine
helpviewer_keywords:
- FindClosestLine method [.NET Framework debugging]
- ISymUnmanagedDocument::FindClosestLine method [.NET Framework debugging]
ms.assetid: 628f2a04-e529-407d-841e-3b3da219a9cb
topic_type:
- apiref
ms.openlocfilehash: 9e6134d39096c4ab157aa545646d83339f92a0b8
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441032"
---
# <a name="isymunmanageddocumentfindclosestline-method"></a><span data-ttu-id="dbf98-102">Metodo ISymUnmanagedDocument::FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="dbf98-102">ISymUnmanagedDocument::FindClosestLine Method</span></span>
<span data-ttu-id="dbf98-103">Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga del documento che può essere o meno un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="dbf98-103">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbf98-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbf98-104">Syntax</span></span>  
  
```cpp  
HRESULT FindClosestLine(  
    [in]  ULONG32  line,  
    [out, retval] ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbf98-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dbf98-105">Parameters</span></span>  
 `line`  
 <span data-ttu-id="dbf98-106">in Riga di questo documento.</span><span class="sxs-lookup"><span data-stu-id="dbf98-106">[in] A line in this document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="dbf98-107">out Puntatore a una variabile che riceve la riga.</span><span class="sxs-lookup"><span data-stu-id="dbf98-107">[out] A pointer to a variable that receives the line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbf98-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dbf98-108">Return Value</span></span>  
 <span data-ttu-id="dbf98-109">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="dbf98-109">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf98-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbf98-110">See also</span></span>

- [<span data-ttu-id="dbf98-111">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="dbf98-111">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
