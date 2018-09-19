---
title: Convenzioni di denominazione
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70888e068782add5ebe5ae1c7da3bdee842faea8
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2018
ms.locfileid: "46325994"
---
# <a name="naming-guidelines"></a><span data-ttu-id="b691c-102">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="b691c-102">Naming Guidelines</span></span>
<span data-ttu-id="b691c-103">Segue un set coerente di convenzioni di denominazione per lo sviluppo di un framework può essere un importante contributo a livello di usabilità del framework.</span><span class="sxs-lookup"><span data-stu-id="b691c-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="b691c-104">Consente al framework di essere usata da molti sviluppatori sui progetti ampiamente separati.</span><span class="sxs-lookup"><span data-stu-id="b691c-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="b691c-105">Oltre la coerenza del form, i nomi di elementi del framework devono essere riconosciuti facilmente e devono fornire la funzione di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="b691c-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="b691c-106">L'obiettivo di questo capitolo è fornire un set di convenzioni di denominazione coerente che risolve in nomi significativi immediato per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="b691c-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="b691c-107">Anche se adottare le convenzioni di denominazione come linee guida sullo sviluppo di codice generale comporta la denominazione più coerente in tutto il codice, è necessario solo per applicarli alle API esposte pubblicamente (pubblici o protetti tipi e membri, e in modo esplicito le interfacce implementate).</span><span class="sxs-lookup"><span data-stu-id="b691c-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b691c-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="b691c-108">In This Section</span></span>  
 [<span data-ttu-id="b691c-109">Convenzioni per l'uso di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="b691c-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="b691c-110">Convenzioni di denominazione generali</span><span class="sxs-lookup"><span data-stu-id="b691c-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="b691c-111">Nomi di assembly e DLL</span><span class="sxs-lookup"><span data-stu-id="b691c-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="b691c-112">Nomi di spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="b691c-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="b691c-113">Nomi di classi, struct e interfacce</span><span class="sxs-lookup"><span data-stu-id="b691c-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="b691c-114">Nomi di membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="b691c-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="b691c-115">Denominazione di parametri</span><span class="sxs-lookup"><span data-stu-id="b691c-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="b691c-116">Denominazione di risorse</span><span class="sxs-lookup"><span data-stu-id="b691c-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="b691c-117">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="b691c-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b691c-118">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b691c-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b691c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b691c-119">See also</span></span>

- [<span data-ttu-id="b691c-120">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="b691c-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
