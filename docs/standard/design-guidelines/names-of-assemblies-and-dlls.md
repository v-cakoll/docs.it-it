---
title: Nomi di assembly e DLL
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: KrzysztofCwalina
ms.openlocfilehash: 1aeef9e1be6e5fe747f440a8cb7f21095cb22f49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516437"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="aea59-102">Nomi di assembly e DLL</span><span class="sxs-lookup"><span data-stu-id="aea59-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="aea59-103">Un assembly è l'unità di distribuzione e l'identità per i programmi di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="aea59-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="aea59-104">Anche se gli assembly possono estendersi su uno o più file, in genere un assembly viene eseguito il mapping uno a uno con una DLL.</span><span class="sxs-lookup"><span data-stu-id="aea59-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="aea59-105">Pertanto, questa sezione viene descritto solo DLL le convenzioni di denominazione, che possono quindi essere mappate alle convenzioni di denominazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="aea59-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="aea59-106">**✓ DO** scegliere nomi per l'assembly DLL che suggeriscono grandi blocchi di funzionalità, ad esempio System. Data.</span><span class="sxs-lookup"><span data-stu-id="aea59-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="aea59-107">Nomi di assembly e DLL non devono corrispondere ai nomi dello spazio dei nomi, ma è ragionevole seguono il nome dello spazio dei nomi per la denominazione di assembly.</span><span class="sxs-lookup"><span data-stu-id="aea59-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="aea59-108">Una buona norma consiste nel denominare la DLL in base al prefisso comune degli spazi dei nomi contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="aea59-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="aea59-109">Ad esempio, un assembly con due spazi dei nomi `MyCompany.MyTechnology.FirstFeature` e `MyCompany.MyTechnology.SecondFeature`, potrebbe essere chiamato `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="aea59-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="aea59-110">**✓ CONSIDER** denominazione DLL in base al modello seguente:</span><span class="sxs-lookup"><span data-stu-id="aea59-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="aea59-111">in cui `<Component>` contiene uno o più clausole separati da punti.</span><span class="sxs-lookup"><span data-stu-id="aea59-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="aea59-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="aea59-112">For example:</span></span>  
  
 <span data-ttu-id="aea59-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="aea59-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="aea59-114">*Parti protette da copyright © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="aea59-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="aea59-115">*Ristampato con l'autorizzazione di Pearson Education, Inc. dal [linee guida di progettazione di Framework: Convenzioni, linguaggi e modelli per le librerie .NET di riutilizzabile, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina e Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional come parte della serie di sviluppo di Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="aea59-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea59-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aea59-116">See also</span></span>

- [<span data-ttu-id="aea59-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="aea59-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="aea59-118">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="aea59-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
