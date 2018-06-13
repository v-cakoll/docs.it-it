---
title: Metodo ISymUnmanagedMethod::GetRanges
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRanges
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRanges
helpviewer_keywords:
- ISymUnmanagedMethod::GetRanges method [.NET Framework debugging]
- GetRanges method [.NET Framework debugging]
ms.assetid: a85283d8-379c-417a-9736-ddeeef9bcf50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32036058924aaf79fa7282144ced75040bc1f825
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426020"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="ac9a7-102">Metodo ISymUnmanagedMethod::GetRanges</span><span class="sxs-lookup"><span data-stu-id="ac9a7-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="ac9a7-103">Data una posizione in un documento, restituisce una matrice di coppie di offset iniziali e finali che corrispondono agli intervalli di Microsoft intermediate language (MSIL) che la posizione all'interno del metodo.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="ac9a7-104">La matrice è una matrice di interi e ha il formato [inizio, fine, inizio, fine].</span><span class="sxs-lookup"><span data-stu-id="ac9a7-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="ac9a7-105">Il numero di coppie di intervallo è la lunghezza della matrice divisa 2.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9a7-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac9a7-106">Syntax</span></span>  
  
```  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac9a7-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac9a7-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="ac9a7-108">[in] Il documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="ac9a7-109">[in] Riga del documento corrispondente agli intervalli.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="ac9a7-110">[in] Colonna del documento corrispondente agli intervalli.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="ac9a7-111">[in] Dimensione della matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="ac9a7-112">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="ac9a7-113">[out] Puntatore al buffer che riceve gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac9a7-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac9a7-114">Return Value</span></span>  
 <span data-ttu-id="ac9a7-115">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ac9a7-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9a7-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac9a7-116">Requirements</span></span>  
 <span data-ttu-id="ac9a7-117">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ac9a7-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9a7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac9a7-118">See Also</span></span>  
 [<span data-ttu-id="ac9a7-119">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="ac9a7-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
