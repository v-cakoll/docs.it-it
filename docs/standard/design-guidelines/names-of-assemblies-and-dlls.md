---
title: Nomi di assembly e DLL
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97bd152cff53fb1c2edb107b6d6b34bd91ca1c49
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972059"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="97bcc-102">Nomi di assembly e DLL</span><span class="sxs-lookup"><span data-stu-id="97bcc-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="97bcc-103">Un assembly è l'unità di distribuzione e l'identità per i programmi di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="97bcc-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="97bcc-104">Anche se gli assembly possono estendersi su uno o più file, in genere un assembly viene eseguito il mapping uno a uno con una DLL.</span><span class="sxs-lookup"><span data-stu-id="97bcc-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="97bcc-105">Pertanto, questa sezione viene descritto solo DLL le convenzioni di denominazione, che possono quindi essere mappate alle convenzioni di denominazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="97bcc-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="97bcc-106">**✓ DO** scegliere nomi per l'assembly DLL che suggeriscono grandi blocchi di funzionalità, ad esempio System. Data.</span><span class="sxs-lookup"><span data-stu-id="97bcc-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="97bcc-107">Nomi di assembly e DLL non devono corrispondere ai nomi dello spazio dei nomi, ma è ragionevole seguono il nome dello spazio dei nomi per la denominazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="97bcc-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="97bcc-108">Una buona norma consiste nel denominare la DLL in base al prefisso comune degli spazi dei nomi contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="97bcc-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="97bcc-109">Ad esempio, un assembly con due spazi dei nomi `MyCompany.MyTechnology.FirstFeature` e `MyCompany.MyTechnology.SecondFeature`, potrebbe essere chiamato `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="97bcc-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="97bcc-110">**✓ CONSIDER** denominazione DLL in base al modello seguente:</span><span class="sxs-lookup"><span data-stu-id="97bcc-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="97bcc-111">in cui `<Component>` contiene uno o più clausole separati da punti.</span><span class="sxs-lookup"><span data-stu-id="97bcc-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="97bcc-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="97bcc-112">For example:</span></span>  
  
 <span data-ttu-id="97bcc-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="97bcc-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="97bcc-114">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="97bcc-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="97bcc-115">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="97bcc-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97bcc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97bcc-116">See also</span></span>

- [<span data-ttu-id="97bcc-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="97bcc-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="97bcc-118">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="97bcc-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
