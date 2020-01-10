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
ms.openlocfilehash: 0678f695e3ae7c40660031862c9073a21fd72491
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709231"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="c924d-102">Nomi di spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="c924d-102">Names of Namespaces</span></span>
<span data-ttu-id="c924d-103">Come per le altre linee guida per la denominazione, l'obiettivo di denominare gli spazi dei nomi consiste nel creare una chiarezza sufficiente per il programmatore che usa il Framework per conoscere immediatamente il contenuto dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c924d-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="c924d-104">Nel modello seguente viene specificata la regola generale per la denominazione degli spazi dei nomi:</span><span class="sxs-lookup"><span data-stu-id="c924d-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="c924d-105">Di seguito vengono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="c924d-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="c924d-106">**✓ DO** spazi dei nomi con un nome della società per evitare gli spazi dei nomi di società diverse da con lo stesso nome del prefisso.</span><span class="sxs-lookup"><span data-stu-id="c924d-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="c924d-107">**✓ DO** utilizzare un nome stabile e indipendente dalla versione del prodotto nel secondo livello di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c924d-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="c924d-108">**X DO NOT** utilizzare gerarchie organizzative come base per i nomi nelle gerarchie dello spazio dei nomi, perché i nomi dei gruppi all'interno di aziende tendono a essere di breve durata.</span><span class="sxs-lookup"><span data-stu-id="c924d-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="c924d-109">Organizzare la gerarchia di spazi dei nomi intorno ai gruppi di tecnologie correlate.</span><span class="sxs-lookup"><span data-stu-id="c924d-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="c924d-110">**✓ DO** utilizzare il sistema Pascal e i componenti di spazio dei nomi separato con punti (ad esempio, `Microsoft.Office.PowerPoint`).</span><span class="sxs-lookup"><span data-stu-id="c924d-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="c924d-111">Se il marchio usa una combinazione di maiuscole e minuscole non tradizionale, è necessario seguire la combinazione di maiuscole e minuscole definita dal marchio, anche se si devia dalla normale combinazione dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="c924d-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="c924d-112">**✓ CONSIDER** usando nomi plurali ove appropriato.</span><span class="sxs-lookup"><span data-stu-id="c924d-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="c924d-113">Ad esempio, usare `System.Collections` invece di `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="c924d-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="c924d-114">I nomi e gli acronimi delle marche sono tuttavia eccezioni a questa regola.</span><span class="sxs-lookup"><span data-stu-id="c924d-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="c924d-115">Ad esempio, usare `System.IO` invece di `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="c924d-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="c924d-116">**X DO NOT** utilizzare lo stesso nome per uno spazio dei nomi e un tipo nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c924d-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="c924d-117">Ad esempio, non usare `Debug` come nome dello spazio dei nomi e quindi fornire anche una classe denominata `Debug` nello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c924d-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="c924d-118">Molti compilatori richiedono che tali tipi siano completi.</span><span class="sxs-lookup"><span data-stu-id="c924d-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="c924d-119">Conflitti di spazi dei nomi e nomi di tipo</span><span class="sxs-lookup"><span data-stu-id="c924d-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="c924d-120">**X DO NOT** introducono i nomi di tipo generico, ad esempio `Element`, `Node`, `Log`, e `Message`.</span><span class="sxs-lookup"><span data-stu-id="c924d-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="c924d-121">È molto probabile che questa operazione provochi conflitti tra i nomi dei tipi negli scenari comuni.</span><span class="sxs-lookup"><span data-stu-id="c924d-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="c924d-122">È necessario qualificare i nomi di tipo generico (`FormElement`, `XmlNode`, `EventLog``SoapMessage`).</span><span class="sxs-lookup"><span data-stu-id="c924d-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="c924d-123">Esistono linee guida specifiche per evitare conflitti tra nomi di tipi per diverse categorie di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c924d-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
- <span data-ttu-id="c924d-124">**Spazi dei nomi del modello di applicazione**</span><span class="sxs-lookup"><span data-stu-id="c924d-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="c924d-125">Gli spazi dei nomi che appartengono a un singolo modello di applicazione vengono spesso usati insieme, ma non vengono usati quasi mai con gli spazi dei nomi di altri modelli di applicazione.</span><span class="sxs-lookup"><span data-stu-id="c924d-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="c924d-126">Ad esempio, lo spazio dei nomi <xref:System.Windows.Forms?displayProperty=nameWithType> viene usato molto raramente insieme allo spazio dei nomi <xref:System.Web.UI?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c924d-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="c924d-127">Di seguito è riportato un elenco di gruppi di spazi dei nomi del modello di applicazione ben noti:</span><span class="sxs-lookup"><span data-stu-id="c924d-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="c924d-128">**X DO NOT** assegnare lo stesso nome per i tipi negli spazi dei nomi all'interno di un modello di applicazione singolo.</span><span class="sxs-lookup"><span data-stu-id="c924d-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="c924d-129">Non aggiungere ad esempio un tipo denominato `Page` allo spazio dei nomi <xref:System.Web.UI.Adapters?displayProperty=nameWithType>, perché lo spazio dei nomi <xref:System.Web.UI?displayProperty=nameWithType> già contiene un tipo denominato `Page`.</span><span class="sxs-lookup"><span data-stu-id="c924d-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
- <span data-ttu-id="c924d-130">**Spazi dei nomi dell'infrastruttura**</span><span class="sxs-lookup"><span data-stu-id="c924d-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="c924d-131">Questo gruppo contiene spazi dei nomi importati raramente durante lo sviluppo di applicazioni comuni.</span><span class="sxs-lookup"><span data-stu-id="c924d-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="c924d-132">Ad esempio, `.Design` gli spazi dei nomi vengono utilizzati principalmente per lo sviluppo di strumenti di programmazione.</span><span class="sxs-lookup"><span data-stu-id="c924d-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="c924d-133">Evitare conflitti con i tipi in questi spazi dei nomi non è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="c924d-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
- <span data-ttu-id="c924d-134">**Spazi dei nomi principali**</span><span class="sxs-lookup"><span data-stu-id="c924d-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="c924d-135">Gli spazi dei nomi principali includono tutti gli spazi dei nomi `System`, esclusi gli spazi dei nomi dei modelli di applicazione e gli spazi dei nomi dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="c924d-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="c924d-136">Gli spazi dei nomi principali includono, tra gli altri, `System`, `System.IO`, `System.Xml`e `System.Net`.</span><span class="sxs-lookup"><span data-stu-id="c924d-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="c924d-137">**X DO NOT** consentono di tipi di nomi in conflitto con qualsiasi tipo negli spazi dei nomi dei componenti di base.</span><span class="sxs-lookup"><span data-stu-id="c924d-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="c924d-138">Ad esempio, non usare mai `Stream` come nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="c924d-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="c924d-139">Si verificherebbe un conflitto con <xref:System.IO.Stream?displayProperty=nameWithType>, un tipo di uso molto comune.</span><span class="sxs-lookup"><span data-stu-id="c924d-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
- <span data-ttu-id="c924d-140">**Gruppi di spazi dei nomi tecnologici**</span><span class="sxs-lookup"><span data-stu-id="c924d-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="c924d-141">Questa categoria include tutti gli spazi dei nomi con gli stessi primi due nodi dello spazio dei nomi `(<Company>.<Technology>*`), ad esempio `Microsoft.Build.Utilities` e `Microsoft.Build.Tasks`.</span><span class="sxs-lookup"><span data-stu-id="c924d-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="c924d-142">È importante che i tipi che appartengono a una singola tecnologia non siano in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="c924d-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="c924d-143">**X DO NOT** assegnare nomi dei tipi che possano entrare in conflitto con altri tipi all'interno di una singola tecnologia.</span><span class="sxs-lookup"><span data-stu-id="c924d-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="c924d-144">**X DO NOT** introdurre conflitti di nomi tra i tipi negli spazi dei nomi di tecnologia e uno spazio dei nomi del modello di applicazione (a meno che la tecnologia non deve essere utilizzato con il modello di applicazione).</span><span class="sxs-lookup"><span data-stu-id="c924d-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="c924d-145">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="c924d-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="c924d-146">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="c924d-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c924d-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c924d-147">See also</span></span>

- [<span data-ttu-id="c924d-148">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="c924d-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="c924d-149">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="c924d-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
