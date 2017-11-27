---
title: Metodo ISymUnmanagedReader::Initialize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5917fbe3cebe9b1e9ab91d113aee2461f414c14d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="94ed9-102">Metodo ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="94ed9-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="94ed9-103">Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che il lettore verrà associato, insieme al nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="94ed9-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="94ed9-104">Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di altri metodi di lettura.</span><span class="sxs-lookup"><span data-stu-id="94ed9-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94ed9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94ed9-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94ed9-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="94ed9-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="94ed9-107">[in] L'interfaccia dell'utilità di importazione dei metadati al quale verrà associato questo reader.</span><span class="sxs-lookup"><span data-stu-id="94ed9-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="94ed9-108">[in] Il nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="94ed9-108">[in] The file name of the module.</span></span> <span data-ttu-id="94ed9-109">È possibile utilizzare il `pIStream` parametro invece.</span><span class="sxs-lookup"><span data-stu-id="94ed9-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="94ed9-110">[in] Il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="94ed9-110">[in] The path to search.</span></span> <span data-ttu-id="94ed9-111">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="94ed9-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="94ed9-112">[in] Flusso di file, utilizzato come alternativa al parametro filename.</span><span class="sxs-lookup"><span data-stu-id="94ed9-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94ed9-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="94ed9-113">Return Value</span></span>  
 <span data-ttu-id="94ed9-114">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="94ed9-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94ed9-115">Note</span><span class="sxs-lookup"><span data-stu-id="94ed9-115">Remarks</span></span>  
 <span data-ttu-id="94ed9-116">È necessario specificare uno solo del `filename` o `pIStream` parametri, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="94ed9-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="94ed9-117">Il parametro `searchPath` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="94ed9-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94ed9-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94ed9-118">Requirements</span></span>  
 <span data-ttu-id="94ed9-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="94ed9-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ed9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94ed9-120">See Also</span></span>  
 [<span data-ttu-id="94ed9-121">ISymUnmanagedReader (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="94ed9-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
