---
title: Interfaccia ISymUnmanagedDocument
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33213aced635549dd439cf679d89367a71baa7c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168805"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="c690d-102">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="c690d-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="c690d-103">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="c690d-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="c690d-104">Un documento è definito da un uniform resource locator (URL) e un GUID del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="c690d-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="c690d-105">È possibile individuare il documento indipendentemente dal modo in cui viene archiviato usando l'URL e GUID del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="c690d-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="c690d-106">È possibile archiviare l'origine del documento nell'archivio simboli e recuperarlo tramite questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c690d-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c690d-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="c690d-107">Methods</span></span>  
  
|<span data-ttu-id="c690d-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="c690d-108">Method</span></span>|<span data-ttu-id="c690d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c690d-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c690d-110">Metodo FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="c690d-110">FindClosestLine Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="c690d-111">Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga in questo documento che possa o non sia un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="c690d-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="c690d-112">Metodo GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="c690d-112">GetCheckSum Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="c690d-113">Ottiene il checksum.</span><span class="sxs-lookup"><span data-stu-id="c690d-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="c690d-114">Metodo GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="c690d-114">GetCheckSumAlgorithmId Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="c690d-115">Ottiene l'identificatore dell'algoritmo di checksum, o restituisce un GUID di tutti gli zeri se non sono presenti checksum.</span><span class="sxs-lookup"><span data-stu-id="c690d-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="c690d-116">Metodo GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="c690d-116">GetDocumentType Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="c690d-117">Ottiene il tipo di documento di questo documento.</span><span class="sxs-lookup"><span data-stu-id="c690d-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="c690d-118">Metodo GetLanguage</span><span class="sxs-lookup"><span data-stu-id="c690d-118">GetLanguage Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="c690d-119">Ottiene l'identificatore di lingua di questo documento.</span><span class="sxs-lookup"><span data-stu-id="c690d-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="c690d-120">Metodo GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="c690d-120">GetLanguageVendor Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="c690d-121">Ottiene il fornitore di linguaggio di questo documento.</span><span class="sxs-lookup"><span data-stu-id="c690d-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="c690d-122">Metodo GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="c690d-122">GetSourceLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="c690d-123">Recupera la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="c690d-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="c690d-124">Metodo GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="c690d-124">GetSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="c690d-125">Restituisce l'intervallo specificato dell'origine incorporata al buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="c690d-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="c690d-126">Metodo GetURL</span><span class="sxs-lookup"><span data-stu-id="c690d-126">GetURL Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|<span data-ttu-id="c690d-127">Restituisce l'URL per questo documento.</span><span class="sxs-lookup"><span data-stu-id="c690d-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="c690d-128">Metodo HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="c690d-128">HasEmbeddedSource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="c690d-129">Restituisce `true` se il documento di origine è incorporata nei simboli di debug; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="c690d-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c690d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c690d-130">See also</span></span>

- [<span data-ttu-id="c690d-131">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="c690d-131">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
