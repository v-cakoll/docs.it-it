---
title: Funzionalità del linguaggio
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, elements of
- Visual Basic code
ms.assetid: b0b21730-298c-47e6-9a2f-cc81f628067b
ms.openlocfilehash: 2a2e8d0a08fda5783fa20e7403ea215133d0514e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405055"
---
# <a name="visual-basic-language-features"></a><span data-ttu-id="63f1a-102">Funzionalità del linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63f1a-102">Visual Basic Language Features</span></span>
<span data-ttu-id="63f1a-103">Gli argomenti seguenti introducono e discutono i componenti essenziali di Visual Basic, un linguaggio di programmazione orientato a oggetti.</span><span class="sxs-lookup"><span data-stu-id="63f1a-103">The following topics introduce and discuss the essential components of Visual Basic, an object-oriented programming language.</span></span> <span data-ttu-id="63f1a-104">Dopo aver creato l'interfaccia utente per l'applicazione usando form e controlli, è necessario scrivere il codice per la definizione del comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="63f1a-104">After creating the user interface for your application using forms and controls, you need to write the code that defines the application's behavior.</span></span> <span data-ttu-id="63f1a-105">Come per qualsiasi linguaggio di programmazione moderno, Visual Basic supporta numerosi costrutti di programmazione e elementi di linguaggio comuni.</span><span class="sxs-lookup"><span data-stu-id="63f1a-105">As with any modern programming language, Visual Basic supports a number of common programming constructs and language elements.</span></span>  
  
 <span data-ttu-id="63f1a-106">Se si conoscono altri linguaggi di programmazione, molti dei concetti trattati in questa sezione potrebbero sembrare familiari.</span><span class="sxs-lookup"><span data-stu-id="63f1a-106">If you have programmed in other languages, much of the material covered in this section might seem familiar.</span></span> <span data-ttu-id="63f1a-107">Anche se la maggior parte dei costrutti è simile a quella di altri linguaggi, la natura guidata dagli eventi di Visual Basic introduce alcune piccole differenze.</span><span class="sxs-lookup"><span data-stu-id="63f1a-107">While most of the constructs are similar to those in other languages, the event-driven nature of Visual Basic introduces some subtle differences.</span></span>  
  
 <span data-ttu-id="63f1a-108">Se non si ha esperienza di programmazione, le informazioni in questa sezione possono fungere da introduzione ai concetti fondamentali per la scrittura di codice.</span><span class="sxs-lookup"><span data-stu-id="63f1a-108">If you are new to programming, the material in this section serves as an introduction to the basic building blocks for writing code.</span></span> <span data-ttu-id="63f1a-109">Una volta appreso le nozioni di base, è possibile creare potenti applicazioni usando Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63f1a-109">Once you understand the basics, you can create powerful applications using Visual Basic.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63f1a-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="63f1a-110">In This Section</span></span>  
 [<span data-ttu-id="63f1a-111">Matrici</span><span class="sxs-lookup"><span data-stu-id="63f1a-111">Arrays</span></span>](arrays/index.md)  
 <span data-ttu-id="63f1a-112">Informazioni su come rendere il codice più compatto e potente tramite la dichiarazione e l'uso delle matrici, che contengono più valori correlati.</span><span class="sxs-lookup"><span data-stu-id="63f1a-112">Discusses making your code more compact and powerful by declaring and using arrays, which hold multiple related values.</span></span>  
  
 [<span data-ttu-id="63f1a-113">Inizializzatori di insieme</span><span class="sxs-lookup"><span data-stu-id="63f1a-113">Collection Initializers</span></span>](collection-initializers/index.md)  
 <span data-ttu-id="63f1a-114">Descrizione degli inizializzatori di raccolta, che consentono di creare una raccolta e popolarla con un set iniziale di valori.</span><span class="sxs-lookup"><span data-stu-id="63f1a-114">Describes collection initializers, which enable you to create a collection and populate it with an initial set of values.</span></span>  
  
 [<span data-ttu-id="63f1a-115">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="63f1a-115">Constants and Enumerations</span></span>](constants-enums/index.md)  
 <span data-ttu-id="63f1a-116">Informazioni sull'archiviazione dei valori costanti per l'uso ripetuto, compresi i set di valori costanti correlati.</span><span class="sxs-lookup"><span data-stu-id="63f1a-116">Discusses storing unchanging values for repeated use, including sets of related constant values.</span></span>  
  
 [<span data-ttu-id="63f1a-117">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="63f1a-117">Control Flow</span></span>](control-flow/index.md)  
 <span data-ttu-id="63f1a-118">Informazioni su come regolare il flusso di esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="63f1a-118">Shows how to regulate the flow of your program's execution.</span></span>  
  
 [<span data-ttu-id="63f1a-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="63f1a-119">Data Types</span></span>](data-types/index.md)  
 <span data-ttu-id="63f1a-120">Descrizione dei tipi di dati che può contenere un elemento di programmazione e delle modalità di archiviazione di tali dati.</span><span class="sxs-lookup"><span data-stu-id="63f1a-120">Describes what kinds of data a programming element can hold and how that data is stored.</span></span>  
  
 [<span data-ttu-id="63f1a-121">Elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="63f1a-121">Declared Elements</span></span>](declared-elements/index.md)  
 <span data-ttu-id="63f1a-122">Informazioni sugli elementi di programmazione che è possibile dichiarare, i relativi nomi e caratteristiche e su come il compilatore risolve i riferimenti a tali elementi.</span><span class="sxs-lookup"><span data-stu-id="63f1a-122">Covers programming elements you can declare, their names and characteristics, and how the compiler resolves references to them.</span></span>  
  
 [<span data-ttu-id="63f1a-123">Delegati</span><span class="sxs-lookup"><span data-stu-id="63f1a-123">Delegates</span></span>](delegates/index.md)  
 <span data-ttu-id="63f1a-124">Introduzione ai delegati e ai possibili usi in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63f1a-124">Provides an introduction to delegates and how they are used in Visual Basic.</span></span>  
  
 [<span data-ttu-id="63f1a-125">Associazione anticipata e tardiva</span><span class="sxs-lookup"><span data-stu-id="63f1a-125">Early and Late Binding</span></span>](early-late-binding/index.md)  
 <span data-ttu-id="63f1a-126">Descrizione dell'associazione, eseguita dal compilatore quando un oggetto viene assegnato a una variabile oggetto, e informazioni sulle differenze tra gli oggetti ad associazione anticipata e tardiva.</span><span class="sxs-lookup"><span data-stu-id="63f1a-126">Describes binding, which is performed by the compiler when an object is assigned to an object variable, and the differences between early-bound and late-bound objects.</span></span>  
  
 [<span data-ttu-id="63f1a-127">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="63f1a-127">Error Types</span></span>](error-types.md)  
 <span data-ttu-id="63f1a-128">Panoramica degli errori di sintassi, degli errori di run-time e degli errori di logica.</span><span class="sxs-lookup"><span data-stu-id="63f1a-128">Provides an overview of syntax errors, run-time errors, and logic errors.</span></span>  
  
 [<span data-ttu-id="63f1a-129">Events</span><span class="sxs-lookup"><span data-stu-id="63f1a-129">Events</span></span>](events/index.md)  
 <span data-ttu-id="63f1a-130">Informazioni su come dichiarare e usare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="63f1a-130">Shows how to declare and use events.</span></span>  
  
 [<span data-ttu-id="63f1a-131">Interfacce</span><span class="sxs-lookup"><span data-stu-id="63f1a-131">Interfaces</span></span>](interfaces/index.md)  
 <span data-ttu-id="63f1a-132">Descrizione delle caratteristiche delle interfacce e di come si possono usare nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="63f1a-132">Describes what interfaces are and how you can use them in your applications.</span></span>  
  
 [<span data-ttu-id="63f1a-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="63f1a-133">LINQ</span></span>](linq/index.md)  
 <span data-ttu-id="63f1a-134">Vengono forniti collegamenti ad argomenti che introducono funzionalità LINQ (Language Integrated Query) e programmazione.</span><span class="sxs-lookup"><span data-stu-id="63f1a-134">Provides links to topics that introduce Language-Integrated Query (LINQ) features and programming.</span></span>  
  
 [<span data-ttu-id="63f1a-135">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="63f1a-135">Objects and Classes</span></span>](objects-and-classes/index.md)  
 <span data-ttu-id="63f1a-136">Panoramica di oggetti e classi, di come vengono usati, delle relazioni tra questi elementi e delle proprietà, dei metodi e degli eventi che espongono.</span><span class="sxs-lookup"><span data-stu-id="63f1a-136">Provides an overview of objects and classes, how they are used, their relationships to each other, and the properties, methods, and events they expose.</span></span>  
  
 [<span data-ttu-id="63f1a-137">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="63f1a-137">Operators and Expressions</span></span>](operators-and-expressions/index.md)  
 <span data-ttu-id="63f1a-138">Descrizione degli elementi di codice che consentono di modificare gli elementi contenenti valori, di come usarli in modo efficiente e come combinarli per ottenere nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="63f1a-138">Describes the code elements that manipulate value-holding elements, how to use them efficiently, and how to combine them to yield new values.</span></span>  
  
 [<span data-ttu-id="63f1a-139">Procedure</span><span class="sxs-lookup"><span data-stu-id="63f1a-139">Procedures</span></span>](procedures/index.md)  
 <span data-ttu-id="63f1a-140">Descrizione delle routine `Sub`, `Function`, `Property` e `Operator`, oltre ad argomenti avanzati quali come le routine ricorsive e di overload.</span><span class="sxs-lookup"><span data-stu-id="63f1a-140">Describes `Sub`, `Function`, `Property`, and `Operator` procedures, as well as advanced topics such as recursive and overloaded procedures.</span></span>  
  
 [<span data-ttu-id="63f1a-141">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="63f1a-141">Statements</span></span>](statements.md)  
 <span data-ttu-id="63f1a-142">Descrizione della dichiarazione e delle istruzioni eseguibili.</span><span class="sxs-lookup"><span data-stu-id="63f1a-142">Describes declaration and executable statements.</span></span>  
  
 [<span data-ttu-id="63f1a-143">Stringhe</span><span class="sxs-lookup"><span data-stu-id="63f1a-143">Strings</span></span>](strings/index.md)  
 <span data-ttu-id="63f1a-144">Collegamenti ad argomenti che descrivono i concetti di base sull'uso delle stringhe in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63f1a-144">Provides links to topics that describe the basic concepts about using strings in Visual Basic.</span></span>  
  
 [<span data-ttu-id="63f1a-145">Variabili</span><span class="sxs-lookup"><span data-stu-id="63f1a-145">Variables</span></span>](variables/index.md)  
 <span data-ttu-id="63f1a-146">Introduzione alle variabili e descrizione di come usarle in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63f1a-146">Introduces variables and describes how to use them in Visual Basic.</span></span>  
  
 [<span data-ttu-id="63f1a-147">XML</span><span class="sxs-lookup"><span data-stu-id="63f1a-147">XML</span></span>](xml/index.md)  
 <span data-ttu-id="63f1a-148">Collegamenti ad argomenti che descrivono come usare XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63f1a-148">Provides links to topics that describe how to use XML in Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="63f1a-149">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="63f1a-149">Related Sections</span></span>

 [<span data-ttu-id="63f1a-150">raccolte</span><span class="sxs-lookup"><span data-stu-id="63f1a-150">Collections</span></span>](../concepts/collections.md)  
 <span data-ttu-id="63f1a-151">Descrizione di alcuni dei tipi di raccolte disponibili in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="63f1a-151">Describes some of the types of collections that are provided by the .NET Framework.</span></span> <span data-ttu-id="63f1a-152">Viene mostrato come usare raccolte semplici e raccolte di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="63f1a-152">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>  
  
 [<span data-ttu-id="63f1a-153">Riferimenti al linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63f1a-153">Visual Basic Language Reference</span></span>](../../language-reference/index.md)  
 <span data-ttu-id="63f1a-154">Vengono fornite informazioni di riferimento su vari aspetti della programmazione Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="63f1a-154">Provides reference information on various aspects of Visual Basic programming.</span></span>
