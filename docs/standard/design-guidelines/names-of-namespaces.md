---
title: Nomi di spazi dei nomi
description: Usare queste linee guida per rinominare gli spazi dei nomi come parte delle linee guida per la progettazione di librerie che estendono e interagiscono con le librerie .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: e435e0281165b4a9f12bbccbeb10401b57375dcb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290201"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="56216-103">Nomi di spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="56216-103">Names of Namespaces</span></span>
<span data-ttu-id="56216-104">Come per le altre linee guida per la denominazione, l'obiettivo di denominare gli spazi dei nomi consiste nel creare una chiarezza sufficiente per il programmatore che usa il Framework per conoscere immediatamente il contenuto dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="56216-104">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="56216-105">Nel modello seguente viene specificata la regola generale per la denominazione degli spazi dei nomi:</span><span class="sxs-lookup"><span data-stu-id="56216-105">The following template specifies the general rule for naming namespaces:</span></span>

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 <span data-ttu-id="56216-106">Alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="56216-106">The following are examples:</span></span>

 <span data-ttu-id="56216-107">`Fabrikam.Math` `Litware.Security`</span><span class="sxs-lookup"><span data-stu-id="56216-107">`Fabrikam.Math` `Litware.Security`</span></span>

 <span data-ttu-id="56216-108">✔️ i nomi degli spazi dei nomi prefissi con il nome della società per impedire che gli spazi dei nomi di società diverse abbiano lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="56216-108">✔️ DO prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>

 <span data-ttu-id="56216-109">✔️ utilizzare un nome di prodotto stabile e indipendente dalla versione al secondo livello del nome di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="56216-109">✔️ DO use a stable, version-independent product name at the second level of a namespace name.</span></span>

 <span data-ttu-id="56216-110">❌Non usare gerarchie organizzative come base per i nomi nelle gerarchie dello spazio dei nomi, perché i nomi dei gruppi all'interno delle aziende tendono a essere di breve durata.</span><span class="sxs-lookup"><span data-stu-id="56216-110">❌ DO NOT use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="56216-111">Organizzare la gerarchia di spazi dei nomi intorno ai gruppi di tecnologie correlate.</span><span class="sxs-lookup"><span data-stu-id="56216-111">Organize the hierarchy of namespaces around groups of related technologies.</span></span>

 <span data-ttu-id="56216-112">✔️ utilizzare sistema Pascal e separare i componenti dello spazio dei nomi con i punti (ad esempio, `Microsoft.Office.PowerPoint` ).</span><span class="sxs-lookup"><span data-stu-id="56216-112">✔️ DO use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="56216-113">Se il marchio usa una combinazione di maiuscole e minuscole non tradizionale, è necessario seguire la combinazione di maiuscole e minuscole definita dal marchio, anche se si devia dalla normale combinazione dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="56216-113">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>

 <span data-ttu-id="56216-114">✔️ CONSIGLIABILE utilizzare nomi di spazi dei nomi plurali laddove appropriato.</span><span class="sxs-lookup"><span data-stu-id="56216-114">✔️ CONSIDER using plural namespace names where appropriate.</span></span>

 <span data-ttu-id="56216-115">Usare, ad esempio, `System.Collections` invece di `System.Collection`.</span><span class="sxs-lookup"><span data-stu-id="56216-115">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="56216-116">I nomi e gli acronimi delle marche sono tuttavia eccezioni a questa regola.</span><span class="sxs-lookup"><span data-stu-id="56216-116">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="56216-117">Usare, ad esempio, `System.IO` invece di `System.IOs`.</span><span class="sxs-lookup"><span data-stu-id="56216-117">For example, use `System.IO` instead of `System.IOs`.</span></span>

 <span data-ttu-id="56216-118">❌Non usare lo stesso nome per uno spazio dei nomi e un tipo in tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="56216-118">❌ DO NOT use the same name for a namespace and a type in that namespace.</span></span>

 <span data-ttu-id="56216-119">Ad esempio, non usare `Debug` come nome dello spazio dei nomi e quindi fornire anche una classe denominata `Debug` nello stesso spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="56216-119">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="56216-120">Molti compilatori richiedono che tali tipi siano completi.</span><span class="sxs-lookup"><span data-stu-id="56216-120">Several compilers require such types to be fully qualified.</span></span>

### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="56216-121">Conflitti di spazi dei nomi e nomi di tipo</span><span class="sxs-lookup"><span data-stu-id="56216-121">Namespaces and Type Name Conflicts</span></span>
 <span data-ttu-id="56216-122">❌Non introduce i nomi di tipo generico, ad esempio `Element` ,, `Node` `Log` e `Message` .</span><span class="sxs-lookup"><span data-stu-id="56216-122">❌ DO NOT introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>

 <span data-ttu-id="56216-123">È molto probabile che questa operazione provochi conflitti tra i nomi dei tipi negli scenari comuni.</span><span class="sxs-lookup"><span data-stu-id="56216-123">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="56216-124">È necessario qualificare i nomi di tipo generico ( `FormElement` ,, `XmlNode` `EventLog` , `SoapMessage` ).</span><span class="sxs-lookup"><span data-stu-id="56216-124">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>

 <span data-ttu-id="56216-125">Esistono linee guida specifiche per evitare conflitti tra nomi di tipi per diverse categorie di spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="56216-125">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>

