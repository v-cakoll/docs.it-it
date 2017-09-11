---
title: "Funzionalità del linguaggio Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, elements of
- Visual Basic code
ms.assetid: b0b21730-298c-47e6-9a2f-cc81f628067b
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3594e6622e8bc76839a15739a31ad27d17de8455
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="visual-basic-language-features"></a><span data-ttu-id="8dc2a-102">Funzionalità del linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dc2a-102">Visual Basic Language Features</span></span>
<span data-ttu-id="8dc2a-103">Gli argomenti seguenti introducono e illustrano i componenti essenziali di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], un linguaggio di programmazione orientato a oggetti.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-103">The following topics introduce and discuss the essential components of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], an object-oriented programming language.</span></span> <span data-ttu-id="8dc2a-104">Dopo aver creato l'interfaccia utente per l'applicazione usando form e controlli, è necessario scrivere il codice per la definizione del comportamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-104">After creating the user interface for your application using forms and controls, you need to write the code that defines the application's behavior.</span></span> <span data-ttu-id="8dc2a-105">Analogamente a qualsiasi linguaggio di programmazione moderno, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supporta numerosi costrutti di programmazione ed elementi di linguaggio comuni.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-105">As with any modern programming language, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] supports a number of common programming constructs and language elements.</span></span>  
  
 <span data-ttu-id="8dc2a-106">Se si conoscono altri linguaggi di programmazione, molti dei concetti trattati in questa sezione potrebbero sembrare familiari.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-106">If you have programmed in other languages, much of the material covered in this section might seem familiar.</span></span> <span data-ttu-id="8dc2a-107">Mentre la maggior parte dei costrutti è simile a quelli di altri linguaggi, la natura basata sugli eventi di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] introduce alcune piccole differenze.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-107">While most of the constructs are similar to those in other languages, the event-driven nature of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] introduces some subtle differences.</span></span>  
  
 <span data-ttu-id="8dc2a-108">Se non si ha esperienza di programmazione, le informazioni in questa sezione possono fungere da introduzione ai concetti fondamentali per la scrittura di codice.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-108">If you are new to programming, the material in this section serves as an introduction to the basic building blocks for writing code.</span></span> <span data-ttu-id="8dc2a-109">Dopo aver appreso le nozioni di base, è possibile creare applicazioni elaborate usando [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc2a-109">Once you understand the basics, you can create powerful applications using [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8dc2a-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="8dc2a-110">In This Section</span></span>  
 [<span data-ttu-id="8dc2a-111">Matrici</span><span class="sxs-lookup"><span data-stu-id="8dc2a-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 <span data-ttu-id="8dc2a-112">Informazioni su come rendere il codice più compatto e potente tramite la dichiarazione e l'uso delle matrici, che contengono più valori correlati.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-112">Discusses making your code more compact and powerful by declaring and using arrays, which hold multiple related values.</span></span>  
  
 [<span data-ttu-id="8dc2a-113">Inizializzatori di raccolta</span><span class="sxs-lookup"><span data-stu-id="8dc2a-113">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 <span data-ttu-id="8dc2a-114">Descrizione degli inizializzatori di raccolta, che consentono di creare una raccolta e popolarla con un set iniziale di valori.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-114">Describes collection initializers, which enable you to create a collection and populate it with an initial set of values.</span></span>  
  
 [<span data-ttu-id="8dc2a-115">Costanti ed enumerazioni</span><span class="sxs-lookup"><span data-stu-id="8dc2a-115">Constants and Enumerations</span></span>](../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 <span data-ttu-id="8dc2a-116">Informazioni sull'archiviazione dei valori costanti per l'uso ripetuto, compresi i set di valori costanti correlati.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-116">Discusses storing unchanging values for repeated use, including sets of related constant values.</span></span>  
  
 [<span data-ttu-id="8dc2a-117">Flusso di controllo</span><span class="sxs-lookup"><span data-stu-id="8dc2a-117">Control Flow</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 <span data-ttu-id="8dc2a-118">Informazioni su come regolare il flusso di esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-118">Shows how to regulate the flow of your program's execution.</span></span>  
  
 [<span data-ttu-id="8dc2a-119">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="8dc2a-119">Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="8dc2a-120">Descrizione dei tipi di dati che può contenere un elemento di programmazione e delle modalità di archiviazione di tali dati.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-120">Describes what kinds of data a programming element can hold and how that data is stored.</span></span>  
  
 [<span data-ttu-id="8dc2a-121">Elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="8dc2a-121">Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)  
 <span data-ttu-id="8dc2a-122">Informazioni sugli elementi di programmazione che è possibile dichiarare, i relativi nomi e caratteristiche e su come il compilatore risolve i riferimenti a tali elementi.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-122">Covers programming elements you can declare, their names and characteristics, and how the compiler resolves references to them.</span></span>  
  
 [<span data-ttu-id="8dc2a-123">Delegati</span><span class="sxs-lookup"><span data-stu-id="8dc2a-123">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 <span data-ttu-id="8dc2a-124">Introduzione ai delegati e ai possibili usi in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-124">Provides an introduction to delegates and how they are used in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8dc2a-125">Associazione anticipata e tardiva</span><span class="sxs-lookup"><span data-stu-id="8dc2a-125">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 <span data-ttu-id="8dc2a-126">Descrizione dell'associazione, eseguita dal compilatore quando un oggetto viene assegnato a una variabile oggetto, e informazioni sulle differenze tra gli oggetti ad associazione anticipata e tardiva.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-126">Describes binding, which is performed by the compiler when an object is assigned to an object variable, and the differences between early-bound and late-bound objects.</span></span>  
  
 [<span data-ttu-id="8dc2a-127">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="8dc2a-127">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 <span data-ttu-id="8dc2a-128">Panoramica degli errori di sintassi, degli errori di run-time e degli errori di logica.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-128">Provides an overview of syntax errors, run-time errors, and logic errors.</span></span>  
  
 [<span data-ttu-id="8dc2a-129">Eventi</span><span class="sxs-lookup"><span data-stu-id="8dc2a-129">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)  
 <span data-ttu-id="8dc2a-130">Informazioni su come dichiarare e usare gli eventi.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-130">Shows how to declare and use events.</span></span>  
  
 [<span data-ttu-id="8dc2a-131">Interfacce</span><span class="sxs-lookup"><span data-stu-id="8dc2a-131">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 <span data-ttu-id="8dc2a-132">Descrizione delle caratteristiche delle interfacce e di come si possono usare nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-132">Describes what interfaces are and how you can use them in your applications.</span></span>  
  
 [<span data-ttu-id="8dc2a-133">LINQ</span><span class="sxs-lookup"><span data-stu-id="8dc2a-133">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="8dc2a-134">Collegamenti agli argomenti introduttivi alle funzionalità e alla programmazione di [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc2a-134">Provides links to topics that introduce [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] features and programming.</span></span>  
  
 [<span data-ttu-id="8dc2a-135">Oggetti e classi</span><span class="sxs-lookup"><span data-stu-id="8dc2a-135">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 <span data-ttu-id="8dc2a-136">Panoramica di oggetti e classi, di come vengono usati, delle relazioni tra questi elementi e delle proprietà, dei metodi e degli eventi che espongono.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-136">Provides an overview of objects and classes, how they are used, their relationships to each other, and the properties, methods, and events they expose.</span></span>  
  
 [<span data-ttu-id="8dc2a-137">Operatori ed espressioni</span><span class="sxs-lookup"><span data-stu-id="8dc2a-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 <span data-ttu-id="8dc2a-138">Descrizione degli elementi di codice che consentono di modificare gli elementi contenenti valori, di come usarli in modo efficiente e come combinarli per ottenere nuovi valori.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-138">Describes the code elements that manipulate value-holding elements, how to use them efficiently, and how to combine them to yield new values.</span></span>  
  
 [<span data-ttu-id="8dc2a-139">Routine</span><span class="sxs-lookup"><span data-stu-id="8dc2a-139">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 <span data-ttu-id="8dc2a-140">Descrizione delle routine `Sub`, `Function`, `Property` e `Operator`, oltre ad argomenti avanzati quali come le routine ricorsive e di overload.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-140">Describes `Sub`, `Function`, `Property`, and `Operator` procedures, as well as advanced topics such as recursive and overloaded procedures.</span></span>  
  
 [<span data-ttu-id="8dc2a-141">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="8dc2a-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 <span data-ttu-id="8dc2a-142">Descrizione della dichiarazione e delle istruzioni eseguibili.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-142">Describes declaration and executable statements.</span></span>  
  
 [<span data-ttu-id="8dc2a-143">Stringhe</span><span class="sxs-lookup"><span data-stu-id="8dc2a-143">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 <span data-ttu-id="8dc2a-144">Collegamenti ad argomenti che descrivono i concetti di base sull'uso delle stringhe in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-144">Provides links to topics that describe the basic concepts about using strings in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8dc2a-145">Variabili</span><span class="sxs-lookup"><span data-stu-id="8dc2a-145">Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/index.md)  
 <span data-ttu-id="8dc2a-146">Introduzione alle variabili e descrizione di come usarle in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-146">Introduces variables and describes how to use them in Visual Basic.</span></span>  
  
 [<span data-ttu-id="8dc2a-147">XML</span><span class="sxs-lookup"><span data-stu-id="8dc2a-147">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="8dc2a-148">Collegamenti ad argomenti che descrivono come usare XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-148">Provides links to topics that describe how to use XML in Visual Basic.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8dc2a-149">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="8dc2a-149">Related Sections</span></span>  
 [<span data-ttu-id="8dc2a-150">Raccolte</span><span class="sxs-lookup"><span data-stu-id="8dc2a-150">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 <span data-ttu-id="8dc2a-151">Descrizione di alcuni dei tipi di raccolte disponibili in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-151">Describes some of the types of collections that are provided by the .NET Framework.</span></span> <span data-ttu-id="8dc2a-152">Viene mostrato come usare raccolte semplici e raccolte di coppie chiave/valore.</span><span class="sxs-lookup"><span data-stu-id="8dc2a-152">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>  
  
 [<span data-ttu-id="8dc2a-153">Riferimenti per il linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dc2a-153">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 <span data-ttu-id="8dc2a-154">Informazioni di riferimento su diversi aspetti della programmazione con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8dc2a-154">Provides reference information on various aspects of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming.</span></span>

