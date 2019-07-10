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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1986ed730c6f0a1ba8a2d8e3c688e6872184da9d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736761"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="cdaf3-102">Metodo ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="cdaf3-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="cdaf3-103">Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che verrà associato, insieme al nome file del modulo di questo lettore.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdaf3-104">Questo metodo può essere chiamato una sola volta e deve essere chiamato prima degli altri metodi di lettura.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdaf3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cdaf3-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdaf3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cdaf3-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="cdaf3-107">[in] L'interfaccia dell'utilità di importazione di metadati con cui verrà associato questo lettore.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="cdaf3-108">[in] Nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-108">[in] The file name of the module.</span></span> <span data-ttu-id="cdaf3-109">È possibile usare il `pIStream` parametro invece.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="cdaf3-110">[in] Il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-110">[in] The path to search.</span></span> <span data-ttu-id="cdaf3-111">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="cdaf3-112">[in] Il flusso di file, usato come alternativa per il parametro filename.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdaf3-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cdaf3-113">Return Value</span></span>  
 <span data-ttu-id="cdaf3-114">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdaf3-115">Note</span><span class="sxs-lookup"><span data-stu-id="cdaf3-115">Remarks</span></span>  
 <span data-ttu-id="cdaf3-116">È necessario specificare solo uno dei `filename` o il `pIStream` parametri, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="cdaf3-117">Il parametro `searchPath` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="cdaf3-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdaf3-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdaf3-118">Requirements</span></span>  
 <span data-ttu-id="cdaf3-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cdaf3-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdaf3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdaf3-120">See also</span></span>

- [<span data-ttu-id="cdaf3-121">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="cdaf3-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
