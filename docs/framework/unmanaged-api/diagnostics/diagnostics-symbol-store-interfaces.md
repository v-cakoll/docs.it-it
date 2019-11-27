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
ms.openlocfilehash: bdb691570a9a2bf7bd2bb21af500b06c10b0bc53
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448532"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="9ba4f-102">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9ba4f-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="9ba4f-103">Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da parte di un debugger.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9ba4f-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9ba4f-104">In This Section</span></span>  
 [<span data-ttu-id="9ba4f-105">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="9ba4f-105">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 <span data-ttu-id="9ba4f-106">Fornisce metodi che visualizzano le informazioni di binding correnti sull'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="9ba4f-107">Interfaccia IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="9ba4f-107">IDebugAutoAttach Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 <span data-ttu-id="9ba4f-108">Definisce l'interfaccia per una connessione automatica al debugger richiamata dal server.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="9ba4f-109">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="9ba4f-109">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 <span data-ttu-id="9ba4f-110">Dichiara i metodi per la registrazione e l'annullamento della registrazione di un'origine di notifica della connessione.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="9ba4f-111">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="9ba4f-111">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 <span data-ttu-id="9ba4f-112">Dichiara i metodi per la notifica del sink.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="9ba4f-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="9ba4f-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 <span data-ttu-id="9ba4f-114">Dichiara un metodo per l'impostazione dei filtri di notifica.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="9ba4f-115">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="9ba4f-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="9ba4f-116">Fornisce informazioni per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="9ba4f-117">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="9ba4f-117">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="9ba4f-118">Questa interfaccia è il complemento di lettura per l' [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9ba4f-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="9ba4f-119">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="9ba4f-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="9ba4f-120">Consente la definizione di informazioni facoltative sul metodo asincrono per ogni simbolo di metodo.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="9ba4f-121">Deve usare con un metodo aperto, ovvero tra le chiamate al [Metodo OpenMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)e il [Metodo CloseMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="9ba4f-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="9ba4f-122">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="9ba4f-122">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 <span data-ttu-id="9ba4f-123">Rappresenta uno strumento di associazione di simboli per il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="9ba4f-124">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="9ba4f-124">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="9ba4f-125">Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l'interfaccia `ISymUnmanagedBinder`.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="9ba4f-126">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="9ba4f-126">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="9ba4f-127">Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l'interfaccia `ISymUnmanagedBinder`.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="9ba4f-128">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="9ba4f-128">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 <span data-ttu-id="9ba4f-129">Fornisce l'accesso alle costanti non gestite.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="9ba4f-130">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="9ba4f-130">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 <span data-ttu-id="9ba4f-131">Elimina le risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="9ba4f-132">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="9ba4f-132">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 <span data-ttu-id="9ba4f-133">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="9ba4f-134">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="9ba4f-134">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="9ba4f-135">Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="9ba4f-136">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="9ba4f-136">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="9ba4f-137">Fornisce metodi per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="9ba4f-138">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="9ba4f-138">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 <span data-ttu-id="9ba4f-139">Rappresenta un metodo all'interno dell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="9ba4f-140">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="9ba4f-140">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 <span data-ttu-id="9ba4f-141">Rappresenta uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="9ba4f-142">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="9ba4f-142">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 <span data-ttu-id="9ba4f-143">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="9ba4f-144">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="9ba4f-144">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 <span data-ttu-id="9ba4f-145">Ottiene un metodo del lettore di simboli in base a un token di metodo e a un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="9ba4f-146">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="9ba4f-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="9ba4f-147">Fornisce metodi per ottenere informazioni sulla ricerca di simboli.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="9ba4f-148">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="9ba4f-148">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 <span data-ttu-id="9ba4f-149">Rappresenta un ambito lessicale all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="9ba4f-150">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="9ba4f-150">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 <span data-ttu-id="9ba4f-151">Rappresenta un ambito lessicale in un metodo ed estende l'interfaccia `ISymUnmanagedScope` con metodi che ottengono informazioni sulle costanti definite nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="9ba4f-152">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="9ba4f-152">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="9ba4f-153">Fornisce i dati del server di origine per un modulo.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="9ba4f-154">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="9ba4f-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="9ba4f-155">Fornisce metodi che consentono di ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="9ba4f-156">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="9ba4f-156">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 <span data-ttu-id="9ba4f-157">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="9ba4f-158">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="9ba4f-158">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 <span data-ttu-id="9ba4f-159">Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="9ba4f-160">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="9ba4f-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="9ba4f-161">Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="9ba4f-162">Estende l'interfaccia `ISymUnmanagedWriter`.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="9ba4f-163">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="9ba4f-163">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="9ba4f-164">Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="9ba4f-165">Estende l'interfaccia `ISymUnmanagedWriter`.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="9ba4f-166">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="9ba4f-166">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="9ba4f-167">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="9ba4f-168">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="9ba4f-168">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="9ba4f-169">Interfaccia Metodo ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="9ba4f-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9ba4f-170">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="9ba4f-170">Related Sections</span></span>  
 [<span data-ttu-id="9ba4f-171">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9ba4f-171">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="9ba4f-172">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9ba4f-172">Diagnostics Symbol Store Structures</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="9ba4f-173">Debug</span><span class="sxs-lookup"><span data-stu-id="9ba4f-173">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
