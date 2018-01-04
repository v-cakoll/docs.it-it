---
title: Elaborazione di ordini con criteri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d86c7890af651ba9f0ee0ec2a1763f9c579bac89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="order-processing-with-policy"></a><span data-ttu-id="20291-102">Elaborazione di ordini con criteri</span><span class="sxs-lookup"><span data-stu-id="20291-102">Order Processing with Policy</span></span>
<span data-ttu-id="20291-103">Nell’esempio dei Criteri di elaborazione degli ordini vengono illustrate alcune delle funzionalità principali introdotte nel [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] di Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="20291-103">The Order Processing Policy sample demonstrates some of the key features introduced in the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] of the Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="20291-104">Di seguito viene esposta una nuova funzionalità per il motore di regole WF:</span><span class="sxs-lookup"><span data-stu-id="20291-104">The following functionality is new for the WF rules engine:</span></span>  
  
-   <span data-ttu-id="20291-105">supporto per l’overload degli operatori.</span><span class="sxs-lookup"><span data-stu-id="20291-105">Support for operator overloading.</span></span>  
  
-   <span data-ttu-id="20291-106">Il supporto per l'operatore `new` consente agli utenti di creare nuovi oggetti e matrici dalle regole WF.</span><span class="sxs-lookup"><span data-stu-id="20291-106">Support for the `new` operator, allowing users to create new objects and arrays from WF rules.</span></span>  
  
