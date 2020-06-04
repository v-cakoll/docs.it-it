---
title: Convenzioni di denominazione
ms.date: 07/20/2015
helpviewer_keywords:
- names [Visual Basic], Visual Basic rules
- naming conventions
- naming conventions [Visual Basic], Visual Basic
- Visual Basic code, naming conventions
- conventions [Visual Basic], Visual Basic coding
- names [Visual Basic], naming conventions
- naming conventions [Visual Basic], classes
ms.assetid: 164949a4-2a7c-4736-9d82-9c3078e2e56c
ms.openlocfilehash: 20531e379ddf9b93a278795e9b3c0eb91b47e077
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398344"
---
# <a name="visual-basic-naming-conventions"></a><span data-ttu-id="9e462-102">Convenzioni di denominazione di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e462-102">Visual Basic Naming Conventions</span></span>
<span data-ttu-id="9e462-103">Quando si rinomina un elemento nell'applicazione Visual Basic, il primo carattere del nome deve essere un carattere alfabetico o un carattere di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="9e462-103">When you name an element in your Visual Basic application, the first character of that name must be an alphabetic character or an underscore.</span></span> <span data-ttu-id="9e462-104">Si noti, tuttavia, che i nomi che iniziano con un carattere di sottolineatura non sono conformi all' [indipendenza del linguaggio e a CLS (Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) ).</span><span class="sxs-lookup"><span data-stu-id="9e462-104">Note, however, that names beginning with an underscore are not compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span>  
  
 <span data-ttu-id="9e462-105">I suggerimenti seguenti si applicano alla denominazione.</span><span class="sxs-lookup"><span data-stu-id="9e462-105">The following suggestions apply to naming.</span></span>  
  
- <span data-ttu-id="9e462-106">Iniziare ogni parola separata in un nome con una lettera maiuscola, come in `FindLastRecord` e `RedrawMyForm` .</span><span class="sxs-lookup"><span data-stu-id="9e462-106">Begin each separate word in a name with a capital letter, as in `FindLastRecord` and `RedrawMyForm`.</span></span>  
  
- <span data-ttu-id="9e462-107">Iniziare i nomi di funzione e metodo con un verbo, come in `InitNameArray` o `CloseDialog` .</span><span class="sxs-lookup"><span data-stu-id="9e462-107">Begin function and method names with a verb, as in `InitNameArray` or `CloseDialog`.</span></span>  
  
- <span data-ttu-id="9e462-108">Iniziare i nomi di classe, struttura, modulo e proprietà con un sostantivo, come in `EmployeeName` o `CarAccessory` .</span><span class="sxs-lookup"><span data-stu-id="9e462-108">Begin class, structure, module, and property names with a noun, as in `EmployeeName` or `CarAccessory`.</span></span>  
  
- <span data-ttu-id="9e462-109">Iniziare i nomi di interfaccia con il prefisso "I", seguito da un sostantivo o da una frase nominale, `IComponent` ad esempio, o con un aggettivo che descrive il comportamento dell'interfaccia, ad esempio `IPersistable` .</span><span class="sxs-lookup"><span data-stu-id="9e462-109">Begin interface names with the prefix "I", followed by a noun or a noun phrase, like `IComponent`, or with an adjective describing the interface's behavior, like `IPersistable`.</span></span> <span data-ttu-id="9e462-110">Non usare il carattere di sottolineatura e usare le abbreviazioni sporadicamente, perché le abbreviazioni possono causare confusione.</span><span class="sxs-lookup"><span data-stu-id="9e462-110">Do not use the underscore, and use abbreviations sparingly, because abbreviations can cause confusion.</span></span>  
  
- <span data-ttu-id="9e462-111">Iniziare i nomi dei gestori eventi con un sostantivo che descrive il tipo di evento seguito dal `EventHandler` suffisso "", come in " `MouseEventHandler` ".</span><span class="sxs-lookup"><span data-stu-id="9e462-111">Begin event handler names with a noun describing the type of event followed by the "`EventHandler`" suffix, as in "`MouseEventHandler`".</span></span>  
  
