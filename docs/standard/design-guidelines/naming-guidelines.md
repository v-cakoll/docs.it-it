---
title: Convenzioni di denominazione
description: In questa panoramica, vedere le convenzioni di denominazione da usare nello sviluppo di Framework. Passare ad articoli relativi a capitalizzazione, denominazione generale e altre linee guida.
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
ms.openlocfilehash: fbcf5ef5eb02a5e45b5c981b4247ffe1c9c2631b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447147"
---
# <a name="naming-guidelines"></a><span data-ttu-id="caa38-104">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="caa38-104">Naming Guidelines</span></span>
<span data-ttu-id="caa38-105">Un insieme coerente di convenzioni di denominazione nello sviluppo di un Framework può costituire un importante contributo all'usabilità del Framework.</span><span class="sxs-lookup"><span data-stu-id="caa38-105">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="caa38-106">Consente di usare il Framework da molti sviluppatori in progetti ampiamente separati.</span><span class="sxs-lookup"><span data-stu-id="caa38-106">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="caa38-107">Oltre la coerenza del modulo, i nomi degli elementi del Framework devono essere facilmente comprensibili e devono indicare la funzione di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="caa38-107">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="caa38-108">L'obiettivo di questo capitolo è fornire un set coerente di convenzioni di denominazione che derivano da nomi che hanno un significato immediato per gli sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="caa38-108">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="caa38-109">Sebbene l'adozione di queste convenzioni di denominazione come linee guida per lo sviluppo di codice generale comporti la denominazione più coerente in tutto il codice, è necessario applicarle solo alle API esposte pubblicamente (tipi e membri pubblici o protetti e interfacce implementate in modo esplicito).</span><span class="sxs-lookup"><span data-stu-id="caa38-109">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="caa38-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="caa38-110">In This Section</span></span>  
 [<span data-ttu-id="caa38-111">Convenzioni di maiuscole</span><span class="sxs-lookup"><span data-stu-id="caa38-111">Capitalization Conventions</span></span>](capitalization-conventions.md)  
 [<span data-ttu-id="caa38-112">Convenzioni di denominazione generali</span><span class="sxs-lookup"><span data-stu-id="caa38-112">General Naming Conventions</span></span>](general-naming-conventions.md)  
 [<span data-ttu-id="caa38-113">Nomi di assembly e dll</span><span class="sxs-lookup"><span data-stu-id="caa38-113">Names of Assemblies and DLLs</span></span>](names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="caa38-114">Nomi degli spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="caa38-114">Names of Namespaces</span></span>](names-of-namespaces.md)  
 [<span data-ttu-id="caa38-115">Nomi di classi, struct e interfacce</span><span class="sxs-lookup"><span data-stu-id="caa38-115">Names of Classes, Structs, and Interfaces</span></span>](names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="caa38-116">Nomi dei membri dei tipi</span><span class="sxs-lookup"><span data-stu-id="caa38-116">Names of Type Members</span></span>](names-of-type-members.md)  
 [<span data-ttu-id="caa38-117">Parametri di denominazione</span><span class="sxs-lookup"><span data-stu-id="caa38-117">Naming Parameters</span></span>](naming-parameters.md)  
 [<span data-ttu-id="caa38-118">Denominazione di risorse</span><span class="sxs-lookup"><span data-stu-id="caa38-118">Naming Resources</span></span>](naming-resources.md)  
 <span data-ttu-id="caa38-119">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="caa38-119">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="caa38-120">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="caa38-120">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa38-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caa38-121">See also</span></span>

- [<span data-ttu-id="caa38-122">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="caa38-122">Framework Design Guidelines</span></span>](index.md)
