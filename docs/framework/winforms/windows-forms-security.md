---
title: Sicurezza di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: f64d5ef2e9bb0e977b4c007e8c5109ac0c331a84
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799372"
---
# <a name="windows-forms-security"></a><span data-ttu-id="19cfe-102">Sicurezza di Windows Form</span><span class="sxs-lookup"><span data-stu-id="19cfe-102">Windows Forms Security</span></span>
<span data-ttu-id="19cfe-103">Form di Windows dispongono di un modello di sicurezza che è basata su codice (sicurezza livelli sono impostati per il codice, indipendentemente dall'utente che esegue il codice).</span><span class="sxs-lookup"><span data-stu-id="19cfe-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="19cfe-104">Si tratta di oltre agli eventuali schemi di sicurezza che potrebbero essere già presenti nel sistema informatico.</span><span class="sxs-lookup"><span data-stu-id="19cfe-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="19cfe-105">Tra cui gli schemi nel browser (ad esempio, la sicurezza basata sull'area disponibile in Internet Explorer) o il sistema operativo (ad esempio, la sicurezza basata su credenziali di Windows NT).</span><span class="sxs-lookup"><span data-stu-id="19cfe-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19cfe-106">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="19cfe-106">In This Section</span></span>  
 [<span data-ttu-id="19cfe-107">Panoramica della sicurezza in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19cfe-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="19cfe-108">Viene illustrato brevemente il modello di sicurezza di .NET Framework e i passaggi di base necessari per assicurare che i form di Windows nell'applicazione siano protetti.</span><span class="sxs-lookup"><span data-stu-id="19cfe-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="19cfe-109">Accesso più sicuro a file e dati in Windows Form</span><span class="sxs-lookup"><span data-stu-id="19cfe-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="19cfe-110">Viene descritto come accedere ai file e i dati in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="19cfe-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="19cfe-111">Stampa più sicura in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19cfe-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="19cfe-112">Viene descritto come accedere alle funzionalità di stampa in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="19cfe-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="19cfe-113">Considerazioni aggiuntive sulla sicurezza in Windows Form</span><span class="sxs-lookup"><span data-stu-id="19cfe-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="19cfe-114">Descrive finestre, mediante gli Appunti ed eseguire chiamate a codice non gestito in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="19cfe-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="19cfe-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="19cfe-115">Related Sections</span></span>  
 <span data-ttu-id="19cfe-116">[Criteri di sicurezza predefiniti](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19cfe-116">[Default Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="19cfe-117">Elenca le autorizzazioni predefinite concesse nei set di autorizzazioni attendibilità completa, Intranet locale e Internet.</span><span class="sxs-lookup"><span data-stu-id="19cfe-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="19cfe-118">[Amministrazione generale dei criteri di sicurezza](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19cfe-118">[General Security Policy Administration](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="19cfe-119">Fornisce informazioni sull'amministrazione di criteri di sicurezza di .NET Framework e sull'elevazione delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="19cfe-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="19cfe-120">Autorizzazioni pericolose e amministrazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="19cfe-120">Dangerous Permissions and Policy Administration</span></span>](../misc/dangerous-permissions-and-policy-administration.md)  
 <span data-ttu-id="19cfe-121">Vengono descritte alcune autorizzazioni di.NET Framework che possono potenzialmente consentire al sistema di sicurezza di essere aggirate.</span><span class="sxs-lookup"><span data-stu-id="19cfe-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="19cfe-122">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="19cfe-122">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)  
 <span data-ttu-id="19cfe-123">Vengono forniti collegamenti ad argomenti che illustrano le procedure consigliate per la scrittura in modo sicuro di codice rispetto a .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19cfe-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="19cfe-124">[Richiesta di autorizzazioni](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19cfe-124">[Requesting Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="19cfe-125">Viene illustrato l'utilizzo di attributi per informare il runtime di quali autorizzazioni deve eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="19cfe-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="19cfe-126">Concetti chiave sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="19cfe-126">Key Security Concepts</span></span>](../../standard/security/key-security-concepts.md)  
 <span data-ttu-id="19cfe-127">Collegamenti ad argomenti che trattano gli aspetti di base della sicurezza di codice.</span><span class="sxs-lookup"><span data-stu-id="19cfe-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="19cfe-128">Nozioni fondamentali sulla sicurezza per l’accesso al codice</span><span class="sxs-lookup"><span data-stu-id="19cfe-128">Code Access Security Basics</span></span>](../misc/code-access-security-basics.md)  
 <span data-ttu-id="19cfe-129">Vengono illustrate le nozioni fondamentali sull'utilizzo dei criteri di sicurezza del runtime di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19cfe-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="19cfe-130">[Determinazione della necessità di modificare i criteri di sicurezza](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19cfe-130">[Determining When to Modify Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="19cfe-131">Viene illustrato come determinare quando le applicazioni devono molto diversi da criteri di sicurezza predefiniti.</span><span class="sxs-lookup"><span data-stu-id="19cfe-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="19cfe-132">[Distribuzione di criteri di sicurezza](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="19cfe-132">[Deploying Security Policy](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="19cfe-133">Viene descritto il modo migliore per la distribuzione di modifiche ai criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="19cfe-133">Discusses the best manner for deploying security policy changes.</span></span>
