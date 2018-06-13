---
title: Metodo ISymUnmanagedWriter::DefineSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineSequencePoints
helpviewer_keywords:
- DefineSequencePoints method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineSequencePoints method [.NET Framework debugging]
ms.assetid: 64202baf-be6b-40ba-8162-8cc6c0c9b8e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1dc87b201638bab974c59722a69300977b14cf08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426936"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="79e3b-102">Metodo ISymUnmanagedWriter::DefineSequencePoints</span><span class="sxs-lookup"><span data-stu-id="79e3b-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="79e3b-103">Definisce un gruppo di punti di sequenza nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="79e3b-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="79e3b-104">Ogni riga e colonna iniziale definisce l'inizio di un'istruzione all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="79e3b-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="79e3b-105">Ogni riga e colonna finale definisce la fine di un'istruzione all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="79e3b-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="79e3b-106">Le matrici devono essere ordinate in ordine crescente di offset.</span><span class="sxs-lookup"><span data-stu-id="79e3b-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="79e3b-107">L'offset viene sempre misurato dall'inizio del metodo, in byte.</span><span class="sxs-lookup"><span data-stu-id="79e3b-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79e3b-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79e3b-108">Syntax</span></span>  
  
```  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79e3b-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="79e3b-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="79e3b-110">[in] L'oggetto documento per il quale vengono definiti i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="79e3b-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="79e3b-111">[in] Oggetto `ULONG32` che indica le dimensioni di ogni il `offsets`, `lines`, `columns`, `endLines`, e `endColumns` buffer.</span><span class="sxs-lookup"><span data-stu-id="79e3b-111">[in] A `ULONG32` that that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="79e3b-112">[in] L'offset dei punti di sequenza misurato dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="79e3b-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="79e3b-113">[in] I numeri di riga iniziale dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="79e3b-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="79e3b-114">[in] Numeri di colonna iniziali dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="79e3b-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="79e3b-115">[in] Numeri di riga finali dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="79e3b-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="79e3b-116">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="79e3b-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="79e3b-117">[in] Numeri di colonna finali dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="79e3b-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="79e3b-118">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="79e3b-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79e3b-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="79e3b-119">Return Value</span></span>  
 <span data-ttu-id="79e3b-120">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="79e3b-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79e3b-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79e3b-121">Requirements</span></span>  
 <span data-ttu-id="79e3b-122">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="79e3b-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e3b-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79e3b-123">See Also</span></span>  
 [<span data-ttu-id="79e3b-124">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="79e3b-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
