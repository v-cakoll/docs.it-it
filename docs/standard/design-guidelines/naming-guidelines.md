---
title: Linee guida per la denominazione
ms.date: 10/22/2008
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
ms.openlocfilehash: ad98c0f3b02bdc81e6348493b4e0a02f9cb20ed4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709192"
---
# <a name="naming-guidelines"></a><span data-ttu-id="8c9ae-102">Linee guida per la denominazione</span><span class="sxs-lookup"><span data-stu-id="8c9ae-102">Naming Guidelines</span></span>
<span data-ttu-id="8c9ae-103">Un insieme coerente di convenzioni di denominazione nello sviluppo di un Framework può costituire un importante contributo all'usabilità del Framework.</span><span class="sxs-lookup"><span data-stu-id="8c9ae-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="8c9ae-104">Consente di usare il Framework da molti sviluppatori in progetti ampiamente separati.</span><span class="sxs-lookup"><span data-stu-id="8c9ae-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="8c9ae-105">Oltre la coerenza del modulo, i nomi degli elementi del Framework devono essere facilmente comprensibili e devono indicare la funzione di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="8c9ae-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="8c9ae-106">L'obiettivo di questo capitolo è fornire un set coerente di convenzioni di denominazione che derivano da nomi che hanno un significato immediato per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="8c9ae-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="8c9ae-107">Sebbene l'adozione di queste convenzioni di denominazione come linee guida per lo sviluppo di codice generale comporti la denominazione più coerente in tutto il codice, è necessario applicarle solo alle API esposte pubblicamente (tipi e membri pubblici o protetti e interfacce implementate in modo esplicito).</span><span class="sxs-lookup"><span data-stu-id="8c9ae-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c9ae-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8c9ae-108">In This Section</span></span>  
 [<span data-ttu-id="8c9ae-109">Convenzioni per l'uso di maiuscole e minuscole</span><span class="sxs-lookup"><span data-stu-id="8c9ae-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="8c9ae-110">Convenzioni di denominazione generali</span><span class="sxs-lookup"><span data-stu-id="8c9ae-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="8c9ae-111">Nomi di assembly e DLL</span><span class="sxs-lookup"><span data-stu-id="8c9ae-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="8c9ae-112">Nomi di spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="8c9ae-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="8c9ae-113">Nomi di classi, struct e interfacce</span><span class="sxs-lookup"><span data-stu-id="8c9ae-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="8c9ae-114">Nomi di membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="8c9ae-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="8c9ae-115">Denominazione di parametri</span><span class="sxs-lookup"><span data-stu-id="8c9ae-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="8c9ae-116">Denominazione di risorse</span><span class="sxs-lookup"><span data-stu-id="8c9ae-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="8c9ae-117">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="8c9ae-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="8c9ae-118">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="8c9ae-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9ae-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c9ae-119">See also</span></span>

- [<span data-ttu-id="8c9ae-120">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="8c9ae-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
