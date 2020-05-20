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
ms.openlocfilehash: 451cfecde7e14fad9d3fed3367112e1fb59796e5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615144"
---
# <a name="isymunmanagedmethodgetsequencepoints-method"></a><span data-ttu-id="bcc7c-102">Metodo ISymUnmanagedMethod::GetSequencePoints</span><span class="sxs-lookup"><span data-stu-id="bcc7c-102">ISymUnmanagedMethod::GetSequencePoints Method</span></span>
<span data-ttu-id="bcc7c-103">Ottiene tutti i punti di sequenza all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-103">Gets all the sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bcc7c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="bcc7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bcc7c-105">Parameters</span></span>  
 `cPoints`  
 <span data-ttu-id="bcc7c-106">in Oggetto `ULONG32` che riceve le dimensioni delle `offsets` matrici, `documents` , `lines` , `columns` , `endLines` e `endColumns` .</span><span class="sxs-lookup"><span data-stu-id="bcc7c-106">[in] A `ULONG32` that receives the size of the `offsets`, `documents`, `lines`, `columns`, `endLines`, and `endColumns` arrays.</span></span>  
  
 `pcPoints`  
 <span data-ttu-id="bcc7c-107">out Puntatore a un oggetto `ULONG32` che riceve la lunghezza del buffer necessaria per contenere i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-107">[out] A pointer to a `ULONG32` that receives the length of the buffer required to contain the sequence points.</span></span>  
  
 `offsets`  
 <span data-ttu-id="bcc7c-108">in Matrice in cui archiviare gli offset MSIL (Microsoft Intermediate Language) dall'inizio del metodo per i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-108">[in] An array in which to store the Microsoft intermediate language (MSIL) offsets from the beginning of the method for the sequence points.</span></span>  
  
 `documents`  
 <span data-ttu-id="bcc7c-109">in Matrice in cui archiviare i documenti in cui si trovano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-109">[in] An array in which to store the documents in which the sequence points are located.</span></span>  
  
 `lines`  
 <span data-ttu-id="bcc7c-110">in Matrice in cui archiviare le righe dei documenti in corrispondenza delle quali si trovano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-110">[in] An array in which to store the lines in the documents at which the sequence points are located.</span></span>  
  
 `columns`  
 <span data-ttu-id="bcc7c-111">in Matrice in cui archiviare le colonne dei documenti in cui si trovano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-111">[in] An array in which to store the columns in the documents at which the sequence points are located.</span></span>  
  
 `endLines`  
 <span data-ttu-id="bcc7c-112">in Matrice di righe nei documenti a cui terminano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-112">[in] The array of lines in the documents at which the sequence points end.</span></span>  
  
 `endColumns`  
 <span data-ttu-id="bcc7c-113">in Matrice di colonne nei documenti a cui terminano i punti di sequenza.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-113">[in] The array of columns in the documents at which the sequence points end.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcc7c-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bcc7c-114">Return Value</span></span>  
 <span data-ttu-id="bcc7c-115">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="bcc7c-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcc7c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bcc7c-116">Requirements</span></span>  
 <span data-ttu-id="bcc7c-117">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="bcc7c-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc7c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bcc7c-118">See also</span></span>

- [<span data-ttu-id="bcc7c-119">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="bcc7c-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
