---
title: Metodo ISymUnmanagedReader::GetMethodsFromDocumentPosition
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: bba0fc039c403d45e8a5b60f2b0231eb24226280
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614955"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="93ece-102">Metodo ISymUnmanagedReader::GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="93ece-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>
<span data-ttu-id="93ece-103">Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione nella posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="93ece-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93ece-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93ece-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93ece-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93ece-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="93ece-106">in Documento specificato.</span><span class="sxs-lookup"><span data-stu-id="93ece-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="93ece-107">in Riga del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="93ece-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="93ece-108">in Colonna del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="93ece-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="93ece-109">[in] Dimensione della matrice `pRetVal`.</span><span class="sxs-lookup"><span data-stu-id="93ece-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="93ece-110">out Puntatore a una variabile che riceve il numero di elementi restituiti nella `pRetVal` matrice.</span><span class="sxs-lookup"><span data-stu-id="93ece-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="93ece-111">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) che rappresenta un metodo contenente il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="93ece-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93ece-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="93ece-112">Return Value</span></span>  
 <span data-ttu-id="93ece-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="93ece-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93ece-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93ece-114">Requirements</span></span>  
 <span data-ttu-id="93ece-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="93ece-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93ece-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93ece-116">See also</span></span>

- [<span data-ttu-id="93ece-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="93ece-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
