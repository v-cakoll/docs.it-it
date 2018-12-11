---
title: Nomi di spazi dei nomi
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: KrzysztofCwalina
ms.openlocfilehash: 64efdc46583a0931df9f57c32424ca4233bf2b82
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143441"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="dea47-102">Nomi di spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="dea47-102">Names of Namespaces</span></span>
<span data-ttu-id="dea47-103">Come con altre convenzioni di denominazione, l'obiettivo per la denominazione degli spazi dei nomi consiste nel creare chiarezza sufficiente per il programmatore usando il framework immediatamente sapere che cos'è probabile che il contenuto dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dea47-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="dea47-104">Il modello seguente specifica la regola generale per la denominazione degli spazi dei nomi:</span><span class="sxs-lookup"><span data-stu-id="dea47-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="dea47-105">Di seguito è riportati esempi:</span><span class="sxs-lookup"><span data-stu-id="dea47-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="dea47-106">**✓ DO** spazi dei nomi con un nome della società per evitare gli spazi dei nomi di società diverse da con lo stesso nome del prefisso.</span><span class="sxs-lookup"><span data-stu-id="dea47-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="dea47-107">**✓ DO** utilizzare un nome stabile e indipendente dalla versione del prodotto nel secondo livello di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dea47-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="dea47-108">**X DO NOT** utilizzare gerarchie organizzative come base per i nomi nelle gerarchie dello spazio dei nomi, perché i nomi dei gruppi all'interno di aziende tendono a essere di breve durata.</span><span class="sxs-lookup"><span data-stu-id="dea47-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="dea47-109">Organizzare la gerarchia di spazi dei nomi intorno a gruppi di tecnologie correlate.</span><span class="sxs-lookup"><span data-stu-id="dea47-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="dea47-110">**✓ DO** utilizzare il sistema Pascal e i componenti di spazio dei nomi separato con punti (ad esempio, `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="dea47-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="dea47-111">Se il vostro marchio impiega le maiuscole e minuscole non convenzionale, è consigliabile seguire le maiuscole e minuscole definite per il tuo marchio, anche se esso devia dal maiuscole e minuscole normale dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dea47-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="dea47-112">**✓ CONSIDER** usando nomi plurali ove appropriato.</span><span class="sxs-lookup"><span data-stu-id="dea47-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="dea47-113">Ad esempio, usare `System.Collections` invece di `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="dea47-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="dea47-114">Nomi di marchi e gli acronimi sono tuttavia eccezioni a questa regola.</span><span class="sxs-lookup"><span data-stu-id="dea47-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="dea47-115">Ad esempio, usare `System.IO` invece di `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="dea47-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="dea47-116">**X DO NOT** utilizzare lo stesso nome per uno spazio dei nomi e un tipo nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dea47-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="dea47-117">Ad esempio, non usare `Debug` come uno spazio dei nomi un nome e quindi fornire anche una classe denominata `Debug` nello spazio dei nomi stesso.</span><span class="sxs-lookup"><span data-stu-id="dea47-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="dea47-118">Alcuni compilatori richiedono tali tipi devono essere completi.</span><span class="sxs-lookup"><span data-stu-id="dea47-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="dea47-119">Conflitti di nomi e spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="dea47-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="dea47-120">**X DO NOT** introducono i nomi di tipo generico, ad esempio `Element`, `Node`, `Log`, e `Message`.</span><span class="sxs-lookup"><span data-stu-id="dea47-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="dea47-121">È presente un'elevata probabilità che questa operazione porterà a digitare nome è in conflitto in comune scenari.</span><span class="sxs-lookup"><span data-stu-id="dea47-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="dea47-122">È necessario qualificare i nomi di tipo generico (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="dea47-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="dea47-123">Sono disponibili linee guida specifiche per evitare conflitti di nomi di tipo per le diverse categorie di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dea47-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="dea47-124">**Spazi dei nomi del modello di applicazione**</span><span class="sxs-lookup"><span data-stu-id="dea47-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="dea47-125">Gli spazi dei nomi che appartengono a un singolo modello di applicazione molto spesso vengono utilizzati insieme, ma non sono quasi mai usati con gli spazi dei nomi di altri modelli di applicazione.</span><span class="sxs-lookup"><span data-stu-id="dea47-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="dea47-126">Ad esempio, il <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi è molto raramente utilizzata in combinazione con il <xref:System.Web.UI?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dea47-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="dea47-127">Di seguito è riportato un elenco noto modello dello spazio dei nomi di gruppi di applicazioni:</span><span class="sxs-lookup"><span data-stu-id="dea47-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="dea47-128">**X DO NOT** assegnare lo stesso nome per i tipi negli spazi dei nomi all'interno di un modello di applicazione singolo.</span><span class="sxs-lookup"><span data-stu-id="dea47-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="dea47-129">Ad esempio, non aggiungere un tipo denominato `Page` per il <xref:System.Web.UI.Adapters?displayProperty=nameWithType> dello spazio dei nomi, perché le <xref:System.Web.UI?displayProperty=nameWithType> dello spazio dei nomi contiene già un tipo denominato `Page`.</span><span class="sxs-lookup"><span data-stu-id="dea47-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="dea47-130">**Spazi dei nomi dell'infrastruttura**</span><span class="sxs-lookup"><span data-stu-id="dea47-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="dea47-131">Questo gruppo contiene spazi dei nomi che raramente vengono importati durante lo sviluppo di applicazioni comuni.</span><span class="sxs-lookup"><span data-stu-id="dea47-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="dea47-132">Ad esempio, `.Design` gli spazi dei nomi sono utilizzati principalmente per strumenti di sviluppo di programmazione.</span><span class="sxs-lookup"><span data-stu-id="dea47-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="dea47-133">Come evitare conflitti con i tipi in questi spazi dei nomi non è critico.</span><span class="sxs-lookup"><span data-stu-id="dea47-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="dea47-134">**Spazi dei nomi core**</span><span class="sxs-lookup"><span data-stu-id="dea47-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="dea47-135">Gli spazi dei nomi core includono tutti `System` spazi dei nomi, esclusi gli spazi dei nomi dei modelli di applicazione e gli spazi dei nomi dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="dea47-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="dea47-136">Spazi dei nomi core includono, ad esempio, `System`, `System.IO`, `System.Xml`, e `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="dea47-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="dea47-137">**X DO NOT** consentono di tipi di nomi in conflitto con qualsiasi tipo negli spazi dei nomi dei componenti di base.</span><span class="sxs-lookup"><span data-stu-id="dea47-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="dea47-138">Ad esempio, non utilizzare mai `Stream` come nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="dea47-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="dea47-139">Genererebbe un conflitto con <xref:System.IO.Stream?displayProperty=nameWithType>, un molto usati tipo.</span><span class="sxs-lookup"><span data-stu-id="dea47-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="dea47-140">**Gruppi dello spazio dei nomi di tecnologia**</span><span class="sxs-lookup"><span data-stu-id="dea47-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="dea47-141">Questa categoria include tutti gli spazi dei nomi con i primi due nodi dello spazio dei nomi stesso `(<Company>.<Technology>*`), ad esempio `Microsoft.Build.Utilities` e `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="dea47-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="dea47-142">È importante che i tipi che appartengono a una sola tecnologia non sia in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="dea47-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="dea47-143">**X DO NOT** assegnare nomi dei tipi che possano entrare in conflitto con altri tipi all'interno di una singola tecnologia.</span><span class="sxs-lookup"><span data-stu-id="dea47-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="dea47-144">**X DO NOT** introdurre conflitti di nomi tra i tipi negli spazi dei nomi di tecnologia e uno spazio dei nomi del modello di applicazione (a meno che la tecnologia non deve essere utilizzato con il modello di applicazione).</span><span class="sxs-lookup"><span data-stu-id="dea47-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="dea47-145">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="dea47-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="dea47-146">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="dea47-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea47-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dea47-147">See also</span></span>

- [<span data-ttu-id="dea47-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="dea47-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="dea47-149">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="dea47-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
