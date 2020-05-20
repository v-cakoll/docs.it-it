---
title: Metodo ISymUnmanagedReader::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
ms.openlocfilehash: 07d2de5d12fd769cb5cce243d9e721bb6fc185a7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615475"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="3f0bc-102">Metodo ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="3f0bc-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="3f0bc-103">Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati a cui verrà associato questo Reader, insieme al nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f0bc-104">Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di qualsiasi altro metodo Reader.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f0bc-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f0bc-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f0bc-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f0bc-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="3f0bc-107">in Interfaccia dell'utilità di importazione dei metadati a cui verrà associato il lettore.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="3f0bc-108">in Nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-108">[in] The file name of the module.</span></span> <span data-ttu-id="3f0bc-109">In alternativa, è possibile usare il `pIStream` parametro.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="3f0bc-110">in Percorso in cui eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-110">[in] The path to search.</span></span> <span data-ttu-id="3f0bc-111">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="3f0bc-112">in Il flusso di file, usato come alternativa al parametro filename.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f0bc-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f0bc-113">Return Value</span></span>  
 <span data-ttu-id="3f0bc-114">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f0bc-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3f0bc-115">Remarks</span></span>  
 <span data-ttu-id="3f0bc-116">È necessario specificare solo uno dei `filename` `pIStream` parametri o, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="3f0bc-117">`searchPath` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3f0bc-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f0bc-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f0bc-118">Requirements</span></span>  
 <span data-ttu-id="3f0bc-119">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3f0bc-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f0bc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f0bc-120">See also</span></span>

- [<span data-ttu-id="3f0bc-121">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="3f0bc-121">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
