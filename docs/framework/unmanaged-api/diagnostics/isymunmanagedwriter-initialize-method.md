---
title: Metodo ISymUnmanagedWriter::Initialize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::Initialize
helpviewer_keywords:
- ISymUnmanagedWriter::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: e0ebd793-3764-4df0-8f12-0e95f60b9eae
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bae368919941e6a0b234736f789320b62405a17b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterinitialize-method"></a><span data-ttu-id="4f2cc-102">Metodo ISymUnmanagedWriter::Initialize</span><span class="sxs-lookup"><span data-stu-id="4f2cc-102">ISymUnmanagedWriter::Initialize Method</span></span>
<span data-ttu-id="4f2cc-103">Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer e il nome del file di output in cui verranno scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-103">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>  
  
 <span data-ttu-id="4f2cc-104">Questo metodo può essere chiamato una sola volta e deve essere chiamato prima di altri metodi di scrittura.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-104">This method can be called only once, and it must be called before any other writer methods.</span></span> <span data-ttu-id="4f2cc-105">Per alcuni writer possono richiedere un nome di file.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-105">Some writers may require a file name.</span></span> <span data-ttu-id="4f2cc-106">Tuttavia, è possibile passare sempre un nome di file a questo metodo senza effetti negativi sui writer che non utilizzano il nome del file.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-106">However, you can always pass a file name to this method without any negative effect on writers that do not use the file name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f2cc-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f2cc-107">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *emitter,  
    [in] const WCHAR  *filename,  
    [in] IStream      *pIStream,  
    [in] BOOL         fFullBuild);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f2cc-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f2cc-108">Parameters</span></span>  
 `emitter`  
 <span data-ttu-id="4f2cc-109">[in] Puntatore a interfaccia di emissione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-109">[in] A pointer to the metadata emitter interface.</span></span>  
  
 `filename`  
 <span data-ttu-id="4f2cc-110">[in] Il nome di file in cui vengono scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-110">[in] The file name to which the debugging symbols are written.</span></span> <span data-ttu-id="4f2cc-111">Se specificato per un writer che non usa i nomi file, il parametro sarà ignorato.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-111">If a file name is specified for a writer that does not use file names, this parameter is ignored.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="4f2cc-112">[in] Se specificato, il writer di simboli genererà i simboli nel determinato <xref:System.Runtime.InteropServices.ComTypes.IStream> anziché nel file specificato nella `filename` parametro.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-112">[in] If specified, the symbol writer will emit the symbols into the given <xref:System.Runtime.InteropServices.ComTypes.IStream> rather than to the file specified in the `filename` parameter.</span></span> <span data-ttu-id="4f2cc-113">Il parametro `pIStream` è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-113">The `pIStream` parameter is optional.</span></span>  
  
 `fFullBuild`  
 <span data-ttu-id="4f2cc-114">[in] `true` se si tratta di una ricompilazione completa. `false` se si tratta di una compilazione incrementale.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-114">[in] `true` if this is a full rebuild; `false` if this is an incremental compilation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f2cc-115">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f2cc-115">Return Value</span></span>  
 <span data-ttu-id="4f2cc-116">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4f2cc-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f2cc-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f2cc-117">Requirements</span></span>  
 <span data-ttu-id="4f2cc-118">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f2cc-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2cc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f2cc-119">See Also</span></span>  
 [<span data-ttu-id="4f2cc-120">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4f2cc-120">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="4f2cc-121">Initialize2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="4f2cc-121">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)
