---
title: Interfaccia ISymUnmanagedDocument
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument
helpviewer_keywords: ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8654f28cc4d82a5ed1419215807ec3360522fd55
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="03d3e-102">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="03d3e-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="03d3e-103">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="03d3e-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="03d3e-104">Un documento viene definito da un uniform resource locator (URL) e un GUID del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="03d3e-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="03d3e-105">È possibile individuare il documento indipendentemente dalla modalità di archiviazione utilizzando l'URL e il GUID di tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="03d3e-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="03d3e-106">È possibile archiviare l'origine del documento nell'archivio di simboli e recuperata mediante questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="03d3e-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03d3e-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="03d3e-107">Methods</span></span>  
  
|<span data-ttu-id="03d3e-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="03d3e-108">Method</span></span>|<span data-ttu-id="03d3e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="03d3e-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03d3e-110">FindClosestLine (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="03d3e-111">Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga in questo documento che non può essere un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="03d3e-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="03d3e-112">GetCheckSum (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="03d3e-113">Ottiene il checksum.</span><span class="sxs-lookup"><span data-stu-id="03d3e-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="03d3e-114">GetCheckSumAlgorithmId (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="03d3e-115">Ottiene l'identificatore dell'algoritmo di checksum o restituisce un GUID di tutti gli zeri, se non sono presenti checksum.</span><span class="sxs-lookup"><span data-stu-id="03d3e-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="03d3e-116">GetDocumentType (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="03d3e-117">Ottiene il tipo di questo documento.</span><span class="sxs-lookup"><span data-stu-id="03d3e-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="03d3e-118">GetLanguage (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="03d3e-119">Ottiene l'identificatore di lingua di questo documento.</span><span class="sxs-lookup"><span data-stu-id="03d3e-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="03d3e-120">GetLanguageVendor (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="03d3e-121">Recupera il fornitore di linguaggio di questo documento.</span><span class="sxs-lookup"><span data-stu-id="03d3e-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="03d3e-122">GetSourceLength (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="03d3e-123">Recupera la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="03d3e-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="03d3e-124">GetSourceRange (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="03d3e-125">Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="03d3e-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="03d3e-126">Metodo GetURL</span><span class="sxs-lookup"><span data-stu-id="03d3e-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="03d3e-127">Restituisce l'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="03d3e-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="03d3e-128">HasEmbeddedSource (metodo)</span><span class="sxs-lookup"><span data-stu-id="03d3e-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="03d3e-129">Restituisce `true` se il documento di origine è incorporata nei simboli di debug; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="03d3e-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03d3e-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03d3e-130">See Also</span></span>  
 [<span data-ttu-id="03d3e-131">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="03d3e-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
