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
ms.workload: dotnet
ms.openlocfilehash: 9a9550bf1e3e5500356584b1bdd53f5d3061e190
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="bc34f-102">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="bc34f-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="bc34f-103">Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da un debugger.</span><span class="sxs-lookup"><span data-stu-id="bc34f-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bc34f-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="bc34f-104">In This Section</span></span>  
 [<span data-ttu-id="bc34f-105">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="bc34f-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="bc34f-106">Fornisce metodi che consentono di visualizzare informazioni correnti di associazione dell'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bc34f-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="bc34f-107">Interfaccia IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="bc34f-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="bc34f-108">Definisce l'interfaccia per la connessione automatico di un debugger richiamato al server.</span><span class="sxs-lookup"><span data-stu-id="bc34f-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="bc34f-109">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="bc34f-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="bc34f-110">Dichiara i metodi per la registrazione e annullamento della registrazione di un'origine di notifica di connessione.</span><span class="sxs-lookup"><span data-stu-id="bc34f-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="bc34f-111">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="bc34f-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="bc34f-112">Dichiara i metodi per la notifica di sink.</span><span class="sxs-lookup"><span data-stu-id="bc34f-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="bc34f-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="bc34f-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="bc34f-114">Dichiara un metodo per impostare i filtri di notifica.</span><span class="sxs-lookup"><span data-stu-id="bc34f-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="bc34f-115">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="bc34f-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="bc34f-116">Vengono fornite informazioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="bc34f-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="bc34f-117">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="bc34f-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="bc34f-118">Questa interfaccia rappresenta il complemento di lettura per [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="bc34f-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="bc34f-119">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="bc34f-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="bc34f-120">Consente la definizione delle informazioni sul metodo async facoltativo per ogni simbolo del metodo.</span><span class="sxs-lookup"><span data-stu-id="bc34f-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="bc34f-121">Deve utilizzare con un metodo di aperto (vale a dire, tra le chiamate al [OpenMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)e [CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="bc34f-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="bc34f-122">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="bc34f-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="bc34f-123">Rappresenta un raccoglitore di simboli per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="bc34f-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="bc34f-124">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="bc34f-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="bc34f-125">Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bc34f-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="bc34f-126">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="bc34f-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="bc34f-127">Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bc34f-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="bc34f-128">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="bc34f-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="bc34f-129">Fornisce l'accesso alle costanti non gestite.</span><span class="sxs-lookup"><span data-stu-id="bc34f-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="bc34f-130">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="bc34f-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="bc34f-131">Elimina le risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="bc34f-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="bc34f-132">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="bc34f-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="bc34f-133">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="bc34f-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="bc34f-134">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="bc34f-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="bc34f-135">Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="bc34f-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="bc34f-136">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="bc34f-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="bc34f-137">Fornisce metodi per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="bc34f-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="bc34f-138">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="bc34f-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="bc34f-139">Rappresenta un metodo all'interno dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="bc34f-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="bc34f-140">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="bc34f-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="bc34f-141">Rappresenta uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="bc34f-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="bc34f-142">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="bc34f-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="bc34f-143">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="bc34f-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="bc34f-144">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="bc34f-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="bc34f-145">Ottiene un metodo del lettore di simboli specificato un token di metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="bc34f-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="bc34f-146">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="bc34f-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="bc34f-147">Fornisce metodi per ottenere informazioni sui simboli di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bc34f-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="bc34f-148">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="bc34f-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="bc34f-149">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="bc34f-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="bc34f-150">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="bc34f-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="bc34f-151">Rappresenta un ambito lessicale in un metodo ed estende il `ISymUnmanagedScope` interfaccia con metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito...</span><span class="sxs-lookup"><span data-stu-id="bc34f-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="bc34f-152">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="bc34f-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="bc34f-153">Fornisce i dati di server di origine per un modulo.</span><span class="sxs-lookup"><span data-stu-id="bc34f-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="bc34f-154">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="bc34f-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="bc34f-155">Fornisce metodi per ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="bc34f-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="bc34f-156">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="bc34f-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="bc34f-157">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="bc34f-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="bc34f-158">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="bc34f-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="bc34f-159">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="bc34f-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="bc34f-160">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="bc34f-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="bc34f-161">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="bc34f-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="bc34f-162">Estende il `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bc34f-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="bc34f-163">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="bc34f-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="bc34f-164">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="bc34f-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="bc34f-165">Estende il `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="bc34f-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="bc34f-166">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="bc34f-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="bc34f-167">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="bc34f-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="bc34f-168">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="bc34f-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="bc34f-169">Interfaccia ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="bc34f-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bc34f-170">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="bc34f-170">Related Sections</span></span>  
 [<span data-ttu-id="bc34f-171">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="bc34f-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="bc34f-172">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="bc34f-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="bc34f-173">Debug</span><span class="sxs-lookup"><span data-stu-id="bc34f-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
