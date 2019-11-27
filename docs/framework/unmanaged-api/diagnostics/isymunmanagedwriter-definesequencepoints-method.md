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
ms.openlocfilehash: 63ba108bc234e566450bb019afc63acb4e75ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427992"
---
# <a name="isymunmanagedwriterdefinesequencepoints-method"></a><span data-ttu-id="7c050-102">Metodo ISymUnmanagedWriter::DefineSequencePoints</span><span class="sxs-lookup"><span data-stu-id="7c050-102">ISymUnmanagedWriter::DefineSequencePoints Method</span></span>
<span data-ttu-id="7c050-103">Definisce un gruppo di punti di sequenza nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="7c050-103">Defines a group of sequence points within the current method.</span></span> <span data-ttu-id="7c050-104">Ogni riga iniziale e colonna iniziale definiscono l'inizio di un'istruzione all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="7c050-104">Each starting line and starting column define the start of a statement within a method.</span></span> <span data-ttu-id="7c050-105">Ogni riga finale e colonna finale definiscono la fine di un'istruzione all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="7c050-105">Each ending line and ending column define the end of a statement within a method.</span></span> <span data-ttu-id="7c050-106">Le matrici devono essere ordinate in ordine crescente di offset.</span><span class="sxs-lookup"><span data-stu-id="7c050-106">The arrays should be sorted in increasing order of offsets.</span></span> <span data-ttu-id="7c050-107">L'offset viene sempre misurato dall'inizio del metodo, espresso in byte.</span><span class="sxs-lookup"><span data-stu-id="7c050-107">The offset is always measured from the start of the method, in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c050-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c050-108">Syntax</span></span>  
  
```cpp  
HRESULT DefineSequencePoints(  
    [in] ISymUnmanagedDocumentWriter*  document,  
    [in] ULONG32 spCount,  
    [in, size_is(spCount)] ULONG32     offsets[],  
    [in, size_is(spCount)] ULONG32     lines[],  
    [in, size_is(spCount)] ULONG32     columns[],  
    [in, size_is(spCount)] ULONG32     endLines[],  
    [in, size_is(spCount)] ULONG32     endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c050-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c050-109">Parameters</span></span>  
 `document`  
 <span data-ttu-id="7c050-110">in Oggetto documento per il quale vengono definiti i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="7c050-110">[in] The document object for which the sequence points are being defined.</span></span>  
  
 `spCount`  
 <span data-ttu-id="7c050-111">in `ULONG32` che indica le dimensioni di ognuno dei buffer `offsets`, `lines`, `columns`, `endLines`e `endColumns`.</span><span class="sxs-lookup"><span data-stu-id="7c050-111">[in] A `ULONG32` that indicates the size of each of the `offsets`, `lines`, `columns`, `endLines`, and `endColumns` buffers.</span></span>  
  
 `offsets`  
 <span data-ttu-id="7c050-112">in Offset dei punti di sequenza misurato a partire dall'inizio del metodo.</span><span class="sxs-lookup"><span data-stu-id="7c050-112">[in] The offset of the sequence points measured from the beginning of the method.</span></span>  
  
 `lines`  
 <span data-ttu-id="7c050-113">in Numeri di riga iniziali dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="7c050-113">[in] The starting line numbers of the sequence points.</span></span>  
  
 `columns`  
 <span data-ttu-id="7c050-114">in Numeri di colonna iniziali dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="7c050-114">[in] The starting column numbers of the sequence points.</span></span>  
  
 `endLines`  
 <span data-ttu-id="7c050-115">in Numeri di riga finali dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="7c050-115">[in] The ending line numbers of the sequence points.</span></span> <span data-ttu-id="7c050-116">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7c050-116">This parameter is optional.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="7c050-117">in Numeri di colonna finali dei punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="7c050-117">[in] The ending column numbers of the sequence points.</span></span> <span data-ttu-id="7c050-118">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="7c050-118">This parameter is optional.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c050-119">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c050-119">Return Value</span></span>  
 <span data-ttu-id="7c050-120">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7c050-120">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c050-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c050-121">Requirements</span></span>  
 <span data-ttu-id="7c050-122">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="7c050-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c050-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c050-123">See also</span></span>

- [<span data-ttu-id="7c050-124">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="7c050-124">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
