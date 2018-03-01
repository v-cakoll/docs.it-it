---
title: Interfaccia ISymUnmanagedDocument
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2e176679b4fdb4d0a2c5c4fbcbc09403e45f1ad1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="b6859-102">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="b6859-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="b6859-103">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="b6859-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="b6859-104">Un documento viene definito da un uniform resource locator (URL) e un GUID del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="b6859-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="b6859-105">È possibile individuare il documento indipendentemente dalla modalità di archiviazione utilizzando l'URL e il GUID di tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="b6859-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="b6859-106">È possibile archiviare l'origine del documento nell'archivio di simboli e recuperata mediante questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="b6859-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6859-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="b6859-107">Methods</span></span>  
  
|<span data-ttu-id="b6859-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="b6859-108">Method</span></span>|<span data-ttu-id="b6859-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6859-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6859-110">Metodo FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="b6859-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="b6859-111">Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga in questo documento che non può essere un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="b6859-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="b6859-112">Metodo GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="b6859-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="b6859-113">Ottiene il checksum.</span><span class="sxs-lookup"><span data-stu-id="b6859-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="b6859-114">Metodo GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="b6859-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="b6859-115">Ottiene l'identificatore dell'algoritmo di checksum o restituisce un GUID di tutti gli zeri, se non sono presenti checksum.</span><span class="sxs-lookup"><span data-stu-id="b6859-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="b6859-116">Metodo GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="b6859-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="b6859-117">Ottiene il tipo di questo documento.</span><span class="sxs-lookup"><span data-stu-id="b6859-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="b6859-118">Metodo GetLanguage</span><span class="sxs-lookup"><span data-stu-id="b6859-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="b6859-119">Ottiene l'identificatore di lingua di questo documento.</span><span class="sxs-lookup"><span data-stu-id="b6859-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="b6859-120">Metodo GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="b6859-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="b6859-121">Recupera il fornitore di linguaggio di questo documento.</span><span class="sxs-lookup"><span data-stu-id="b6859-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="b6859-122">Metodo GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="b6859-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="b6859-123">Recupera la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="b6859-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="b6859-124">Metodo GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="b6859-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="b6859-125">Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="b6859-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="b6859-126">Metodo GetURL</span><span class="sxs-lookup"><span data-stu-id="b6859-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="b6859-127">Restituisce l'URL per il documento.</span><span class="sxs-lookup"><span data-stu-id="b6859-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="b6859-128">Metodo HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="b6859-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="b6859-129">Restituisce `true` se il documento di origine è incorporata nei simboli di debug; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="b6859-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6859-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6859-130">See Also</span></span>  
 [<span data-ttu-id="b6859-131">Interfacce dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="b6859-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