-   <span data-ttu-id="20291-107">Supporto per i metodi di estensione per migliorare l’esperienza utente nel chiamare metodi di estensione dalle regole WF compatibili con gli stili di codifica C#.</span><span class="sxs-lookup"><span data-stu-id="20291-107">Support for extension methods to make the user experience in calling extension methods from WF rules compatible with C# coding styles.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20291-108">Questo esempio richiede che [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] sia installato e pronto per la compilazione e l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="20291-108">This sample requires that [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] is installed to build and run.</span></span> <span data-ttu-id="20291-109">Per aprire i file del progetto e della soluzione è richiesto [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20291-109">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] is required to open the project and solution files.</span></span>  
  
 <span data-ttu-id="20291-110">Nell’esempio viene illustrato un progetto `OrderProcessingPolicy` nel quale viene immesso un ordine del cliente, costituito da un elenco numerato di elementi disponibili e un codice postale.</span><span class="sxs-lookup"><span data-stu-id="20291-110">The sample demonstrates an `OrderProcessingPolicy` project in which a customer order, which consists of a numbered list of available items and a zip code, is entered.</span></span> <span data-ttu-id="20291-111">L'ordine viene elaborato correttamente se entrambi le voci sono corrette; in caso contrario, i criteri creano oggetti di errore, usando un operatore `+` di overload e un metodo di estensione predefinito per informare l'utente degli errori.</span><span class="sxs-lookup"><span data-stu-id="20291-111">The order is processed successfully if both entries are correct; otherwise, the policy creates error objects, utilizing an overloaded `+` operator and a predefined extension method to inform the user of the errors.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="20291-112">metodi di estensione, vedere [C# versione 3.0 Specification](http://go.microsoft.com/fwlink/?LinkId=95402).</span><span class="sxs-lookup"><span data-stu-id="20291-112"> extension methods, see [C# Version 3.0 Specification](http://go.microsoft.com/fwlink/?LinkId=95402).</span></span>  
  
 <span data-ttu-id="20291-113">L’esempio comprende i progetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="20291-113">The sample is comprised of the following projects:</span></span>  
  
-   `OrderErrorLibrary`  
  
     <span data-ttu-id="20291-114">`OrderErrorLibrary` è una libreria di classi che definisce le classi `OrderError` e `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-114">The `OrderErrorLibrary` is a class library that defines `OrderError` and `OrderErrorCollection` classes.</span></span> <span data-ttu-id="20291-115">Un'istanza `OrderError` viene creata quando viene immesso un input non valido.</span><span class="sxs-lookup"><span data-stu-id="20291-115">An `OrderError` instance is created when an invalid input is entered.</span></span> <span data-ttu-id="20291-116">La libreria fornisce anche un metodo di estensione sulla classe `OrderErrorCollection` che restituisce la proprietà `ErrorText` su tutti gli oggetti `OrderError` in `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-116">The library also provides an extension method on the `OrderErrorCollection` class that outputs the `ErrorText` property on all `OrderError` objects in the `OrderErrorCollection`.</span></span>  
  
-   `OrderProcessingPolicy`  
  
     <span data-ttu-id="20291-117">Il progetto `OrderProcessingPolicy` è un'applicazione console di WF che definisce una sola attività `PolicyFromFile`.</span><span class="sxs-lookup"><span data-stu-id="20291-117">The `OrderProcessingPolicy` project is a WF console application that defines a single `PolicyFromFile` activity.</span></span> <span data-ttu-id="20291-118">L'attività dispone delle regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="20291-118">The activity has the following rules:</span></span>  
  
    -   `invalidItemNum`  
  
         <span data-ttu-id="20291-119">Questa regola convalida che il numero dell'elemento è compreso tra 1 e 6, incluso.</span><span class="sxs-lookup"><span data-stu-id="20291-119">This rule validates that the item number is between 1 and 6, inclusive.</span></span> <span data-ttu-id="20291-120">Se il numero dell'elemento rientra nell'intervallo valido, la regola non esegue alcuna operazione (ad eccezione della stampa alla console).</span><span class="sxs-lookup"><span data-stu-id="20291-120">If the item number is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="20291-121">Se il numero dell'elemento non rientra tra 1 e 6, la regola `invalidItemNum` esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20291-121">If the item number is not between 1 and 6, the `invalidItemNum` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="20291-122">Crea un oggetto `OrderError` nuovo, passando a quest’ultimo il numero dell'elemento immesso, e imposta le proprietà `ErrorText` e `CustomerName` sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="20291-122">Creates a new `OrderError` object, passing it the item number entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="20291-123">Crea un oggetto `invalidItemNumErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-123">Creates an `invalidItemNumErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="20291-124">Aggiunge l’istanza `OrderError` di recente creazione a `invalidItemNumErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-124">Adds the newly-created `OrderError` instance to the `invalidItemNumErrorCollection`.</span></span>  
  
         <span data-ttu-id="20291-125">In questo modo viene illustrato il supporto per l'operatore `new` con il quale è possibile creare un'istanza di oggetti nelle regole.</span><span class="sxs-lookup"><span data-stu-id="20291-125">This demonstrates support for the `new` operator, with which you can instantiate objects inside rules.</span></span>  
  
    -   `invalidZip`  
  
         <span data-ttu-id="20291-126">Questa regola convalida che il CAP dispone di 5 cifre ed è compreso nell'intervallo da 600 a 99998.</span><span class="sxs-lookup"><span data-stu-id="20291-126">This rule validates that the zip code has 5 digits, and is within the range 600 to 99998.</span></span> <span data-ttu-id="20291-127">Se il numero del CAP rientra nell'intervallo valido, la regola non esegue alcuna operazione (ad eccezione della stampa nella console).</span><span class="sxs-lookup"><span data-stu-id="20291-127">If the zip code is within the valid range, the rule does nothing (other than printing to the console).</span></span> <span data-ttu-id="20291-128">Se il codice postale è costituito da meno di 5 cifre o non rientra nell'intervallo compreso tra 00600 and 99998, la regola `invalidZip` esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20291-128">If the length of the zip code is less than 5, or the zip code is not between 00600 and 99998, the `invalidZip` rule does the following:</span></span>  
  
        1.  <span data-ttu-id="20291-129">Crea un oggetto `OrderError`, passando a quest’ultimo il codice postale immesso, e imposta le proprietà `ErrorText` e `CustomerName` sull'oggetto.</span><span class="sxs-lookup"><span data-stu-id="20291-129">Creates an `OrderError` object, passing it the zip code entered, and sets the `ErrorText` and `CustomerName` properties on the object.</span></span>  
  
        2.  <span data-ttu-id="20291-130">Crea un oggetto `invalidZipCodeErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-130">Creates an `invalidZipCodeErrorCollection` object.</span></span>  
  
        3.  <span data-ttu-id="20291-131">Aggiunge l’istanza `OrderError` di recente creazione a `invalidZipCodeErrorCollection` di recente creazione.</span><span class="sxs-lookup"><span data-stu-id="20291-131">Adds the newly-created `OrderError` instance to the newly-created `invalidZipCodeErrorCollection`.</span></span>  
  
         <span data-ttu-id="20291-132">In questa regola viene nuovamente illustrato il supporto per l'operatore `new` che consente di creare un'istanza di oggetti nelle regole.</span><span class="sxs-lookup"><span data-stu-id="20291-132">This rule again demonstrates support for the `new` operator, which allows you to instantiate objects inside rules.</span></span>  
  
    -   `displayErrors`  
  
         <span data-ttu-id="20291-133">Questa regola consente di controllare la presenza di eventuali errori aggiunti dalle due regole precedenti nei due oggetti `OrderErrorCollection``invalidItemNumErrorCollection` e `invalidIZipCodeErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-133">This rule checks to see if there were any errors added by the previous two rules in the two `OrderErrorCollection` objects `invalidItemNumErrorCollection` and `invalidIZipCodeErrorCollection`.</span></span> <span data-ttu-id="20291-134">Se sono stati rilevati errori ( `invalidItemNumErrorCollection` o `invalidZipCodeErrorCollection` non è `null`), la regola esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="20291-134">If there were errors (either `invalidItemNumErrorCollection` or `invalidZipCodeErrorCollection` is not `null`), the rule does the following:</span></span>  
  
        1.  <span data-ttu-id="20291-135">Chiama il metodo di overload `+` operatore per copiare il contenuto di `invalidItemNumErrorCollection` e `invalidZipCodeErrorCollection` per un `invalidOrdersCollection``OrderErrorCollection` istanza.</span><span class="sxs-lookup"><span data-stu-id="20291-135">Calls the overloaded `+` operator to copy the contents of `invalidItemNumErrorCollection` and `invalidZipCodeErrorCollection` to an `invalidOrdersCollection``OrderErrorCollection` instance.</span></span>  
  
        2.  <span data-ttu-id="20291-136">Chiama il metodo di estensione `PrintOrderErrors` su `invalidOrdersCollection` e restituisce la proprietà `ErrorText` su ogni `orderError` oggetto in `invalidOrdersCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-136">Calls the `PrintOrderErrors` extension method on `invalidOrdersCollection` and outputs the `ErrorText` property on all `orderError` objects in `invalidOrdersCollection`.</span></span>  
  
 <span data-ttu-id="20291-137">L'operatore `+` di overload su `OrderErrorCollection` è definito nella classe `OrderErrorCollection`, nel progetto `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="20291-137">The overloaded operator `+` on the `OrderErrorCollection` is defined in the `OrderErrorCollection` class, in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="20291-138">Prende due oggetti `OrderErrorCollection` e li combina in un oggetto `OrderErrorCollection`.</span><span class="sxs-lookup"><span data-stu-id="20291-138">It takes two `OrderErrorCollection` objects and combines them into one `OrderErrorCollection` object.</span></span>  
  
 <span data-ttu-id="20291-139">Il metodo di estensione `PrintOrderErrors` è definito anche nel progetto `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="20291-139">The `PrintOrderErrors` extension method is also defined in the `OrderErrorLibrary` project.</span></span> <span data-ttu-id="20291-140">I metodi di estensione rappresentano una nuova funzionalità C# che consente agli sviluppatori di aggiungere nuovi metodi al contratto pubblico di un tipo CLR esistente, senza che sia necessario derivarne una classe o ricompilare il tipo originale.</span><span class="sxs-lookup"><span data-stu-id="20291-140">Extension methods are a new C# feature that enables developers to add new methods to the public contract of an existing CLR type, without having to derive a class from it or recompile the original type.</span></span>  
  
 <span data-ttu-id="20291-141">Quando si esegue l'esempio viene richiesto di immettere un nome, il numero dell'elemento da acquistare e un codice postale.</span><span class="sxs-lookup"><span data-stu-id="20291-141">When you run the sample you are prompted to enter a name, the item number of the item to be purchased, and a zip code.</span></span> <span data-ttu-id="20291-142">Queste informazioni vengono quindi verificate dalle regole definite nell'attività dei criteri.</span><span class="sxs-lookup"><span data-stu-id="20291-142">This information is then verified by the rules defined in the policy activity.</span></span> <span data-ttu-id="20291-143">Di seguito è riportato un esempio di output generato dal programma.</span><span class="sxs-lookup"><span data-stu-id="20291-143">The following is sample output from the program.</span></span>  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="20291-144">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="20291-144">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="20291-145">Aprire il file di progetto OrderProcessingPolicy.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20291-145">Open the OrderProcessingPolicy.sln project file in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="20291-146">Esistono due progetti diversi nella soluzione: `OrderErrorLibrary` e `OrderProcessingPolicy`.</span><span class="sxs-lookup"><span data-stu-id="20291-146">There are two different projects in the solution: `OrderErrorLibrary` and `OrderProcessingPolicy`.</span></span> <span data-ttu-id="20291-147">Il progetto `OrderProcessingPolicy` usa classi e metodi definiti in `OrderErrorLibrary`.</span><span class="sxs-lookup"><span data-stu-id="20291-147">The `OrderProcessingPolicy` project uses classes and methods defined in the `OrderErrorLibrary`.</span></span>  
  
3.  <span data-ttu-id="20291-148">Compilare tutti i progetti.</span><span class="sxs-lookup"><span data-stu-id="20291-148">Build all projects.</span></span>  
  
4.  <span data-ttu-id="20291-149">Fai clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="20291-149">Click **Run**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20291-150">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="20291-150">The samples may already be installed on your computer.</span></span> <span data-ttu-id="20291-151">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="20291-151">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="20291-152">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="20291-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="20291-153">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="20291-153">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`