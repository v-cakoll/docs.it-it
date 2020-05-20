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
ms.openlocfilehash: cd5d1f2d59d3e55ba454f23d2e5dd4b1316c0df4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615176"
---
# <a name="isymunmanagedmethodgetranges-method"></a><span data-ttu-id="87752-102">Metodo ISymUnmanagedMethod::GetRanges</span><span class="sxs-lookup"><span data-stu-id="87752-102">ISymUnmanagedMethod::GetRanges Method</span></span>
<span data-ttu-id="87752-103">Data una posizione in un documento, restituisce una matrice di coppie di offset di inizio e di fine che corrispondono agli intervalli di MSIL (Microsoft Intermediate Language) che la posizione copre all'interno di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="87752-103">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span> <span data-ttu-id="87752-104">La matrice è una matrice di numeri interi e ha il formato [inizio, fine, inizio, fine].</span><span class="sxs-lookup"><span data-stu-id="87752-104">The array is an array of integers and has the format [start, end, start, end].</span></span> <span data-ttu-id="87752-105">Il numero di coppie di intervalli è la lunghezza della matrice divisa per 2.</span><span class="sxs-lookup"><span data-stu-id="87752-105">The number of range pairs is the length of the array divided by 2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87752-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87752-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRanges(  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32                line,  
    [in]  ULONG32                column,  
    [in]  ULONG32                cRanges,  
    [out] ULONG32                *pcRanges,  
    [out, size_is(cRanges),  
        length_is(*pcRanges)] ULONG32 ranges[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87752-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="87752-107">Parameters</span></span>  
 `document`  
 <span data-ttu-id="87752-108">in Documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="87752-108">[in] The document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="87752-109">in Riga del documento corrispondente agli intervalli.</span><span class="sxs-lookup"><span data-stu-id="87752-109">[in] The document line corresponding to the ranges.</span></span>  
  
 `column`  
 <span data-ttu-id="87752-110">in Colonna del documento corrispondente agli intervalli.</span><span class="sxs-lookup"><span data-stu-id="87752-110">[in] The document column corresponding to the ranges.</span></span>  
  
 `cRanges`  
 <span data-ttu-id="87752-111">[in] Dimensione della matrice `ranges`.</span><span class="sxs-lookup"><span data-stu-id="87752-111">[in] The size of the `ranges` array.</span></span>  
  
 `pcRanges`  
 <span data-ttu-id="87752-112">out Puntatore a un oggetto `ULONG32` che riceve la dimensione del buffer necessario per contenere gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="87752-112">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the ranges.</span></span>  
  
 `ranges`  
 <span data-ttu-id="87752-113">out Puntatore al buffer che riceve gli intervalli.</span><span class="sxs-lookup"><span data-stu-id="87752-113">[out] A pointer to the buffer that receives the ranges.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87752-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="87752-114">Return Value</span></span>  
 <span data-ttu-id="87752-115">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="87752-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87752-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87752-116">Requirements</span></span>  
 <span data-ttu-id="87752-117">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="87752-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87752-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87752-118">See also</span></span>

- [<span data-ttu-id="87752-119">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="87752-119">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