- <span data-ttu-id="56216-126">**Spazi dei nomi del modello di applicazione**</span><span class="sxs-lookup"><span data-stu-id="56216-126">**Application model namespaces**</span></span>

     <span data-ttu-id="56216-127">Gli spazi dei nomi che appartengono a un singolo modello di applicazione vengono spesso usati insieme, ma non vengono usati quasi mai con gli spazi dei nomi di altri modelli di applicazione.</span><span class="sxs-lookup"><span data-stu-id="56216-127">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="56216-128">Lo spazio dei nomi, ad esempio, <xref:System.Windows.Forms?displayProperty=nameWithType> viene usato molto raramente insieme allo <xref:System.Web.UI?displayProperty=nameWithType> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="56216-128">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="56216-129">Di seguito è riportato un elenco di gruppi di spazi dei nomi del modello di applicazione ben noti:</span><span class="sxs-lookup"><span data-stu-id="56216-129">The following is a list of well-known application model namespace groups:</span></span>

     <span data-ttu-id="56216-130">`System.Windows*` `System.Web.UI*`</span><span class="sxs-lookup"><span data-stu-id="56216-130">`System.Windows*` `System.Web.UI*`</span></span>

     <span data-ttu-id="56216-131">❌NON assegnare lo stesso nome ai tipi negli spazi dei nomi all'interno di un singolo modello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="56216-131">❌ DO NOT give the same name to types in namespaces within a single application model.</span></span>

     <span data-ttu-id="56216-132">Ad esempio, non aggiungere un tipo denominato `Page` allo <xref:System.Web.UI.Adapters?displayProperty=nameWithType> spazio dei nomi, perché lo <xref:System.Web.UI?displayProperty=nameWithType> spazio dei nomi contiene già un tipo denominato `Page` .</span><span class="sxs-lookup"><span data-stu-id="56216-132">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>

- <span data-ttu-id="56216-133">**Spazi dei nomi dell'infrastruttura**</span><span class="sxs-lookup"><span data-stu-id="56216-133">**Infrastructure namespaces**</span></span>

     <span data-ttu-id="56216-134">Questo gruppo contiene spazi dei nomi importati raramente durante lo sviluppo di applicazioni comuni.</span><span class="sxs-lookup"><span data-stu-id="56216-134">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="56216-135">`.Design`Gli spazi dei nomi, ad esempio, vengono utilizzati principalmente per lo sviluppo di strumenti di programmazione.</span><span class="sxs-lookup"><span data-stu-id="56216-135">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="56216-136">Evitare conflitti con i tipi in questi spazi dei nomi non è fondamentale.</span><span class="sxs-lookup"><span data-stu-id="56216-136">Avoiding conflicts with types in these namespaces is not critical.</span></span>

- <span data-ttu-id="56216-137">**Spazi dei nomi principali**</span><span class="sxs-lookup"><span data-stu-id="56216-137">**Core namespaces**</span></span>

     <span data-ttu-id="56216-138">Gli spazi dei nomi principali includono tutti gli spazi dei nomi `System` , esclusi gli spazi dei nomi dei modelli di applicazione e gli spazi dei nomi dell'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="56216-138">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="56216-139">Gli spazi dei nomi principali includono, tra gli altri,,, `System` `System.IO` `System.Xml` e `System.Net` .</span><span class="sxs-lookup"><span data-stu-id="56216-139">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>

     <span data-ttu-id="56216-140">❌NON assegnare nomi di tipi che potrebbero entrare in conflitto con qualsiasi tipo negli spazi dei nomi di base.</span><span class="sxs-lookup"><span data-stu-id="56216-140">❌ DO NOT give types names that would conflict with any type in the Core namespaces.</span></span>

     <span data-ttu-id="56216-141">Ad esempio, non usare mai `Stream` come nome di tipo.</span><span class="sxs-lookup"><span data-stu-id="56216-141">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="56216-142">Si verificherebbe un conflitto con <xref:System.IO.Stream?displayProperty=nameWithType> un tipo di utilizzo molto comune.</span><span class="sxs-lookup"><span data-stu-id="56216-142">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>

- <span data-ttu-id="56216-143">**Gruppi di spazi dei nomi tecnologici**</span><span class="sxs-lookup"><span data-stu-id="56216-143">**Technology namespace groups**</span></span>

     <span data-ttu-id="56216-144">Questa categoria include tutti gli spazi dei nomi con gli stessi primi due nodi dello spazio dei nomi `(<Company>.<Technology>*` , ad esempio `Microsoft.Build.Utilities` e `Microsoft.Build.Tasks` .</span><span class="sxs-lookup"><span data-stu-id="56216-144">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="56216-145">È importante che i tipi che appartengono a una singola tecnologia non siano in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="56216-145">It is important that types belonging to a single technology do not conflict with each other.</span></span>

     <span data-ttu-id="56216-146">❌NON assegnare nomi di tipi che potrebbero essere in conflitto con altri tipi all'interno di una singola tecnologia.</span><span class="sxs-lookup"><span data-stu-id="56216-146">❌ DO NOT assign type names that would conflict with other types within a single technology.</span></span>

     <span data-ttu-id="56216-147">❌NON introdurre conflitti tra i tipi negli spazi dei nomi della tecnologia e uno spazio dei nomi del modello applicativo, a meno che la tecnologia non sia destinata all'utilizzo con il modello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="56216-147">❌ DO NOT introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>

 <span data-ttu-id="56216-148">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="56216-148">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="56216-149">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="56216-149">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="56216-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56216-150">See also</span></span>

- [<span data-ttu-id="56216-151">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="56216-151">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="56216-152">Linee guida per la denominazione</span><span class="sxs-lookup"><span data-stu-id="56216-152">Naming Guidelines</span></span>](naming-guidelines.md)
