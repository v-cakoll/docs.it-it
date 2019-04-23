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
ms.openlocfilehash: 661c27b9c21f77104b8a86163d3c92d44f8a85df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181779"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="bfa99-102">Metodo ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="bfa99-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="bfa99-103">Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati che verrà associato, insieme al nome file del modulo di questo lettore.</span><span class="sxs-lookup"><span data-stu-id="bfa99-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfa99-104">Questo metodo può essere chiamato una sola volta e deve essere chiamato prima degli altri metodi di lettura.</span><span class="sxs-lookup"><span data-stu-id="bfa99-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa99-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfa99-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfa99-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="bfa99-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="bfa99-107">[in] L'interfaccia dell'utilità di importazione di metadati con cui verrà associato questo lettore.</span><span class="sxs-lookup"><span data-stu-id="bfa99-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="bfa99-108">[in] Nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="bfa99-108">[in] The file name of the module.</span></span> <span data-ttu-id="bfa99-109">È possibile usare il `pIStream` parametro invece.</span><span class="sxs-lookup"><span data-stu-id="bfa99-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="bfa99-110">[in] Il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bfa99-110">[in] The path to search.</span></span> <span data-ttu-id="bfa99-111">Questo parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bfa99-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="bfa99-112">[in] Il flusso di file, usato come alternativa per il parametro filename.</span><span class="sxs-lookup"><span data-stu-id="bfa99-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfa99-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bfa99-113">Return Value</span></span>  
 <span data-ttu-id="bfa99-114">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="bfa99-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfa99-115">Note</span><span class="sxs-lookup"><span data-stu-id="bfa99-115">Remarks</span></span>  
 <span data-ttu-id="bfa99-116">È necessario specificare solo uno dei `filename` o il `pIStream` parametri, non entrambi.</span><span class="sxs-lookup"><span data-stu-id="bfa99-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="bfa99-117">Il parametro `searchPath` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bfa99-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfa99-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfa99-118">Requirements</span></span>  
 <span data-ttu-id="bfa99-119">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bfa99-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa99-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfa99-120">See also</span></span>

- [<span data-ttu-id="bfa99-121">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="bfa99-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
