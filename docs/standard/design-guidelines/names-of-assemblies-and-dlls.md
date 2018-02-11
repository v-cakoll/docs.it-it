---
title: Nomi di assembly e DLL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f74c37821d730ec8dcaa74763967c662bafd6699
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2018
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="86424-102">Nomi di assembly e DLL</span><span class="sxs-lookup"><span data-stu-id="86424-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="86424-103">Un assembly è l'unità di distribuzione e l'identità per i programmi di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="86424-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="86424-104">Anche se l'assembly possono estendersi su uno o più file, in genere un assembly esegue il mapping uno a uno con una DLL.</span><span class="sxs-lookup"><span data-stu-id="86424-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="86424-105">Pertanto, in questa sezione descrive solo DLL convenzioni di denominazione, che è quindi possono eseguire il mapping alle convenzioni di denominazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="86424-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="86424-106">**✓ SI** scegliere nomi per l'assembly DLL che suggeriscono di grandi blocchi di funzionalità, ad esempio System. Data.</span><span class="sxs-lookup"><span data-stu-id="86424-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="86424-107">Nomi di assembly e DLL non sono necessario che corrispondano ai nomi di spazio dei nomi, ma è consigliabile seguire il nome dello spazio dei nomi, la denominazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="86424-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="86424-108">Una buona regola pratica viene assegnato un nome della DLL in base al prefisso comune degli spazi dei nomi contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="86424-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="86424-109">Ad esempio, un assembly con due spazi dei nomi `MyCompany.MyTechnology.FirstFeature` e `MyCompany.MyTechnology.SecondFeature`, potrebbe essere chiamato `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="86424-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="86424-110">**Provare a ✓** denominazione DLL in base al modello seguente:</span><span class="sxs-lookup"><span data-stu-id="86424-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="86424-111">dove `<Component>` contiene uno o più clausole separati da punti.</span><span class="sxs-lookup"><span data-stu-id="86424-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="86424-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="86424-112">For example:</span></span>  
  
 <span data-ttu-id="86424-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="86424-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="86424-114">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="86424-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="86424-115">*State ristampate dall'autorizzazione di Pearson Education, Inc. da [linee guida: convenzioni, idiomi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 di Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="86424-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86424-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86424-116">See Also</span></span>  
 [<span data-ttu-id="86424-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="86424-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="86424-118">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="86424-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
