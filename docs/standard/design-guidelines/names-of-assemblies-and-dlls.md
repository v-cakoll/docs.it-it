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
ms.openlocfilehash: f3c5997f777c937e9726b271afa0ae6d7a19b37d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744162"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="f1809-102">Nomi di assembly e DLL</span><span class="sxs-lookup"><span data-stu-id="f1809-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="f1809-103">Un assembly è l'unità di distribuzione e di identità per i programmi di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f1809-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="f1809-104">Sebbene gli assembly possano estendersi su uno o più file, in genere un assembly esegue il mapping uno-a-uno con una DLL.</span><span class="sxs-lookup"><span data-stu-id="f1809-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="f1809-105">Pertanto, in questa sezione vengono descritte solo le convenzioni di denominazione delle DLL, che possono essere mappate alle convenzioni di denominazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="f1809-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="f1809-106">✔️ scegliere nomi per le DLL di assembly che suggeriscono grandi porzioni di funzionalità, ad esempio System. Data.</span><span class="sxs-lookup"><span data-stu-id="f1809-106">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="f1809-107">I nomi di assembly e DLL non devono corrispondere ai nomi degli spazi dei nomi, ma è ragionevole seguire il nome dello spazio dei nomi durante la denominazione degli assembly.</span><span class="sxs-lookup"><span data-stu-id="f1809-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="f1809-108">Una regola empirica consiste nel denominare la DLL in base al prefisso comune degli spazi dei nomi contenuti nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="f1809-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="f1809-109">Ad esempio, è possibile chiamare un assembly con due spazi dei nomi, `MyCompany.MyTechnology.FirstFeature` e `MyCompany.MyTechnology.SecondFeature`, `MyCompany.MyTechnology.dll`.</span><span class="sxs-lookup"><span data-stu-id="f1809-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="f1809-110">✔️ CONSIDERARE la denominazione di dll in base al modello seguente:</span><span class="sxs-lookup"><span data-stu-id="f1809-110">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="f1809-111">dove `<Component>` contiene una o più clausole separate da punti.</span><span class="sxs-lookup"><span data-stu-id="f1809-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="f1809-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f1809-112">For example:</span></span>

 <span data-ttu-id="f1809-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="f1809-113">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="f1809-114">*Parti © 2005, 2009 Microsoft Corporation. Tutti i diritti riservati.*</span><span class="sxs-lookup"><span data-stu-id="f1809-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f1809-115">*Ristampato con l'autorizzazione di Pearson Education, Inc. da [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2a edizione](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) di Krzysztof Cwalina and Brad Abrams, pubblicato il 22 ottobre 2008 da Addison-Wesley Professional nella collana Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="f1809-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f1809-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1809-116">See also</span></span>

- [<span data-ttu-id="f1809-117">Linee guida per la progettazione di Framework</span><span class="sxs-lookup"><span data-stu-id="f1809-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="f1809-118">Convenzioni di denominazione</span><span class="sxs-lookup"><span data-stu-id="f1809-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
