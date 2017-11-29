---
title: Interfacce dell'archivio dei simboli di diagnostica
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 50ef54c90609bf8ef1e3a943664daef95f50d926
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="8b452-102">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="8b452-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="8b452-103">Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da un debugger.</span><span class="sxs-lookup"><span data-stu-id="8b452-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8b452-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8b452-104">In This Section</span></span>  
 [<span data-ttu-id="8b452-105">IBindingDisplay (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="8b452-106">Fornisce metodi che consentono di visualizzare informazioni correnti di associazione dell'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8b452-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="8b452-107">IDebugAutoAttach (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="8b452-108">Definisce l'interfaccia per la connessione automatico di un debugger richiamato al server.</span><span class="sxs-lookup"><span data-stu-id="8b452-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="8b452-109">INotifyConnection2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="8b452-110">Dichiara i metodi per la registrazione e annullamento della registrazione di un'origine di notifica di connessione.</span><span class="sxs-lookup"><span data-stu-id="8b452-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="8b452-111">INotifySink2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="8b452-112">Dichiara i metodi per la notifica di sink.</span><span class="sxs-lookup"><span data-stu-id="8b452-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="8b452-113">INotifySource2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="8b452-114">Dichiara un metodo per impostare i filtri di notifica.</span><span class="sxs-lookup"><span data-stu-id="8b452-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="8b452-115">ISymENCUnmanagedMethod (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="8b452-116">Vengono fornite informazioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="8b452-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="8b452-117">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="8b452-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="8b452-118">Questa interfaccia rappresenta il complemento di lettura per [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8b452-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="8b452-119">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="8b452-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="8b452-120">Consente la definizione delle informazioni sul metodo async facoltativo per ogni simbolo del metodo.</span><span class="sxs-lookup"><span data-stu-id="8b452-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="8b452-121">Deve utilizzare con un metodo di aperto (vale a dire, tra le chiamate al [OpenMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)e [CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="8b452-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="8b452-122">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="8b452-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="8b452-123">Rappresenta un raccoglitore di simboli per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="8b452-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="8b452-124">ISymUnmanagedBinder2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="8b452-125">Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8b452-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="8b452-126">ISymUnmanagedBinder3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="8b452-127">Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8b452-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="8b452-128">ISymUnmanagedConstant (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="8b452-129">Fornisce l'accesso alle costanti non gestite.</span><span class="sxs-lookup"><span data-stu-id="8b452-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="8b452-130">ISymUnmanagedDispose (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="8b452-131">Elimina le risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="8b452-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="8b452-132">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="8b452-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="8b452-133">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="8b452-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="8b452-134">ISymUnmanagedDocumentWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="8b452-135">Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="8b452-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="8b452-136">ISymUnmanagedENCUpdate (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="8b452-137">Fornisce metodi per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="8b452-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="8b452-138">ISymUnmanagedMethod (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="8b452-139">Rappresenta un metodo all'interno dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="8b452-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="8b452-140">ISymUnmanagedNamespace (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="8b452-141">Rappresenta uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="8b452-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="8b452-142">ISymUnmanagedReader (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="8b452-143">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="8b452-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="8b452-144">ISymUnmanagedReader2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="8b452-145">Ottiene un metodo del lettore di simboli specificato un token di metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="8b452-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="8b452-146">ISymUnmanagedReaderSymbolSearchInfo (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="8b452-147">Fornisce metodi per ottenere informazioni sui simboli di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8b452-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="8b452-148">ISymUnmanagedScope (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="8b452-149">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="8b452-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="8b452-150">ISymUnmanagedScope2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="8b452-151">Rappresenta un ambito lessicale in un metodo ed estende il `ISymUnmanagedScope` interfaccia con metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito...</span><span class="sxs-lookup"><span data-stu-id="8b452-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="8b452-152">ISymUnmanagedSourceServerModule (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="8b452-153">Fornisce i dati di server di origine per un modulo.</span><span class="sxs-lookup"><span data-stu-id="8b452-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="8b452-154">ISymUnmanagedSymbolSearchInfo (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="8b452-155">Fornisce metodi per ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8b452-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="8b452-156">ISymUnmanagedVariable (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="8b452-157">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="8b452-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="8b452-158">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="8b452-159">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="8b452-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="8b452-160">ISymUnmanagedWriter2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="8b452-161">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="8b452-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="8b452-162">Estende il `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8b452-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="8b452-163">ISymUnmanagedWriter3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b452-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="8b452-164">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="8b452-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="8b452-165">Estende il `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8b452-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="8b452-166">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="8b452-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="8b452-167">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="8b452-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="8b452-168">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="8b452-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="8b452-169">Interfaccia ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="8b452-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8b452-170">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8b452-170">Related Sections</span></span>  
 [<span data-ttu-id="8b452-171">Enumerazioni dell'archivio di simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="8b452-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="8b452-172">Strutture di archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="8b452-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="8b452-173">Debug</span><span class="sxs-lookup"><span data-stu-id="8b452-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
