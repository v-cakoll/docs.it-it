---
title: Convenzioni di denominazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40da7449c88eaaba92e34374c002c7e175b2ef16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="naming-guidelines"></a><span data-ttu-id="3215f-102">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="3215f-102">Naming Guidelines</span></span>
<span data-ttu-id="3215f-103">Segue un set di convenzioni di denominazione per lo sviluppo di un framework coerente possibile contribuito a livello di usabilità del framework.</span><span class="sxs-lookup"><span data-stu-id="3215f-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="3215f-104">Consente al framework di utilizzabile da molti sviluppatori su progetti separati ampiamente.</span><span class="sxs-lookup"><span data-stu-id="3215f-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="3215f-105">Oltre la coerenza del modulo, nomi degli elementi di framework devono essere facilmente comprensibili e devono indicare la funzione di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="3215f-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="3215f-106">L'obiettivo di questo capitolo è fornire un set di convenzioni di denominazione coerente che risolve in nomi che ha senso immediato per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="3215f-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="3215f-107">Sebbene adottare le convenzioni di denominazione come linee guida sullo sviluppo di codice generale comporta la denominazione più coerente in tutto il codice, è necessario solo per applicarli alle API che vengono esposte pubblicamente (pubblici o protetti di tipi e membri, e in modo esplicito le interfacce implementate).</span><span class="sxs-lookup"><span data-stu-id="3215f-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3215f-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="3215f-108">In This Section</span></span>  
 [<span data-ttu-id="3215f-109">Convenzioni di lettere maiuscole/minuscole</span><span class="sxs-lookup"><span data-stu-id="3215f-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="3215f-110">Convenzioni di denominazione generale</span><span class="sxs-lookup"><span data-stu-id="3215f-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="3215f-111">Nomi degli assembly e DLL</span><span class="sxs-lookup"><span data-stu-id="3215f-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="3215f-112">Nomi degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="3215f-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="3215f-113">Nomi delle classi, strutture e interfacce</span><span class="sxs-lookup"><span data-stu-id="3215f-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="3215f-114">Nomi dei membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="3215f-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="3215f-115">Denominazione dei parametri</span><span class="sxs-lookup"><span data-stu-id="3215f-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="3215f-116">Nomi delle risorse</span><span class="sxs-lookup"><span data-stu-id="3215f-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="3215f-117">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="3215f-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3215f-118">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="3215f-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3215f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3215f-119">See Also</span></span>  
 [<span data-ttu-id="3215f-120">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="3215f-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
