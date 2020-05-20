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
ms.openlocfilehash: a8ff6d3a925773e58e0713a87b167420c246f85b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615566"
---
# <a name="isymunmanageddocument-interface"></a><span data-ttu-id="a1ebb-102">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="a1ebb-102">ISymUnmanagedDocument Interface</span></span>
<span data-ttu-id="a1ebb-103">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-103">Represents a document referenced by a symbol store.</span></span> <span data-ttu-id="a1ebb-104">Un documento è definito da un URL (Uniform Resource Locator) e da un GUID del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-104">A document is defined by a uniform resource locator (URL) and a document type GUID.</span></span> <span data-ttu-id="a1ebb-105">È possibile individuare il documento indipendentemente dalla relativa modalità di archiviazione utilizzando l'URL e il GUID del tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-105">You can locate the document regardless of how it is stored by using the URL and document type GUID.</span></span> <span data-ttu-id="a1ebb-106">È possibile archiviare l'origine del documento nell'archivio dei simboli e recuperarla tramite questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-106">You can store the document source in the symbol store and retrieve it through this interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1ebb-107">Metodi</span><span class="sxs-lookup"><span data-stu-id="a1ebb-107">Methods</span></span>  
  
|<span data-ttu-id="a1ebb-108">Metodo</span><span class="sxs-lookup"><span data-stu-id="a1ebb-108">Method</span></span>|<span data-ttu-id="a1ebb-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1ebb-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1ebb-110">Metodo FindClosestLine</span><span class="sxs-lookup"><span data-stu-id="a1ebb-110">FindClosestLine Method</span></span>](isymunmanageddocument-findclosestline-method.md)|<span data-ttu-id="a1ebb-111">Restituisce la riga più vicina che rappresenta un punto di sequenza, data una riga del documento che può essere o meno un punto di sequenza.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-111">Returns the closest line that is a sequence point, given a line in this document that may or may not be a sequence point.</span></span>|  
|[<span data-ttu-id="a1ebb-112">Metodo GetCheckSum</span><span class="sxs-lookup"><span data-stu-id="a1ebb-112">GetCheckSum Method</span></span>](isymunmanageddocument-getchecksum-method.md)|<span data-ttu-id="a1ebb-113">Ottiene il checksum.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-113">Gets the checksum.</span></span>|  
|[<span data-ttu-id="a1ebb-114">Metodo GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="a1ebb-114">GetCheckSumAlgorithmId Method</span></span>](isymunmanageddocument-getchecksumalgorithmid-method.md)|<span data-ttu-id="a1ebb-115">Ottiene l'identificatore dell'algoritmo di checksum oppure restituisce un GUID di tutti gli zeri in assenza di checksum.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-115">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>|  
|[<span data-ttu-id="a1ebb-116">Metodo GetDocumentType</span><span class="sxs-lookup"><span data-stu-id="a1ebb-116">GetDocumentType Method</span></span>](isymunmanageddocument-getdocumenttype-method.md)|<span data-ttu-id="a1ebb-117">Ottiene il tipo di documento di questo documento.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-117">Gets the document type of this document.</span></span>|  
|[<span data-ttu-id="a1ebb-118">Metodo GetLanguage</span><span class="sxs-lookup"><span data-stu-id="a1ebb-118">GetLanguage Method</span></span>](isymunmanageddocument-getlanguage-method.md)|<span data-ttu-id="a1ebb-119">Ottiene l'identificatore di lingua di questo documento.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-119">Gets the language identifier of this document.</span></span>|  
|[<span data-ttu-id="a1ebb-120">Metodo GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="a1ebb-120">GetLanguageVendor Method</span></span>](isymunmanageddocument-getlanguagevendor-method.md)|<span data-ttu-id="a1ebb-121">Ottiene il fornitore del linguaggio del documento.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-121">Gets the language vendor of this document.</span></span>|  
|[<span data-ttu-id="a1ebb-122">Metodo GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="a1ebb-122">GetSourceLength Method</span></span>](isymunmanageddocument-getsourcelength-method.md)|<span data-ttu-id="a1ebb-123">Recupera la lunghezza, in byte, dell'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-123">Gets the length, in bytes, of the embedded source.</span></span>|  
|[<span data-ttu-id="a1ebb-124">Metodo GetSourceRange</span><span class="sxs-lookup"><span data-stu-id="a1ebb-124">GetSourceRange Method</span></span>](isymunmanageddocument-getsourcerange-method.md)|<span data-ttu-id="a1ebb-125">Restituisce l'intervallo specificato dell'origine incorporata nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-125">Returns the specified range of the embedded source into the given buffer.</span></span>|  
|[<span data-ttu-id="a1ebb-126">Metodo GetURL</span><span class="sxs-lookup"><span data-stu-id="a1ebb-126">GetURL Method</span></span>](isymunmanageddocument-geturl-method.md)|<span data-ttu-id="a1ebb-127">Restituisce l'URL per questo documento.</span><span class="sxs-lookup"><span data-stu-id="a1ebb-127">Returns the URL for this document.</span></span>|  
|[<span data-ttu-id="a1ebb-128">Metodo HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="a1ebb-128">HasEmbeddedSource Method</span></span>](isymunmanageddocument-hasembeddedsource-method.md)|<span data-ttu-id="a1ebb-129">Restituisce `true` se l'origine del documento è incorporata nei simboli di debug; in caso contrario, restituisce `false` .</span><span class="sxs-lookup"><span data-stu-id="a1ebb-129">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1ebb-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1ebb-130">See also</span></span>

- [<span data-ttu-id="a1ebb-131">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="a1ebb-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
