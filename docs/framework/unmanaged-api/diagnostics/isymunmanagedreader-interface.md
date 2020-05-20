---
title: Interfaccia ISymUnmanagedReader
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
ms.openlocfilehash: b372021fcda39d9973d96a9c39e93e38617887a6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615462"
---
# <a name="isymunmanagedreader-interface"></a><span data-ttu-id="3917b-102">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="3917b-102">ISymUnmanagedReader Interface</span></span>
<span data-ttu-id="3917b-103">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="3917b-103">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3917b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3917b-104">Methods</span></span>  
  
|<span data-ttu-id="3917b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3917b-105">Method</span></span>|<span data-ttu-id="3917b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3917b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3917b-107">Metodo GetDocument</span><span class="sxs-lookup"><span data-stu-id="3917b-107">GetDocument Method</span></span>](isymunmanagedreader-getdocument-method.md)|<span data-ttu-id="3917b-108">Trova un documento.</span><span class="sxs-lookup"><span data-stu-id="3917b-108">Finds a document.</span></span>|  
|[<span data-ttu-id="3917b-109">Metodo GetDocuments</span><span class="sxs-lookup"><span data-stu-id="3917b-109">GetDocuments Method</span></span>](isymunmanagedreader-getdocuments-method.md)|<span data-ttu-id="3917b-110">Restituisce una matrice di tutti i documenti definiti nell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="3917b-110">Returns an array of all the documents defined in the symbol store.</span></span>|  
|[<span data-ttu-id="3917b-111">Metodo GetDocumentVersion</span><span class="sxs-lookup"><span data-stu-id="3917b-111">GetDocumentVersion Method</span></span>](isymunmanagedreader-getdocumentversion-method.md)|<span data-ttu-id="3917b-112">Ottiene la versione specificata del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="3917b-112">Gets the specified version of the specified document.</span></span>|  
|[<span data-ttu-id="3917b-113">Metodo GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="3917b-113">GetGlobalVariables Method</span></span>](isymunmanagedreader-getglobalvariables-method.md)|<span data-ttu-id="3917b-114">Restituisce tutte le variabili globali.</span><span class="sxs-lookup"><span data-stu-id="3917b-114">Returns all global variables.</span></span>|  
|[<span data-ttu-id="3917b-115">Metodo GetMethod</span><span class="sxs-lookup"><span data-stu-id="3917b-115">GetMethod Method</span></span>](isymunmanagedreader-getmethod-method.md)|<span data-ttu-id="3917b-116">Ottiene un metodo del lettore di simboli, dato un token di metodo.</span><span class="sxs-lookup"><span data-stu-id="3917b-116">Gets a symbol reader method, given a method token.</span></span>|  
|[<span data-ttu-id="3917b-117">Metodo GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="3917b-117">GetMethodByVersion Method</span></span>](isymunmanagedreader-getmethodbyversion-method.md)|<span data-ttu-id="3917b-118">Ottiene un metodo del lettore di simboli, dato un token del metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="3917b-118">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span>|  
|[<span data-ttu-id="3917b-119">Metodo GetMethodFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="3917b-119">GetMethodFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodfromdocumentposition-method.md)|<span data-ttu-id="3917b-120">Restituisce il metodo che contiene il punto di interruzione in corrispondenza della posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="3917b-120">Returns the method that contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="3917b-121">Metodo GetMethodsFromDocumentPosition</span><span class="sxs-lookup"><span data-stu-id="3917b-121">GetMethodsFromDocumentPosition Method</span></span>](isymunmanagedreader-getmethodsfromdocumentposition-method.md)|<span data-ttu-id="3917b-122">Restituisce una matrice di metodi, ognuno dei quali contiene il punto di interruzione nella posizione specificata in un documento.</span><span class="sxs-lookup"><span data-stu-id="3917b-122">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>|  
|[<span data-ttu-id="3917b-123">Metodo GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="3917b-123">GetMethodVersion Method</span></span>](isymunmanagedreader-getmethodversion-method.md)|<span data-ttu-id="3917b-124">Ottiene la versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="3917b-124">Gets the method version.</span></span>|  
|[<span data-ttu-id="3917b-125">Metodo GetNamespaces</span><span class="sxs-lookup"><span data-stu-id="3917b-125">GetNamespaces Method</span></span>](isymunmanagedreader-getnamespaces-method.md)|<span data-ttu-id="3917b-126">Ottiene gli spazi dei nomi definiti in ambito globale all'interno dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="3917b-126">Gets the namespaces defined at global scope within this symbol store.</span></span>|  
|[<span data-ttu-id="3917b-127">Metodo GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="3917b-127">GetSymAttribute Method</span></span>](isymunmanagedreader-getsymattribute-method.md)|<span data-ttu-id="3917b-128">Ottiene un attributo personalizzato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="3917b-128">Gets a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="3917b-129">Metodo GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="3917b-129">GetSymbolStoreFileName Method</span></span>](isymunmanagedreader-getsymbolstorefilename-method.md)|<span data-ttu-id="3917b-130">Fornisce il nome file su disco dell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="3917b-130">Provides the on-disk file name of the symbol store.</span></span>|  
|[<span data-ttu-id="3917b-131">Metodo GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="3917b-131">GetUserEntryPoint Method</span></span>](isymunmanagedreader-getuserentrypoint-method.md)|<span data-ttu-id="3917b-132">Restituisce il metodo specificato come punto di ingresso utente per il modulo, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="3917b-132">Returns the method that was specified as the user entry point for the module, if any.</span></span>|  
|[<span data-ttu-id="3917b-133">Metodo GetVariables</span><span class="sxs-lookup"><span data-stu-id="3917b-133">GetVariables Method</span></span>](isymunmanagedreader-getvariables-method.md)|<span data-ttu-id="3917b-134">Restituisce una variabile non locale, data l'elemento padre e il nome.</span><span class="sxs-lookup"><span data-stu-id="3917b-134">Return a non-local variable, given its parent and name.</span></span>|  
|[<span data-ttu-id="3917b-135">Metodo Initialize</span><span class="sxs-lookup"><span data-stu-id="3917b-135">Initialize Method</span></span>](isymunmanagedreader-initialize-method.md)|<span data-ttu-id="3917b-136">Inizializza il lettore di simboli con l'interfaccia dell'utilità di importazione dei metadati a cui verrà associato questo Reader, insieme al nome file del modulo.</span><span class="sxs-lookup"><span data-stu-id="3917b-136">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>|  
|[<span data-ttu-id="3917b-137">Metodo ReplaceSymbolStore</span><span class="sxs-lookup"><span data-stu-id="3917b-137">ReplaceSymbolStore Method</span></span>](isymunmanagedreader-replacesymbolstore-method.md)|<span data-ttu-id="3917b-138">Sostituisce l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="3917b-138">Replaces the existing symbol store with a delta symbol store.</span></span>|  
|[<span data-ttu-id="3917b-139">Metodo UpdateSymbolStore</span><span class="sxs-lookup"><span data-stu-id="3917b-139">UpdateSymbolStore Method</span></span>](isymunmanagedreader-updatesymbolstore-method.md)|<span data-ttu-id="3917b-140">Aggiorna l'archivio dei simboli esistente con un archivio dei simboli delta.</span><span class="sxs-lookup"><span data-stu-id="3917b-140">Updates the existing symbol store with a delta symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3917b-141">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3917b-141">Requirements</span></span>  
 <span data-ttu-id="3917b-142">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3917b-142">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3917b-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3917b-143">See also</span></span>

- [<span data-ttu-id="3917b-144">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="3917b-144">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="3917b-145">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="3917b-145">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