- <span data-ttu-id="9e462-112">Nei nomi delle classi di argomenti dell'evento includere il `EventArgs` suffisso "".</span><span class="sxs-lookup"><span data-stu-id="9e462-112">In names of event argument classes, include the "`EventArgs`" suffix.</span></span>  
  
- <span data-ttu-id="9e462-113">Se un evento ha un concetto di "before" o "After", usare un suffisso presente o passato, come in " `ControlAdd` " o " `ControlAdded` ".</span><span class="sxs-lookup"><span data-stu-id="9e462-113">If an event has a concept of "before" or "after," use a suffix in present or past tense, as in "`ControlAdd`" or "`ControlAdded`".</span></span>  
  
- <span data-ttu-id="9e462-114">Per i termini usati lungo o di frequente, usare le abbreviazioni per tenere ragionevoli le lunghezze dei nomi, ad esempio, "HTML" invece di "Hypertext Markup Language".</span><span class="sxs-lookup"><span data-stu-id="9e462-114">For long or frequently used terms, use abbreviations to keep name lengths reasonable, for example, "HTML", instead of "Hypertext Markup Language".</span></span> <span data-ttu-id="9e462-115">In generale, i nomi delle variabili maggiori di 32 caratteri sono difficili da leggere in un monitor impostato su una risoluzione bassa.</span><span class="sxs-lookup"><span data-stu-id="9e462-115">In general, variable names greater than 32 characters are difficult to read on a monitor set to a low resolution.</span></span> <span data-ttu-id="9e462-116">Inoltre, assicurarsi che le abbreviazioni siano coerenti nell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e462-116">Also, make sure your abbreviations are consistent throughout the entire application.</span></span> <span data-ttu-id="9e462-117">Il cambio casuale di un progetto tra "HTML" e "Hypertext Markup Language" può causare confusione.</span><span class="sxs-lookup"><span data-stu-id="9e462-117">Randomly switching in a project between "HTML" and "Hypertext Markup Language" can lead to confusion.</span></span>  
  
- <span data-ttu-id="9e462-118">Evitare di usare nomi in un ambito interno identici a quelli in un ambito esterno.</span><span class="sxs-lookup"><span data-stu-id="9e462-118">Avoid using names in an inner scope that are the same as names in an outer scope.</span></span> <span data-ttu-id="9e462-119">Se si accede a una variabile errata, possono verificarsi errori.</span><span class="sxs-lookup"><span data-stu-id="9e462-119">Errors can result if the wrong variable is accessed.</span></span> <span data-ttu-id="9e462-120">Se si verifica un conflitto tra una variabile e la parola chiave con lo stesso nome, è necessario identificare la parola chiave facendola precedere dalla libreria dei tipi appropriata.</span><span class="sxs-lookup"><span data-stu-id="9e462-120">If a conflict occurs between a variable and the keyword of the same name, you must identify the keyword by preceding it with the appropriate type library.</span></span> <span data-ttu-id="9e462-121">Se, ad esempio, è presente una variabile denominata `Date` , è possibile usare la `Date` funzione intrinseca solo chiamando <xref:System.DateTime.Date%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9e462-121">For example, if you have a variable called `Date`, you can use the intrinsic `Date` function only by calling <xref:System.DateTime.Date%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e462-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e462-122">See also</span></span>

- [<span data-ttu-id="9e462-123">Parole chiave come nomi di elementi nel codice</span><span class="sxs-lookup"><span data-stu-id="9e462-123">Keywords as Element Names in Code</span></span>](keywords-as-element-names-in-code.md)
- [<span data-ttu-id="9e462-124">Me, My, MyBase e MyClass</span><span class="sxs-lookup"><span data-stu-id="9e462-124">Me, My, MyBase, and MyClass</span></span>](me-my-mybase-and-myclass.md)
- [<span data-ttu-id="9e462-125">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="9e462-125">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="9e462-126">Struttura del programma e convenzioni del codice</span><span class="sxs-lookup"><span data-stu-id="9e462-126">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="9e462-127">Riferimenti al linguaggio Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e462-127">Visual Basic Language Reference</span></span>](../../language-reference/index.md)
