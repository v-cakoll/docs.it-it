---
title: Convenzioni di denominazione di Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dfdb403519d7e29602fc87445ce32aeb0e55250e
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2017
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="7bd64-102">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bd64-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="7bd64-103">Quando si assegna un elemento nell'applicazione Visual Basic, il primo carattere del nome deve essere un carattere alfabetico o un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="7bd64-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="7bd64-104">Si noti tuttavia che i nomi che iniziano con un carattere di sottolineatura non sono compatibili con la [indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="7bd64-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="7bd64-105">I suggerimenti seguenti si applicano a denominazione.</span><span class="sxs-lookup"><span data-stu-id="7bd64-105">The following suggestions apply to naming.</span></span>  
  
-   <span data-ttu-id="7bd64-106">Iniziare di ciascuna parola in un nome con una lettera maiuscola, ad esempio `FindLastRecord` e `RedrawMyForm`.</span><span class="sxs-lookup"><span data-stu-id="7bd64-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
-   <span data-ttu-id="7bd64-107">Funzioni e metodi nomi devono iniziare con un verbo HTTP, come `InitNameArray` o `CloseDialog`.</span><span class="sxs-lookup"><span data-stu-id="7bd64-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
-   <span data-ttu-id="7bd64-108">Iniziare classe, struttura, modulo e i nomi delle proprietà e un sostantivo, ad esempio `EmployeeName` o `CarAccessory`.</span><span class="sxs-lookup"><span data-stu-id="7bd64-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
-   <span data-ttu-id="7bd64-109">Interfaccia nomi devono iniziare con il prefisso "I", seguito da un sostantivo o un sintagma nominale, ad esempio `IComponent`, oppure con un aggettivo che descrive il comportamento dell'interfaccia, ad esempio `IPersistable`.</span><span class="sxs-lookup"><span data-stu-id="7bd64-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="7bd64-110">Non utilizzare il carattere di sottolineatura e abbreviazioni con cautela, perché le abbreviazioni possono provocare confusione.</span><span class="sxs-lookup"><span data-stu-id="7bd64-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
-   <span data-ttu-id="7bd64-111">I nomi dei gestori eventi devono iniziare con una che descrive il tipo di evento aggiungendo il "`EventHandler`"suffisso, come in"`MouseEventHandler`".</span><span class="sxs-lookup"><span data-stu-id="7bd64-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
-   <span data-ttu-id="7bd64-112">Il nome delle classi di argomenti di evento, includere il "`EventArgs`" suffisso.</span><span class="sxs-lookup"><span data-stu-id="7bd64-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
-   <span data-ttu-id="7bd64-113">Se un evento è un concetto di "before" o "after", utilizzare un suffisso presente o passato, come in "`ControlAdd`"o"`ControlAdded`".</span><span class="sxs-lookup"><span data-stu-id="7bd64-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
-   <span data-ttu-id="7bd64-114">Per i termini di tempo o utilizzati di frequente, le abbreviazioni per mantenere la lunghezza del nome ragionevole, ad esempio, "HTML", anziché "Hypertext Markup Language".</span><span class="sxs-lookup"><span data-stu-id="7bd64-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="7bd64-115">In generale, i nomi delle variabili maggiore di 32 caratteri sono difficili da leggere su un monitor impostato a bassa risoluzione.</span><span class="sxs-lookup"><span data-stu-id="7bd64-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="7bd64-116">Assicurarsi inoltre che le abbreviazioni sono coerenti in tutta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7bd64-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="7bd64-117">All'interno di un progetto tra "HTML" e "Hypertext Markup Language" può generare confusione.</span><span class="sxs-lookup"><span data-stu-id="7bd64-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
-   <span data-ttu-id="7bd64-118">Evitare di utilizzare nomi in un ambito interno che sono gli stessi nomi in un ambito esterno.</span><span class="sxs-lookup"><span data-stu-id="7bd64-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="7bd64-119">Possono verificarsi errori se si accede alla variabile non corretta.</span><span class="sxs-lookup"><span data-stu-id="7bd64-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="7bd64-120">Se si verifica un conflitto tra una variabile e la parola chiave con lo stesso nome, è necessario identificare la parola chiave anteponendovi la libreria dei tipi appropriati.</span><span class="sxs-lookup"><span data-stu-id="7bd64-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="7bd64-121">Ad esempio, se si dispone di una variabile denominata `Date`, è possibile utilizzare la funzione intrinseca `Date` funzione solo per la chiamata <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bd64-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd64-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bd64-122">See Also</span></span>  
 [<span data-ttu-id="7bd64-123">Parole chiave come nomi di elementi nel codice</span><span class="sxs-lookup"><span data-stu-id="7bd64-123">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 [<span data-ttu-id="7bd64-124">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="7bd64-124">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="7bd64-125">Nomi di elementi dichiarati</span><span class="sxs-lookup"><span data-stu-id="7bd64-125">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="7bd64-126">Struttura del programma e convenzioni di scrittura del codice</span><span class="sxs-lookup"><span data-stu-id="7bd64-126">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="7bd64-127">Riferimenti per il linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bd64-127">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
