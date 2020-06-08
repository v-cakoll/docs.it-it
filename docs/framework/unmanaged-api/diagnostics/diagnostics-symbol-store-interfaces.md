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
ms.openlocfilehash: 34eee8c05e1c356d4c431245c6837bd2b3a89b32
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504472"
---
# <a name="diagnostics-symbol-store-interfaces"></a><span data-ttu-id="d6064-102">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="d6064-102">Diagnostics Symbol Store Interfaces</span></span>
<span data-ttu-id="d6064-103">Questo argomento descrive le interfacce non gestite che consentono a un compilatore di generare informazioni sui simboli per l'uso da parte di un debugger.</span><span class="sxs-lookup"><span data-stu-id="d6064-103">This topic describes the unmanaged interfaces that enable a compiler to generate symbol information for use by a debugger.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d6064-104">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="d6064-104">In This Section</span></span>  
 [<span data-ttu-id="d6064-105">Interfaccia IBindingDisplay</span><span class="sxs-lookup"><span data-stu-id="d6064-105">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)  
 <span data-ttu-id="d6064-106">Fornisce metodi che visualizzano le informazioni di binding correnti sull'applicazione in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d6064-106">Provides methods that display current binding information about the running application.</span></span>  
  
 [<span data-ttu-id="d6064-107">Interfaccia IDebugAutoAttach</span><span class="sxs-lookup"><span data-stu-id="d6064-107">IDebugAutoAttach Interface</span></span>](idebugautoattach-interface.md)  
 <span data-ttu-id="d6064-108">Definisce l'interfaccia per una connessione automatica al debugger richiamata dal server.</span><span class="sxs-lookup"><span data-stu-id="d6064-108">Defines the interface for a server-invoked debugger auto attach.</span></span>  
  
 [<span data-ttu-id="d6064-109">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="d6064-109">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)  
 <span data-ttu-id="d6064-110">Dichiara i metodi per la registrazione e l'annullamento della registrazione di un'origine di notifica della connessione.</span><span class="sxs-lookup"><span data-stu-id="d6064-110">Declares methods for registering and unregistering a connection notification source.</span></span>  
  
 [<span data-ttu-id="d6064-111">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="d6064-111">INotifySink2 Interface</span></span>](inotifysink2-interface.md)  
 <span data-ttu-id="d6064-112">Dichiara i metodi per la notifica del sink.</span><span class="sxs-lookup"><span data-stu-id="d6064-112">Declares methods for sink notification.</span></span>  
  
 [<span data-ttu-id="d6064-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="d6064-113">INotifySource2 Interface</span></span>](inotifysource2-interface.md)  
 <span data-ttu-id="d6064-114">Dichiara un metodo per l'impostazione dei filtri di notifica.</span><span class="sxs-lookup"><span data-stu-id="d6064-114">Declares a method for setting notification filters.</span></span>  
  
 [<span data-ttu-id="d6064-115">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="d6064-115">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)  
 <span data-ttu-id="d6064-116">Fornisce informazioni per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="d6064-116">Provides information for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="d6064-117">Interfaccia ISymUnmanagedAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="d6064-117">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)  
 <span data-ttu-id="d6064-118">Questa interfaccia è il complemento di lettura per l' [interfaccia ISymUnmanagedAsyncMethodPropertiesWriter](isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d6064-118">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
 [<span data-ttu-id="d6064-119">Interfaccia ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="d6064-119">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)  
 <span data-ttu-id="d6064-120">Consente la definizione di informazioni facoltative sul metodo asincrono per ogni simbolo di metodo.</span><span class="sxs-lookup"><span data-stu-id="d6064-120">Allows definition of optional async method information per method symbol.</span></span> <span data-ttu-id="d6064-121">Deve usare con un metodo aperto, ovvero tra le chiamate al [Metodo OpenMethod](isymunmanagedwriter-openmethod-method.md)e il [Metodo CloseMethod](isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="d6064-121">Must use with an opened method (that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md)and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md)).</span></span>  
  
 [<span data-ttu-id="d6064-122">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="d6064-122">ISymUnmanagedBinder Interface</span></span>](isymunmanagedbinder-interface.md)  
 <span data-ttu-id="d6064-123">Rappresenta uno strumento di associazione di simboli per il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="d6064-123">Represents a symbol binder for unmanaged code.</span></span>  
  
 [<span data-ttu-id="d6064-124">Interfaccia ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="d6064-124">ISymUnmanagedBinder2 Interface</span></span>](isymunmanagedbinder2-interface.md)  
 <span data-ttu-id="d6064-125">Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l' `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d6064-125">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="d6064-126">Interfaccia ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="d6064-126">ISymUnmanagedBinder3 Interface</span></span>](isymunmanagedbinder3-interface.md)  
 <span data-ttu-id="d6064-127">Rappresenta uno strumento di associazione di simboli per il codice non gestito ed estende l' `ISymUnmanagedBinder` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d6064-127">Represents a symbol binder for unmanaged code, and extends the `ISymUnmanagedBinder` interface.</span></span>  
  
 [<span data-ttu-id="d6064-128">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="d6064-128">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)  
 <span data-ttu-id="d6064-129">Fornisce l'accesso alle costanti non gestite.</span><span class="sxs-lookup"><span data-stu-id="d6064-129">Provides access to unmanaged constants.</span></span>  
  
 [<span data-ttu-id="d6064-130">Interfaccia ISymUnmanagedDispose</span><span class="sxs-lookup"><span data-stu-id="d6064-130">ISymUnmanagedDispose Interface</span></span>](isymunmanageddispose-interface.md)  
 <span data-ttu-id="d6064-131">Elimina le risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="d6064-131">Disposes of unmanaged resources.</span></span>  
  
 [<span data-ttu-id="d6064-132">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="d6064-132">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)  
 <span data-ttu-id="d6064-133">Rappresenta un documento al quale fa riferimento un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="d6064-133">Represents a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="d6064-134">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="d6064-134">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)  
 <span data-ttu-id="d6064-135">Fornisce i metodi per la scrittura di un documento cui viene fatto riferimento in un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="d6064-135">Provides methods for writing to a document referenced by a symbol store.</span></span>  
  
 [<span data-ttu-id="d6064-136">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="d6064-136">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)  
 <span data-ttu-id="d6064-137">Fornisce metodi per la funzionalità di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="d6064-137">Provides methods for the Edit and Continue feature.</span></span>  
  
 [<span data-ttu-id="d6064-138">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="d6064-138">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)  
 <span data-ttu-id="d6064-139">Rappresenta un metodo all'interno dell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="d6064-139">Represents a method within the symbol store.</span></span>  
  
 [<span data-ttu-id="d6064-140">Interfaccia ISymUnmanagedNamespace</span><span class="sxs-lookup"><span data-stu-id="d6064-140">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)  
 <span data-ttu-id="d6064-141">Rappresenta uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="d6064-141">Represents a namespace.</span></span>  
  
 [<span data-ttu-id="d6064-142">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="d6064-142">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)  
 <span data-ttu-id="d6064-143">Rappresenta un lettore di simboli che fornisce l'accesso a documenti, metodi e variabili all'interno di un archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="d6064-143">Represents a symbol reader that provides access to documents, methods, and variables within a symbol store.</span></span>  
  
 [<span data-ttu-id="d6064-144">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="d6064-144">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)  
 <span data-ttu-id="d6064-145">Ottiene un metodo del lettore di simboli in base a un token di metodo e a un numero di versione di modifica e copia.</span><span class="sxs-lookup"><span data-stu-id="d6064-145">Gets a symbol reader method given a method token and an edit-and-copy version number.</span></span>  
  
 [<span data-ttu-id="d6064-146">Interfaccia ISymUnmanagedReaderSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="d6064-146">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](isymunmanagedreadersymbolsearchinfo-interface.md)  
 <span data-ttu-id="d6064-147">Fornisce metodi per ottenere informazioni sulla ricerca di simboli.</span><span class="sxs-lookup"><span data-stu-id="d6064-147">Provides methods that get symbol search information.</span></span>  
  
 [<span data-ttu-id="d6064-148">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="d6064-148">ISymUnmanagedScope Interface</span></span>](isymunmanagedscope-interface.md)  
 <span data-ttu-id="d6064-149">Rappresenta un ambito lessicale all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="d6064-149">Represents a lexical scope within a method.</span></span>  
  
 [<span data-ttu-id="d6064-150">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="d6064-150">ISymUnmanagedScope2 Interface</span></span>](isymunmanagedscope2-interface.md)  
 <span data-ttu-id="d6064-151">Rappresenta un ambito lessicale in un metodo ed estende l' `ISymUnmanagedScope` interfaccia con metodi che ottengono informazioni sulle costanti definite nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="d6064-151">Represents a lexical scope within a method, and extends the `ISymUnmanagedScope` interface with methods that get information about constants defined within the scope..</span></span>  
  
 [<span data-ttu-id="d6064-152">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="d6064-152">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)  
 <span data-ttu-id="d6064-153">Fornisce i dati del server di origine per un modulo.</span><span class="sxs-lookup"><span data-stu-id="d6064-153">Provides source server data for a module.</span></span>  
  
 [<span data-ttu-id="d6064-154">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="d6064-154">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)  
 <span data-ttu-id="d6064-155">Fornisce metodi che consentono di ottenere informazioni sul percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="d6064-155">Provides methods that get information about the search path.</span></span>  
  
 [<span data-ttu-id="d6064-156">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="d6064-156">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)  
 <span data-ttu-id="d6064-157">Rappresenta una variabile, ad esempio un parametro, una variabile locale o un campo.</span><span class="sxs-lookup"><span data-stu-id="d6064-157">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
 [<span data-ttu-id="d6064-158">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d6064-158">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)  
 <span data-ttu-id="d6064-159">Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.</span><span class="sxs-lookup"><span data-stu-id="d6064-159">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
 [<span data-ttu-id="d6064-160">Interfaccia ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="d6064-160">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)  
 <span data-ttu-id="d6064-161">Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.</span><span class="sxs-lookup"><span data-stu-id="d6064-161">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="d6064-162">Estende l' `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d6064-162">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="d6064-163">Interfaccia ISymUnmanagedWriter3</span><span class="sxs-lookup"><span data-stu-id="d6064-163">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)  
 <span data-ttu-id="d6064-164">Rappresenta un writer di simboli e fornisce metodi per definire documenti, punti di sequenza, ambiti lessicali e variabili.</span><span class="sxs-lookup"><span data-stu-id="d6064-164">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="d6064-165">Estende l' `ISymUnmanagedWriter` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d6064-165">Extends the `ISymUnmanagedWriter` interface.</span></span>  
  
 [<span data-ttu-id="d6064-166">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="d6064-166">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)  
 <span data-ttu-id="d6064-167">Interfaccia ISymUnmanagedWriter4.</span><span class="sxs-lookup"><span data-stu-id="d6064-167">ISymUnmanagedWriter4 interface.</span></span>  
  
 [<span data-ttu-id="d6064-168">Interfaccia ISymUnmanagedWriter5</span><span class="sxs-lookup"><span data-stu-id="d6064-168">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)  
 <span data-ttu-id="d6064-169">Interfaccia Metodo ISymUnmanagedWriter5.</span><span class="sxs-lookup"><span data-stu-id="d6064-169">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d6064-170">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="d6064-170">Related Sections</span></span>  
 [<span data-ttu-id="d6064-171">Enumerazioni dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="d6064-171">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)  
  
 [<span data-ttu-id="d6064-172">Strutture dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="d6064-172">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)  
  
 [<span data-ttu-id="d6064-173">Debug</span><span class="sxs-lookup"><span data-stu-id="d6064-173">Debugging</span></span>](../debugging/index.md)
