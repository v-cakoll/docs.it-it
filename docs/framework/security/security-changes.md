---
title: Modifiche della sicurezza in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfc48d4fed127b288353f0295f2de1ca33e0a8fe
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971203"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="814c1-102">Modifiche della sicurezza in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="814c1-102">Security Changes in the .NET Framework</span></span>
<span data-ttu-id="814c1-103">Il passaggio più importante alla sicurezza nella .NET Framework 4,5 è la denominazione sicura.</span><span class="sxs-lookup"><span data-stu-id="814c1-103">The most important change to security in the .NET Framework 4.5 is in strong naming.</span></span> <span data-ttu-id="814c1-104">Per una descrizione delle modifiche, vedere [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) .</span><span class="sxs-lookup"><span data-stu-id="814c1-104">See [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
 <span data-ttu-id="814c1-105">.NET Framework offre un modello di sicurezza a due livelli per le applicazioni gestite.</span><span class="sxs-lookup"><span data-stu-id="814c1-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> <span data-ttu-id="814c1-106">Le applicazioni[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] vengono eseguite in un contenitore di sicurezza di Windows tramite cui viene limitato l'accesso alle risorse.</span><span class="sxs-lookup"><span data-stu-id="814c1-106">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="814c1-107">All'interno del contenitore, le applicazioni gestite sono completamente attendibili.</span><span class="sxs-lookup"><span data-stu-id="814c1-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="814c1-108">Da una prospettiva di sicurezza per l'accesso di codice (CAS), non c'è niente che uno sviluppatore possa fare per elevare il livello di privilegi.</span><span class="sxs-lookup"><span data-stu-id="814c1-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="814c1-109">Per informazioni sui privilegi concessi da Windows, vedere [Dichiarazioni di funzionalità delle app (app di Windows Store)](https://go.microsoft.com/fwlink/?LinkId=230436) in Windows Dev Center.</span><span class="sxs-lookup"><span data-stu-id="814c1-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="814c1-110">Per informazioni sulla creazione di un'app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] , vedere [Creare la prima app di Windows Store in C# o Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span><span class="sxs-lookup"><span data-stu-id="814c1-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
