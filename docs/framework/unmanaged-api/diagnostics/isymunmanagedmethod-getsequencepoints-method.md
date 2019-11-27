---
title: Metodo ISymUnmanagedMethod::GetSequencePoints
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSequencePoints
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSequencePoints
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePoints method [.NET Framework debugging]
- GetSequencePoints method [.NET Framework debugging]
ms.assetid: f909ac48-3d8f-49fb-a369-e3d9959151cd
topic_type:
- apiref
ms.openlocfilehash: 75d477af7395a9b7d3328b2a5787f810733f3749
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448883"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="4b6c8-102">Metodo ISymUnmanagedMethod::GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="4b6c8-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="4b6c8-103">Ottiene tutti i punti di sequenza all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b6c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b6c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSequencePoints(  
    [in]  ULONG32  cPoints,  
    [out] ULONG32  *pcPoints,  
    [in, size_is(cPoints)] ULONG32  offsets[],  
    [in, size_is(cPoints)] ISymUnmanagedDocument* documents[],  
    [in, size_is(cPoints)] ULONG32  lines[],  
    [in, size_is(cPoints)] ULONG32  columns[],  
    [in, size_is(cPoints)] ULONG32  endLines[],  
    [in, size_is(cPoints)] ULONG32  endColumns[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b6c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b6c8-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="4b6c8-106">in `ULONG32` che riceve la dimensione delle matrici `offsets`, `documents`, `lines`, `columns`, `endLines`e `endColumns`.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="4b6c8-107">out Puntatore a un `ULONG32` che riceve la lunghezza del buffer necessaria per contenere i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="4b6c8-108">in Matrice in cui archiviare gli offset MSIL (Microsoft Intermediate Language) dall'inizio del metodo per i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="4b6c8-109">in Matrice in cui archiviare i documenti in cui si trovano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="4b6c8-110">in Matrice in cui archiviare le righe dei documenti in corrispondenza delle quali si trovano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="4b6c8-111">in Matrice in cui archiviare le colonne dei documenti in cui si trovano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="4b6c8-112">in Matrice di righe nei documenti a cui terminano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="4b6c8-113">in Matrice di colonne nei documenti a cui terminano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b6c8-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4b6c8-114">Return Value</span></span>  
 <span data-ttu-id="4b6c8-115">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4b6c8-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b6c8-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b6c8-116">Requirements</span></span>  
 <span data-ttu-id="4b6c8-117">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="4b6c8-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6c8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b6c8-118">See also</span></span>

- [<span data-ttu-id="4b6c8-119">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="4b6c8-119">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
