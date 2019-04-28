---
title: Interfacce dell'archivio dei simboli di diagnostica
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fca7359888b8b73b2e1cf709ab708d71abf0db6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787894"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="ff15a-102">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ff15a-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="ff15a-103">Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da un debugger.</span><span class="sxs-lookup"><span data-stu-id="ff15a-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff15a-104">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ff15a-104">In This Section</span></span>  
 [<span data-ttu-id="ff15a-105">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="ff15a-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="ff15a-106">Fornisce metodi che consentono di visualizzare informazioni correnti di associazione dell'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ff15a-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="ff15a-107">Interfaccia IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="ff15a-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="ff15a-108">Definisce l'interfaccia per la connessione automatico di un debugger viene richiamato server.</span><span class="sxs-lookup"><span data-stu-id="ff15a-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="ff15a-109">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="ff15a-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="ff15a-110">Dichiara i metodi per la registrazione e annullamento della registrazione di un'origine di notifica di connessione.</span><span class="sxs-lookup"><span data-stu-id="ff15a-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="ff15a-111">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="ff15a-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="ff15a-112">Dichiara i metodi per la notifica ai sink.</span><span class="sxs-lookup"><span data-stu-id="ff15a-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="ff15a-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="ff15a-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="ff15a-114">Dichiara un metodo per impostare i filtri di notifica.</span><span class="sxs-lookup"><span data-stu-id="ff15a-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="ff15a-115">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="ff15a-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="ff15a-116">Vengono fornite informazioni per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="ff15a-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="ff15a-117">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="ff15a-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="ff15a-118">Questa interfaccia è il complemento di lettura per il [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ff15a-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="ff15a-119">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="ff15a-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="ff15a-120">Consente la definizione delle informazioni sul metodo async facoltativo per ogni simbolo del metodo.</span><span class="sxs-lookup"><span data-stu-id="ff15a-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="ff15a-121">Deve utilizzare con un metodo aperto (vale a dire, tra le chiamate al [OpenMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)e il [CloseMethod (metodo)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span><span class="sxs-lookup"><span data-stu-id="ff15a-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="ff15a-122">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="ff15a-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="ff15a-123">Rappresenta un raccoglitore di simboli per codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="ff15a-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="ff15a-124">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="ff15a-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="ff15a-125">Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ff15a-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="ff15a-126">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="ff15a-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="ff15a-127">Rappresenta un raccoglitore di simboli per codice non gestito ed estende il `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ff15a-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="ff15a-128">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="ff15a-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="ff15a-129">Fornisce l'accesso alle costanti non gestite.</span><span class="sxs-lookup"><span data-stu-id="ff15a-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="ff15a-130">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="ff15a-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="ff15a-131">Elimina le risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="ff15a-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="ff15a-132">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="ff15a-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="ff15a-133">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="ff15a-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="ff15a-134">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="ff15a-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="ff15a-135">Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="ff15a-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="ff15a-136">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="ff15a-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="ff15a-137">Fornisce metodi per la funzionalità Modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="ff15a-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="ff15a-138">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="ff15a-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="ff15a-139">Rappresenta un metodo all'interno dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="ff15a-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="ff15a-140">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="ff15a-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="ff15a-141">Rappresenta uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ff15a-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="ff15a-142">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="ff15a-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="ff15a-143">Rappresenta un lettore di simboli che fornisce accesso ai documenti, metodi e le variabili all'interno di un archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="ff15a-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="ff15a-144">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="ff15a-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="ff15a-145">Ottiene un metodo del lettore di simboli dato un token di metodo e un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="ff15a-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="ff15a-146">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ff15a-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="ff15a-147">Fornisce metodi per ottenere informazioni sui simboli di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff15a-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="ff15a-148">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="ff15a-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="ff15a-149">Rappresenta un ambito lessicale in un metodo.</span><span class="sxs-lookup"><span data-stu-id="ff15a-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="ff15a-150">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="ff15a-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="ff15a-151">Rappresenta un ambito lessicale in un metodo ed estende il `ISymUnmanagedScope` interfacciarsi con i metodi che ottengono informazioni sulle costanti definite all'interno dell'ambito...</span><span class="sxs-lookup"><span data-stu-id="ff15a-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="ff15a-152">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="ff15a-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="ff15a-153">Fornisce i dati di server di origine per un modulo.</span><span class="sxs-lookup"><span data-stu-id="ff15a-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="ff15a-154">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ff15a-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="ff15a-155">Fornisce metodi che ottengono informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ff15a-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="ff15a-156">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="ff15a-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="ff15a-157">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="ff15a-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="ff15a-158">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ff15a-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="ff15a-159">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="ff15a-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="ff15a-160">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="ff15a-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="ff15a-161">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="ff15a-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="ff15a-162">Estende il `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ff15a-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="ff15a-163">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="ff15a-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="ff15a-164">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="ff15a-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="ff15a-165">Estende il `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="ff15a-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="ff15a-166">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="ff15a-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="ff15a-167">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="ff15a-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="ff15a-168">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="ff15a-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="ff15a-169">Interfaccia ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="ff15a-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ff15a-170">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ff15a-170">Related Sections</span></span>  
 [<span data-ttu-id="ff15a-171">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ff15a-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="ff15a-172">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="ff15a-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="ff15a-173">Debug</span><span class="sxs-lookup"><span data-stu-id="ff15a-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
